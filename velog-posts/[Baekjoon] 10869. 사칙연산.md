<p>문제 링크
<a href="https://www.acmicpc.net/problem/10869">https://www.acmicpc.net/problem/10869</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>두 자연수 A와 B가 주어진다. 이때, A+B, A-B, A*B, A/B(몫), A%B(나머지)를 출력하는 프로그램을 작성하시오. </p>
<h2 id="입력">입력</h2>
<p>두 자연수 A와 B가 주어진다. (1 ≤ A, B ≤ 10,000)</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 A+B, 둘째 줄에 A-B, 셋째 줄에 A*B, 넷째 줄에 A/B, 다섯째 줄에 A%B를 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>7 3</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>10
4
21
2
1</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>Math.floor()</p>
<hr />
<pre><code class="language-jsx"> Math.floor(a / b)</code></pre>
<ul>
<li>자바스크립트에서 ‘/’는 항상 부동소수점 숫자로 반환되기 때문에 정수를 원하는 경우, 소수점을 포함하지 않는 결과를 위해 Math.floor()를 사용해야 한다.</li>
</ul>
</li>
<li><p>부동소수점 (Floating point)</p>
<hr />
<ul>
<li>자바스크립트에서 ‘/’는 항상 부동소수점 숫자로 반환되기 때문에 정수를 원하는 경우, 소수점을 포함하지 않는 결과를 위해 Math.floor()를 사용해야 한다.</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>Math.floor()<ul>
<li>나눗셈 연산 진행 시 정수 결과를 원하는 경우 사용</li>
</ul>
</li>
<li>부동소수점 어렵당….</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const num = require('fs').readFileSync('/dev/stdin').toString().split(' ');
const a = parseInt(num[0]);
const b = parseInt(num[1]);

console.log(`${a + b}\n${a - b}\n${a * b}\n${Math.floor(a / b)}\n${a % b}`);</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%8B%A4%EC%88%98-%ED%91%9C%ED%98%84%EB%B6%80%EB%8F%99-%EC%86%8C%EC%88%98%EC%A0%90-%EC%9B%90%EB%A6%AC-%ED%95%9C%EB%88%88%EC%97%90-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0">☕ 실수 표현(부동 소수점) 원리 한눈에 이해하기</a></p>
<p><a href="https://www.youtube.com/watch?v=ZQDsWySjY6g">부동소수점 (+ 실수계산 오차가 생기는 이유)</a></p>