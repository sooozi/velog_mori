<p>문제 링크
<a href="https://www.acmicpc.net/problem/18108">https://www.acmicpc.net/problem/18108</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>ICPC Bangkok Regional에 참가하기 위해 수완나품 국제공항에 막 도착한 팀 레드시프트 일행은 눈을 믿을 수 없었다. 공항의 대형 스크린에 올해가 2562년이라고 적혀 있던 것이었다.</p>
<p>불교 국가인 태국은 불멸기원(佛滅紀元), 즉 석가모니가 열반한 해를 기준으로 연도를 세는 불기를 사용한다. 반면, 우리나라는 서기 연도를 사용하고 있다. 불기 연도가 주어질 때 이를 서기 연도로 바꿔 주는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>서기 연도를 알아보고 싶은 불기 연도 <em>y</em>가 주어진다. (1000 ≤ <em>y</em> ≤ 3000)</p>
<h2 id="출력">출력</h2>
<p>불기 연도를 서기 연도로 변환한 결과를 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>2541</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>1998</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<hr />
<h3 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h3>
<p>예제를 보면 불기 연도와 서기 연도는 543년이 차이난다.</p>
<p>‘입력값(불기 연도 2541) - 543 = 서기 연도’로 계산해보자!</p>
<h3 id="my-solution-💡">My Solution 💡</h3>
<pre><code class="language-jsx">const thailand = require('fs').readFileSync('/dev/stdin').toString().split(' ');
const korea = thailand - 543;
console.log(korea);</code></pre>
<h3 id="요약">요약</h3>
<ul>
<li>문제를 풀기 전 어떤 규칙을 가졌는 지 먼저 생각해보자!</li>
</ul>