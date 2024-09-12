<p>문제 링크
<a href="https://www.acmicpc.net/problem/2475">https://www.acmicpc.net/problem/2475</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>컴퓨터를 제조하는 회사인 KOI 전자에서는 제조하는 컴퓨터마다 6자리의 고유번호를 매긴다. 고유번호의 처음 5자리에는 00000부터 99999까지의 수 중 하나가 주어지며 6번째 자리에는 검증수가 들어간다. 검증수는 고유번호의 처음 5자리에 들어가는 5개의 숫자를 각각 제곱한 수의 합을 10으로 나눈 나머지이다.</p>
<p>예를 들어 고유번호의 처음 5자리의 숫자들이 04256이면, 각 숫자를 제곱한 수들의 합 0+16+4+25+36 = 81 을 10으로 나눈 나머지인 1이 검증수이다.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 고유번호의 처음 5자리의 숫자들이 빈칸을 사이에 두고 하나씩 주어진다.</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 검증수를 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>0 4 2 5 6</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>1</code></pre><h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>공백을 기준으로 자르고 각 숫자를 더한다.</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">const input = require('fs').readFileSync('/dev/stdin').toString().split(' ');
const sumOfSquares = input.reduce((sum, num) =&gt; {
  return sum + Math.pow(Number(num), 2);
}, 0);
console.log(sumOfSquares % 10);</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li><p><strong>Array.prototype.reduce</strong></p>
<hr />
<p> 배열의 각 요소에 대해 주어진 함수를 실행하고, 그 결과를 누적하여 하나의 값을 반환한다.</p>
<pre><code class="language-jsx"> array.reduce((accumulator, currentValue) =&gt; {
   // 누적 계산 로직
 }, initialValue);</code></pre>
<ul>
<li><strong><code>accumulator</code></strong>: 현재까지 누적된 값 / 초기값(<code>initialValue</code>)에서 시작, 각 반복에서 업데이트</li>
<li><strong><code>currentValue</code></strong>: 현재 배열 요소</li>
<li><strong><code>initialValue</code></strong>: 누적값의 초기값</li>
</ul>
</li>
</ol>
<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li>메서드들 잘 기억하장…!</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://5kdk.tistory.com/2">[JavaScript] reduce(리듀스) 함수 알아보기</a></p>