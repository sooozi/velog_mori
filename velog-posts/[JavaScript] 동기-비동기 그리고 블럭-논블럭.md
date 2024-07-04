<p>저번에 동기, 비동기에 대해서 알아보았자나요...
그런데 동기, 비동기를 공부하다보면 나오는 블록인지 블럭인지...
그리고 저번 설명에 나왔던 이미지에도 잠깐 출연했던 요 친구 발견한 사람~
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/325191c9-1a6e-472e-bf2f-f87921ab4249/image.png" />
이벤트 루프도 너무 너무 너무 중요하지만!
동기, 비동기와 함께 반드시 알고 가야하는 블럭/논블럭! 뽀개러 가보자고! 아자아자아자! 😀😀😀
<br /><br /></p>
<blockquote>
<h2 id="동기-비동기-한-줄-복습">동기, 비동기 한 줄 복습</h2>
</blockquote>
<h2 id="🟨-1-동기-비동기">🟨 1. 동기, 비동기</h2>
<h3 id="🟨-1-1-sync-동기">🟨 1-1. Sync 동기</h3>
<p>요청 작업에 대해 완료 여부를 따져 <strong>순차대로 처리</strong>한다.</p>
<ul>
<li>😸장점 : 설계가 간단, 직관적, 요청&amp;응답 순서 보장</li>
<li>😿단점 : 작업이 많아지면 자원, 시간 낭비 및 속도 저하, 병렬적 여러 작업 수행 불가능</li>
</ul>
<h3 id="🟨-1-2-async-비동기">🟨 1-2. Async 비동기</h3>
<p>요청 작업에 대해 <strong>완료 여부를 따지지 않고 다음 작업을 그대로 수행</strong>한다.</p>
<ul>
<li>😸장점 : 속도, 성능 향상, 병렬적 여러 작업 수행 가능, 사용자 경험 개선 가능</li>
<li>😿단점 : 설계 복잡, 요청&amp;응답 순서 보장 불가</li>
</ul>
<p><strong><a href="https://velog.io/@sooozi/JavaScript-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EC%99%80-%EB%8F%99%EA%B8%B0-%EB%B9%84%EB%8F%99%EA%B8%B0-%EC%B2%98%EB%A6%AC">💁‍♀️ 동기, 비동기 다시 보러가기</a></strong></p>
<p><br /><br /></p>
<blockquote>
<h2 id="블럭과-논블럭">블럭과 논블럭</h2>
</blockquote>
<h2 id="🟨-2-블럭-논블럭">🟨 2. 블럭, 논블럭</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/325191c9-1a6e-472e-bf2f-f87921ab4249/image.png" />
블럭과 논블럭은 쉽게 말해 현재의 작업의 중단 유무를 나타내는 프로세스의 실행 방식을 말한다. 누군가 블럭과 논블럭의 차이점을 이야기 해보세요! 라고 말한다면 <span style="color: #ffb02e;"><strong>작업 호출 방식</strong></span>과 <span style="color: #ffb02e;"><strong>제어권</strong></span>이라고 말하면 더 이해가 쉬워질 것이다 :) 그리고 글보다는 아래 그림을 살펴보고 글을 읽어보니 더 이해가 쉬웠다...🫢
<br /></p>
<h3 id="🟨-2-1-block-blocking">🟨 2-1. Block, Blocking</h3>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/1081885f-a670-4e95-aa20-15e3ca016a38/image.png" />1. A 함수가 B 함수를 호출
2. B 함수에게 제어권 넘어감
3. B 함수 실행, A 함수 실행 중단
4. B 함수 완료, A 함수에게 제어권 돌려줌
5. 제어권을 돌려받은 A 함수는 다시 함수 실행</p>
<p>A 함수 호출 시 B 함수 호출 후 B 함수 완료까지 기다렸다가 A 함수 실행을 마저 실행한다.</p>
<ul>
<li>🗨️제어권 : A가 제어권을 가지고 있다가 B에게 제어권을 넘겨주고 B의 작업이 완료되면 A에게 제어권이 돌아옴 <span style="color: #ffb02e;"><strong>제어권 줬다가 다시 받어 ^^</strong></span><br />

</li>
</ul>
<h3 id="🟨-2-2-non-block-non-blocking">🟨 2-2. Non-Block, Non-Blocking</h3>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/7c01bd5a-640c-4cff-8f9c-84363c788115/image.png" />1. A 함수가 B 함수를 호출
2. A 함수가 제어권을 유지한 상태로 B 함수 실행
3. A 함수, B 함수 각자 함수 실행 진행</p>
<p>A 함수 호출 시 B 함수 호출 후 계속해서 A는 제어권을 가지고 작업을 진행한다.</p>
<ul>
<li>🗨️제어권 : A함수가 제어권을 계속 가지고 함수를 실행하며 중간에 B함수만 실행한다. <span style="color: #ffb02e;"><strong>제어권 안 줘!</strong></span></li>
</ul>
<br />

