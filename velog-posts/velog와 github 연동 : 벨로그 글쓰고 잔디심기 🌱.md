<h3 id="1-깃허브에-레포지토리-생성">1. 깃허브에 레포지토리 생성</h3>
<p>중요! Public repository로 생성하기!
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/71be1843-076a-4111-bcbc-c1b788a7d68f/image.png" /></p>
<h3 id="2-폴더링-및-파일-생성">2. 폴더링 및 파일 생성</h3>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/4e3a6c33-5f5f-481d-a18e-72331fd1f603/image.png" /></p>
<h3 id="3-update_blogyml파일에-github-action-작성">3. &quot;update_blog.yml&quot;파일에 github action 작성</h3>
<ul>
<li>매일 자정 또는 해당 레포지토리가 push 될 때 파이썬 스크립트를 실행하는 코드</li>
</ul>
<p><span style="color: indianred;"><strong>📛 코드 속 벨로그 주소 확인!!! 📛</strong></span></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/57a955e2-0034-4ade-b08b-cb6b4e060cca/image.png" /></p>
<pre><code>name: Update Blog Posts


on:
  push:
      branches:
        - master  # 또는 워크플로우를 트리거하고 싶은 브랜치 이름
  schedule:
    - cron: '0 0 * * *'  # 매일 자정에 실행

jobs:
  update_blog:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v2

    - name: Push changes
      run: |
        git config --global user.name 'github-actions[bot]'
        git config --global user.email 'github-actions[bot]@users.noreply.github.com'
        git push https://${{ secrets.GH_PAT }}@github.com/rimgosu/velog.git

    - name: Set up Python
      uses: actions/setup-python@v2
      with:
        python-version: '3.x'

    - name: Install dependencies
      run: |
        pip install feedparser gitpython

    - name: Run script
      run: python scripts/update_blog.py</code></pre><h3 id="4-update_blogpy파일에-파이썬-스크립트-작성">4. &quot;update_blog.py&quot;파일에 파이썬 스크립트 작성</h3>
<p><span style="color: indianred;"><strong>📛 코드 속 벨로그 아이디 확인!!! 📛</strong></span>
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/b7017e2c-c900-40f4-846b-96b9cb1858ad/image.png" /></p>
<pre><code>import feedparser
import git
import os

# 벨로그 RSS 피드 URL
# example : rss_url = 'https://api.velog.io/rss/@soozi'
rss_url = 'https://api.velog.io/rss/@[벨로그 아이디]'

# 깃허브 레포지토리 경로
repo_path = '.'

# 'velog-posts' 폴더 경로
posts_dir = os.path.join(repo_path, 'velog-posts')

# 'velog-posts' 폴더가 없다면 생성
if not os.path.exists(posts_dir):
    os.makedirs(posts_dir)

# 레포지토리 로드
repo = git.Repo(repo_path)

# RSS 피드 파싱
feed = feedparser.parse(rss_url)

# 각 글을 파일로 저장하고 커밋
for entry in feed.entries:
    # 파일 이름에서 유효하지 않은 문자 제거 또는 대체
    file_name = entry.title
    file_name = file_name.replace('/', '-')  # 슬래시를 대시로 대체
    file_name = file_name.replace('\\', '-')  # 백슬래시를 대시로 대체
    # 필요에 따라 추가 문자 대체
    file_name += '.md'
    file_path = os.path.join(posts_dir, file_name)

    # 파일이 이미 존재하지 않으면 생성
    if not os.path.exists(file_path):
        with open(file_path, 'w', encoding='utf-8') as file:
            file.write(entry.description)  # 글 내용을 파일에 작성

        # 깃허브 커밋
        repo.git.add(file_path)
        repo.git.commit('-m', f'Add post: {entry.title}')

