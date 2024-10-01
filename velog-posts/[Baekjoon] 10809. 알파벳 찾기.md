<p>문제 링크
<a href="https://www.acmicpc.net/problem/10809">https://www.acmicpc.net/problem/10809</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>알파벳 소문자로만 이루어진 단어 S가 주어진다. 각각의 알파벳에 대해서, 단어에 포함되어 있는 경우에는 처음 등장하는 위치를, 포함되어 있지 않은 경우에는 -1을 출력하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 단어 S가 주어진다. 단어의 길이는 100을 넘지 않으며, 알파벳 소문자로만 이루어져 있다.</p>
<h2 id="출력">출력</h2>
<p>각각의 알파벳에 대해서, a가 처음 등장하는 위치, b가 처음 등장하는 위치, ... z가 처음 등장하는 위치를 공백으로 구분해서 출력한다.</p>
<p>만약, 어떤 알파벳이 단어에 포함되어 있지 않다면 -1을 출력한다. 단어의 첫 번째 글자는 0번째 위치이고, 두 번째 글자는 1번째 위치이다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>baekjoon</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>1 0 -1 -1 2 -1 -1 -1 -1 4 3 -1 -1 7 5 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1</code></pre><h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 구현 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>각 알파벳에 맞게 -1 초기화 세팅 → 문자열 S를 한글자씩 순회하며 첫등장 위치 기록</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">const S = require('fs').readFileSync('/dev/stdin').toString().trim()

// 알파벳 위치를 저장할 배열 (-1로 초기화)
const alphabet = Array(26).fill(-1);

// 각 알파벳의 첫 등장 위치 찾기
for (let i = 0; i &lt; S.length; i++) {
    const char = S[i];
    const charIndex = char.charCodeAt(0) - 'a'.charCodeAt(0); // 'a'를 기준으로 인덱스 계산
    if (alphabet[charIndex] === -1) { // 아직 등장하지 않았다면
        alphabet[charIndex] = i; // 등장 위치 저장
    }
}

// 결과 출력
console.log(alphabet.join(' '));</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li><p><code>.charCodeAt(0)</code></p>
<hr />
<p> : 자바스크립트 문자열 메서드 / 특정 인덱스에 있는 문자의 Unicode(또는 ASCII) 값을 반환</p>
<ul>
<li><p>문법</p>
<pre><code class="language-jsx">  string.charCodeAt(index)</code></pre>
</li>
<li><p>예시</p>
<pre><code class="language-jsx">  const str = &quot;hello&quot;;
  console.log(str.charCodeAt(0)); // 'h'의 Unicode 값인 104 출력
  console.log(str.charCodeAt(1)); // 'e'의 Unicode 값인 101 출력
  console.log(str.charCodeAt(4)); // 'o'의 Unicode 값인 111 출력</code></pre>
</li>
<li><p><strong>인덱스 계산</strong></p>
<ul>
<li><code>char.charCodeAt(0) - 'a'.charCodeAt(0)</code>은 <code>char</code>의 ASCII 코드에서 <code>a</code>의 ASCII 코드를 빼서 <code>char</code>가 알파벳 순서에서 몇 번째인지 나타내는 인덱스를 계산</li>
<li>예를 들어:<ul>
<li><code>char</code>가 <code>'a'</code>일 때: <code>97 - 97 = 0</code> (인덱스 0)</li>
<li><code>char</code>가 <code>'b'</code>일 때: <code>98 - 97 = 1</code> (인덱스 1)</li>
<li><code>char</code>가 <code>'z'</code>일 때: <code>122 - 97 = 25</code> (인덱스 25)</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li><code>.charCodeAt(0)</code>는 자바스크립트의 문자열 메서드로, 특정 인덱스에 있는 문자의 Unicode(또는 ASCII) 값을 반환</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://webclub.tistory.com/329">charAt() &amp; charCodeAt()</a></p>