<p><span style="color: #ffb02e;">💁‍♀️ 그러면 동기, 비동기, 블럭, 논블럭을 섞으면 어떻게 된다는 이야기야...? 도대체...?</span></p>
<br />

<blockquote>
<h2 id="동기비동기블럭논블럭-냅따-섞기">동기/비동기/블럭/논블럭 냅따 섞기</h2>
</blockquote>
<h2 id="🟨-3-본격-case-study">🟨 3. 본격 Case Study</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/fc121537-eb7f-4904-a35e-c1e9b052ba48/image.png" />
동기, 비동기, 블럭, 논블럭 공부하면 한번씩 꼭 보는 이미지이죠? ㅎㅎㅎ
하지만 저는 요 이미지를 보아도 이해가 되지 않더라구요 ㅠㅠ</p>
<p>냅따 섞기 이해를 위해 수많은 예들을 살펴보며 힘들어했던 나날들...
하지만 이 분의 케이스 스터디를 보며 얼추 이해를 해버리고만 나 🥲🥲🥲🥲🥲</p>
<p>수많은 블로그글 중에 가장 이해하기 좋았던 케이스 스터디 예시를 소개합니다!!!</p>
<p>원본글 : <a href="https://musma.github.io/2019/04/17/blocking-and-synchronous.html">https://musma.github.io/2019/04/17/blocking-and-synchronous.html</a>
(정말 감사합니다 ㅠㅠ)</p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/0db7d22e-e27f-435a-9c99-2536a2b57fde/image.png" /></p>
<p><span style="color: #ffb02e;"><strong>케이스 스터디 곱씹기</strong></span></p>
<ul>
<li><strong>동기 &amp; 블로킹</strong> : 다른 작업 결과가 자신의 작업에 영향을 주는 경우 활용 가능, 파일을 읽어 내용을 처리하는 로직에서 사용 가능!</li>
<li>비동기 &amp; 블로킹 : (거의 없음) 다른 작업의 결과를 바로 처리하지 않아 순서대로 작업을 수행하지 않는 방식, Node.js + MySQL</li>
<li><strong>동기 &amp; 논블로킹</strong> : 다른 작업 결과를 바로 처리하여 작업을 순차대로 수행하는 경우 활용 가능, 흔하지 않은 케이스이지만 게임에서 맵을 이용할 때 화면에 뜨는 로딩 스크린!</li>
<li><strong>비동기 &amp; 논블로킹</strong> : 다른 작업 결과가 자신의 작업에 영향을 주지 않는 경우 활용 가능, 작업량이 많거나 시간이 오래 걸리는 작업 처리에 적합!</li>
</ul>
<p><br /><br /></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/f5b9cc85-ba56-4340-8824-565a2f7b90a9/image.png" /></p>
<br />

<p>동기와 비동기, 블럭, 논블럭까지 열심히 구글링을..해보았는데요 ^^ 깔꼼하게 정리가 되었을지 모르겠는고에요 :)
다음에는 저번에 다루었던 비동기 처리를 만들어주는 <strong>이벤트 루프</strong>에 대해 찾아보고 정리해보는 시간을 가져보겠슴미다 ㅎ.ㅎ</p>
<p>끝!</p>
<p><br /><br /><br />
✅ 참고
<em><a href="https://musma.github.io/2019/04/17/blocking-and-synchronous.html">https://musma.github.io/2019/04/17/blocking-and-synchronous.html</a></em>
<em><a href="https://inpa.tistory.com/entry/%F0%9F%91%A9%E2%80%8D%F0%9F%92%BB-%EB%8F%99%EA%B8%B0%EB%B9%84%EB%8F%99%EA%B8%B0-%EB%B8%94%EB%A1%9C%ED%82%B9%EB%85%BC%EB%B8%94%EB%A1%9C%ED%82%B9-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC">https://inpa.tistory.com/entry/%F0%9F%91%A9%E2%80%8D%F0%9F%92%BB-%EB%8F%99%EA%B8%B0%EB%B9%84%EB%8F%99%EA%B8%B0-%EB%B8%94%EB%A1%9C%ED%82%B9%EB%85%BC%EB%B8%94%EB%A1%9C%ED%82%B9-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC</a></em></p>