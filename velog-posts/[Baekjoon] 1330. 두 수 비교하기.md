<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>두 정수 A와 B가 주어졌을 때, A와 B를 비교하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 A와 B가 주어진다. A와 B는 공백 한 칸으로 구분되어져 있다.</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 다음 세 가지 중 하나를 출력한다.</p>
<ul>
<li>A가 B보다 큰 경우에는 '<code>&gt;</code>'를 출력한다.</li>
<li>A가 B보다 작은 경우에는 '<code>&lt;</code>'를 출력한다.</li>
<li>A와 B가 같은 경우에는 '<code>==</code>'를 출력한다.</li>
</ul>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>1 2
10 2
5 5</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>&lt;
&gt;
==</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력(비교 후 기호)</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<p>없음</p>
<hr />
<h3 id="요약">요약</h3>
<p>없음</p>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const fs = require('fs');
const num = fs.readFileSync('/dev/stdin').toString().split(' ');
const a = parseInt(num[0]);
const b = parseInt(num[1]);

if(a == b) {
    console.log('==')
} else if(a &gt; b) {
    console.log('&gt;')
} else {
    console.log('&lt;')
};</code></pre>
<hr />