# 변경 사항을 깃허브에 푸시
repo.git.push()</code></pre><h3 id="5-pat-권한-받기">5. PAT 권한 받기</h3>
<ul>
<li>github 계정 - Settings - Developer Settings - Personal access tokens (classic) - Generate New Token -  'Note'에는 토큰의 이름 쓰고 repo, workflow 클릭 - Generate new token
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/92eb7a4a-0850-4ea6-ac57-884c4829390f/image.png" /></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/18b2e7d9-d5e8-49a4-9876-bc89816b935e/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/9372cdcc-e4e1-4ff7-97fc-5519062ba115/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/8042c8ef-ae3b-43c4-bb2a-f94331e9f38c/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/d7b8bfb9-8f31-4636-861b-7fc9cc9bae63/image.png" /></p>
<ul>
<li>받은 토큰 복사 (한 번 밖에 볼 수 없으니 반드시 복!사!해!)
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/a6133c07-8b47-4a11-8f19-4ea18997753c/image.png" /></li>
</ul>
<ul>
<li><p>위에서 생성한 레포지토리 - Settings - Actions secrets and variables - Actions - New Repository Secret
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/7970de97-1bff-4180-ad95-750c3f32fdd2/image.png" /></p>
</li>
<li><p>Name : 원하는 이름 작성 / Secret : [2번에서 발급받은 토큰]
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/b2436d13-fa7d-4341-a451-fd2a722f115b/image.png" /></p>
</li>
<li><p>내가 fail한 이유.... (미안한고야...깃허브야...)
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/c0434e87-895f-4def-aff8-76aceae8f37b/image.png" /></p>
</li>
<li><p>해결방법(GH_PAT_MORI로 이름 변경)
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/0153cd19-09e7-4205-a6d6-2b988b5903ab/image.png" /></p>
</li>
</ul>
<h3 id="6-커밋-또는-자정까지-웨이링하기">6. 커밋 또는 자정까지 웨이링하기</h3>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/8e0dba9f-f9f8-4e69-8d9c-41d124a3f025/image.png" /></p>
<h3 id="7-잔디심기-실패">7. 잔디심기 실패</h3>
<p><strong>깜찍하게 실패한 이유</strong></p>
<ul>
<li>깃허브가 친절하게 &quot;응~ 너 실패~&quot; 메일을 보내주었습니다 😊
Update Blog Posts: All jobs have failed</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/4bfd8f63-83c1-461f-a534-341c10d1df71/image.png" /></p>
<ul>
<li>당장 들어가서 확인해보니 레포지토리 주소를 잘못 적었다고 말해줍니다! (쏘친절..고마워...)
수정하고 다음날 다시 확인해보겠습니다...나는 다시 웨이링할꼬아...
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/15be5c53-4f0b-4e60-8711-e7052cd7c8ec/image.png" /></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/59400adc-af0a-4f87-a1ab-b21549e166a6/image.png" /></p>
<h3 id="8-잔디심기-실패_2">8. 잔디심기 실패_2</h3>
<p><strong>깜찍하게 실패한 이유</strong></p>
<ul>
<li><p>깃허브가 다시한번 친절하게 &quot;응~ 너 실패~&quot; 메일을 보내주었습니다 😊
Update Blog Posts: All jobs have failed</p>
</li>
<li><p>The requested URL returned error: 403
해당 오류가 발생했다고 합니다!!! 당장 구글링
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/74d7ca58-3294-4006-bfcc-5a9f00cbb651/image.png" /></p>
</li>
<li><p>저장서 권한이 없어서 발생한 오류라고 합니다!
더 구글링 해보니 사용자 이름을 기재해야 한다는 글을 발견하고 냅따 수정했습니다.
<a href="https://github.com/orgs/community/discussions/68891">https://github.com/orgs/community/discussions/68891</a>
<a href="https://velog.io/@nu11/Git-PUSH-%ED%95%A0-%EB%95%8C-403-%EC%97%90%EB%9F%AC-%EB%B0%9C%EC%83%9DThe-requested-URL-returned-error-403">https://velog.io/@nu11/Git-PUSH-%ED%95%A0-%EB%95%8C-403-%EC%97%90%EB%9F%AC-%EB%B0%9C%EC%83%9DThe-requested-URL-returned-error-403</a>
수정하고 다음날 다시 확인해보겠습니다...또 다시 웨이링할꼬아ㅜㅜ</p>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/97899c45-0193-4ad0-a79d-4f68174c70a6/image.png" /></p>
<h3 id="9-잔디심기-실패_3">9. 잔디심기 실패_3</h3>
<p><strong>깜찍하게 실패한 이유 (점점 분노 차오르는 중 🔥🔥🔥)</strong></p>
<ul>
<li><p>깃허브가 다시한번 친절하게 &quot;응~ 너 실패~&quot; 메일을 보내주었습니다 😊
Update Blog Posts: All jobs have failed</p>
</li>
<li><p>Run git credential-manager reject <a href="https://github.com">https://github.com</a>
git credential-manager reject <a href="https://github.com">https://github.com</a>
git config --global user.name 'github-actions[bot]'
git config --global user.email 'github-actions[bot]@users.noreply.github.com'
git push https://***github.com/sooozi/velog_mori.git
shell: /usr/bin/bash -e {0}
git: 'credential-manager' is not a git command. See 'git --help'.
Error: Process completed with exit code 1.</p>
</li>
</ul>
<p>새로운 오류 발견!!! 이번에는 지피티 너를 믿는당
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/2d58f841-21fc-43a8-805f-97cb9e7b0471/image.png" /></p>
<ul>
<li>해결방법
이 오류는 Git이 credential-manager를 인식하지 못하는 것으로 보입니다. Git Credential Manager는 Windows에서 자동으로 설치되지만 macOS 또는 Linux에서는 일반적으로 포함되어 있지 않습니다. 윈도우에서 Git Credential Manager가 기본적으로 설치되어 있지만 여전히 해당 오류가 발생한다면 몇 가지 문제가 있을 수 있습니다. 여러 가지 방법을 시도하여 문제를 해결할 수 있습니다.</li>
</ul>
<ol>
<li>Git Credential Manager 다시 설치: 먼저 시스템에서 Git Credential Manager를 제거하고 다시 설치하는 것이 좋습니다. Git Credential Manager를 재설치하면 문제를 해결할 수 있습니다.</li>
<li>환경 변수 확인: 때로는 시스템 환경 변수가 Git Credential Manager를 찾지 못할 수 있습니다. 이 경우 시스템 환경 변수에 Git 및 Git Credential Manager가 설치된 경로를 추가해야 합니다. 예를 들어, C:\Program Files\Git\mingw64\libexec\git-core와 같은 경로를 추가할 수 있습니다.</li>
<li>Git 업데이트: Git 및 Git Credential Manager의 최신 버전을 설치하여 문제를 해결할 수도 있습니다. Git 및 Git Credential Manager가 최신 상태인지 확인하고 업데이트해 보세요.</li>
<li>Git for Windows 재설치: Git for Windows를 완전히 제거하고 다시 설치하여 문제를 해결할 수도 있습니다. 이렇게 하면 시스템에서 Git과 관련된 모든 구성 요소를 완전히 재설정할 수 있습니다.</li>
<li>관리자 권한으로 실행: Git 명령을 관리자 권한으로 실행하여 문제를 해결할 수 있습니다. 명령 프롬프트나 PowerShell을 관리자 권한으로 실행한 다음 명령을 실행해 보세요.</li>
</ol>
<p>이러한 방법 중 하나로 문제를 해결할 수 있어야 합니다. 계속해서 문제가 지속되면 추가적인 디버깅이 필요할 수 있습니다.</p>
<p>=&gt; Git Credential Manager를 설치하고 설정해보자!!!!</p>
<p><br /><br /><br /><br />
✅ 참고
<a href="https://velog.io/@rimgosu/velog-%EA%B8%80-%EC%9E%91%EC%84%B1-%EC%8B%9C-%EC%9E%90%EB%8F%99%EC%9C%BC%EB%A1%9C-github%EC%97%90-%EC%BB%A4%EB%B0%8B%ED%95%98%EA%B8%B0">https://velog.io/@rimgosu/velog-글-작성-시-자동으로-github에-커밋하기</a></p>