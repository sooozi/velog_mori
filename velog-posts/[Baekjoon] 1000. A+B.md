<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 A와 B가 주어진다. (0 &lt; A, B &lt; 10)</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 A+B를 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력-1">예제 입력 1</h2>
<pre><code>1 2</code></pre><h2 id="예제-출력-1">예제 출력 1</h2>
<pre><code>3</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>파일 시스템 모듈</p>
<hr />
<pre><code class="language-jsx"> const fs = require('fs');</code></pre>
<ul>
<li><p>‘fs’라는 모듈을 불러오는 코드</p>
</li>
<li><p>Node.js에서 파일 시스템과 상호작용할 수 있게 해주는 모듈</p>
<ul>
<li>해당 모듈 사용 시 파일 읽고 쓰는 작업 가능!</li>
</ul>
<pre><code class="language-jsx">const num = fs.readFileSync('/dev/stdin').toString().split(' ');</code></pre>
</li>
<li><p>‘fs’ 모듈을 사용해 입력을 읽어옴</p>
</li>
<li><p><code>fs.readFileSync('/dev/stdin')</code>는 표준 입력(콘솔, 터미널에서 입력되는 데이터)을 동기적으로 읽어옴</p>
</li>
</ul>
</li>
<li><p>parseInt 함수</p>
<hr />
<pre><code class="language-jsx"> var a = parseInt(num[0]);
 var b = parseInt(num[1]);</code></pre>
<hr />
<ul>
<li><code>parseInt(num[0])</code> : 문자열 → 정수</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>파일 시스템 모듈<ul>
<li><code>fs.readFileSync()</code> : 코드 간결성, 간단한 사용 시</li>
<li><code>readline()</code> : 유연하고 복잡한 입력 처리 필요 시</li>
</ul>
</li>
<li><code>parseInt()</code> 문자열 → 정수</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const fs = require('fs');
const num = fs.readFileSync('/dev/stdin').toString().split(' ');
const a = parseInt(num[0]);
const b = parseInt(num[1]);
console.log(a+b);</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://velog.io/@bami/Node.js-%ED%8C%8C%EC%9D%BC-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EB%AA%A8%EB%93%88">[Node.js] 파일 시스템 모듈</a></p>