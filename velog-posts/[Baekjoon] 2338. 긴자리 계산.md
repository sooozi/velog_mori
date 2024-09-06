<p>문제 링크
<a href="https://www.acmicpc.net/problem/2338">https://www.acmicpc.net/problem/2338</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>두 수 A, B를 입력받아, A+B, A-B, A×B를 구하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 A가, 둘째 줄에 B가 주어진다. 각각의 수는 10진수로 1,000자리를 넘지 않으며 양수와 음수가 모두 주어질 수 있다.</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 A+B, 둘째 줄에 A-B, 셋째 줄에 A×B를 출력한다. 각각을 출력할 때, 답이 0인 경우를 제외하고는 0으로 시작하게 해서는 안 된다(1을 01로 출력하면 안 된다는 의미).</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>1
-1</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>0
2
-1</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>BigInt</p>
<hr />
<ul>
<li>일반 정수 타입 사용 시 숫자가 1000자리라면 숫자를 정확하게 처리할 수 없다.</li>
<li>숫자가 너무 커서 넘버 타입이 처리할 수 있는 범위를 초과하면 잘못된 결과가 나올 수 있다.</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>숫자가 커질 수 있다면 BigInt를 사용하자!</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const num = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');
const a = BigInt(num[0]);
const b = BigInt(num[1]);

console.log((a + b).toString());
console.log((a - b).toString());
console.log((a * b).toString());</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://ko.javascript.info/bigint">BigInt</a></p>