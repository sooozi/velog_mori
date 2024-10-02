<p>문제링크
<a href="https://www.acmicpc.net/problem/8958">https://www.acmicpc.net/problem/8958</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>&quot;OOXXOXXOOO&quot;와 같은 OX퀴즈의 결과가 있다. O는 문제를 맞은 것이고, X는 문제를 틀린 것이다. 문제를 맞은 경우 그 문제의 점수는 그 문제까지 연속된 O의 개수가 된다. 예를 들어, 10번 문제의 점수는 3이 된다.</p>
<p>&quot;OOXXOXXOOO&quot;의 점수는 1+2+0+0+1+0+0+1+2+3 = 10점이다.</p>
<p>OX퀴즈의 결과가 주어졌을 때, 점수를 구하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 테스트 케이스의 개수가 주어진다. 각 테스트 케이스는 한 줄로 이루어져 있고, 길이가 0보다 크고 80보다 작은 문자열이 주어진다. 문자열은 O와 X만으로 이루어져 있다.</p>
<h2 id="출력">출력</h2>
<p>각 테스트 케이스마다 점수를 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>5
OOXXOXXOOO
OOXXOOXXOO
OXOXOXOXOXOXOX
OOOOOOOOOO
OOOOXOOOOXOOOOX</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>10
9
7
55
30</code></pre><h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 구현 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>첫째 줄 테스트 케이스 개수 testLength 변수에 담아두기</p>
<p>각 행마다 for문 순회 각 배열마다 O인 경우 숫자 늘리며 더하기, X는 0으로 변경</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">const input = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

const testLength = Number(input[0]);

for (let i = 1; i &lt;= testLength; i++) {
    let test = input[i];
    let score = 0;
    let currentScore = 0;

    for (let t = 0; t &lt; test.length; t++) {
        if(test[t] === 'O') {
            currentScore++;
        } else {
            currentScore = 0;
        }
        score += currentScore;
    }
    console.log(score);
}</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li><p>더 간결한 방법 찾아보기!</p>
<hr />
<pre><code class="language-jsx"> const input = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

 // 첫 번째 줄은 테스트 케이스의 개수를 나타냄
 for (let i = 1; i &lt;= Number(input[0]); i++) {
     // 각 테스트 케이스마다 점수를 계산
     let score = 0;          // 전체 점수를 저장할 변수
     let currentScore = 0;    // 현재 연속된 'O'에 대한 점수를 저장할 변수

     // 현재 테스트 케이스 문자열을 순회
     for (const char of input[i]) {
         // 'O'이면 currentScore를 1 증가, 'X'이면 currentScore는 0으로 초기화
         currentScore = (char === 'O') ? currentScore + 1 : 0;

         // 현재까지의 점수를 score에 더함
         score += currentScore;
     }

     // 각 테스트 케이스의 점수를 출력
     console.log(score);
 }</code></pre>
</li>
</ol>
<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li>예쁘게 코드짜기 어렵다…^<strong><strong><strong><strong>___</strong></strong></strong></strong>^</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://velog.io/@onea/JS-for-...of%EC%99%80-for-...in%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90">[JS] for ...of와 for ...in의 차이점</a></p>