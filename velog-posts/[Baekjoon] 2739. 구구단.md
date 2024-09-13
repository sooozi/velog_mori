<p>문제 링크
<a href="https://www.acmicpc.net/problem/2739">https://www.acmicpc.net/problem/2739</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 N이 주어진다. N은 1보다 크거나 같고, 9보다 작거나 같다.</p>
<h2 id="출력">출력</h2>
<p>출력형식과 같게 N<em>1부터 N</em>9까지 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>2</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18</code></pre><h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 수학 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>1부터 9까지 돌려돌려~</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">const num = parseInt(require('fs').readFileSync('/dev/stdin').toString());
for(let i = 1; i &lt; 10; i++){
    console.log(`${num} * ${i} = ${num * i}`)
}</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li>--</li>
</ol>
<pre><code>---

```jsx

```</code></pre><hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li>잘한다 잘한다 잘한다~</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>