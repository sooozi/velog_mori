<p>문제 링크
<a href="https://www.acmicpc.net/problem/10926">https://www.acmicpc.net/problem/10926</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>준하는 사이트에 회원가입을 하다가 joonas라는 아이디가 이미 존재하는 것을 보고 놀랐다. 준하는 놀람을 ??!로 표현한다. 준하가 가입하려고 하는 사이트에 이미 존재하는 아이디가 주어졌을 때, 놀람을 표현하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 준하가 가입하려고 하는 사이트에 이미 존재하는 아이디가 주어진다. 아이디는 알파벳 소문자로만 이루어져 있으며, 길이는 50자를 넘지 않는다.</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 준하의 놀람을 출력한다. 놀람은 아이디 뒤에 ??!를 붙여서 나타낸다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>joonas</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>joonas??!</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 입력값 + ??! → 출력</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>readFileSync</p>
<hr />
<pre><code class="language-jsx"> const input = require('fs').readFileSync('/dev/stdin').toString().trim();</code></pre>
<ul>
<li><strong>readFileSync</strong> : 파일을 동기적으로 읽어오는 함수<ul>
<li>동기적 : 파일을 다 읽을 때까지 코드가 멈춰 있다는 뜻, 모든 데이터를 다 읽고 난 후 다음 코드로 넘어간다.</li>
</ul>
</li>
<li>readFileSync로 읽어온 데이터는 컴퓨터가 이해할 수 있는 <strong>바이너리 데이터</strong>이다.</li>
</ul>
</li>
<li><p>.toString()</p>
<hr />
<pre><code class="language-jsx"> const input = require('fs').readFileSync('/dev/stdin').toString().trim();</code></pre>
<ul>
<li>바이너리 데이터를 사람이 읽을 수 있는 <strong>문자열</strong>로 바꿔준다.</li>
</ul>
</li>
<li><p>.trim()</p>
<hr />
<pre><code class="language-jsx"> const input = require('fs').readFileSync('/dev/stdin').toString().trim();</code></pre>
<hr />
<ul>
<li><strong>문자열 앞뒤 공백, 줄바꿈을 제거</strong>한다.</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>readFileSync : 컴퓨터가 읽을 수 있는 바이너리 데이터를 동기적으로 읽어오는 함수</li>
<li>.toString() : 데이터타입 → 문자열</li>
<li>.trim() : 문자열 앞뒤 공백, 줄바꿈 제거</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const input = require('fs').readFileSync('/dev/stdin').toString().trim();
console.log(input + '??!');</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://velog.io/@dalkong/Node.Js-%ED%8C%8C%EC%9D%BC-%EC%9D%BD%EA%B8%B0-readFile-readFileSync-%EC%B0%A8%EC%9D%B4">[Node.Js] 파일 읽기 : readFile, readFileSync 차이</a></p>
<p><a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/toString">Object.prototype.toString() - JavaScript | MDN</a></p>
<p><a href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/trim">String.prototype.trim() - JavaScript | MDN</a></p>