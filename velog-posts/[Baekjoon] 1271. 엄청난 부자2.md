<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>갑부 최백준 조교는 동전을 최소로 바꾸는데 성공했으나 김재홍 조교가 그 돈을 발견해서 최백준 조교에게 그 돈을 나누자고 따진다.</p>
<p>그 사실이 전 우주로 알려지자 우주에 있던 많은 생명체들이 자신들에게 돈을 분배해 달라고 당장 달려오기 시작했다.</p>
<p>프로토스 중앙 우주 정부의 정책인, ‘모든 지적 생명체는 동등하다’라는 규칙에 입각해서 돈을 똑같이 분배하고자 한다.</p>
<p>한 생명체에게 얼마씩 돈을 줄 수 있는가?</p>
<p>또, 생명체들에게 동일하게 분배한 후 남는 돈은 얼마인가?</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에는 최백준 조교가 가진 돈 n과 돈을 받으러 온 생명체의 수 m이 주어진다. (1 ≤ m ≤ n ≤ 101000, m과 n은 10진수 정수)</p>
<h2 id="출력">출력</h2>
<p>첫째 줄에 생명체 하나에게 돌아가는 돈의 양을 출력한다. 그리고 두 번째 줄에는 1원씩 분배할 수 없는 남는 돈을 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>1000 100</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>10
0</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 연산 → 출력(몫, 나머지)</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>이전과 동일한 방법 사용 시 틀림!</p>
<hr />
<pre><code class="language-jsx"> const fs = require('fs');
 const [a, b] = fs.readFileSync('/dev/stdin').toString().split(' ').map(Number);
 const moneyPerEntity = Math.floor(a / b);
 const remainingMoney = a % b;

 console.log(moneyPerEntity);
 console.log(remainingMoney);</code></pre>
<ul>
<li>Number로 접근<ul>
<li>Number 타입은 64비트 부동소수점 수를 사용, 사용 가능한 범위를 초과하는 큰 숫자 처리 시 오차가 발생할 수 있어 틀림!!!</li>
</ul>
</li>
<li><strong>문제 제목에 씌여있듯 백준이는 증말 어마어어어어어어어마한 부자였던 것이였다…😰</strong></li>
</ul>
</li>
<li><p>BigInt : 매우 큰 정수를 정확하게 표현할 수 있는 데이터 타입!</p>
<hr />
<pre><code class="language-jsx"> const fs = require('fs');
 const num = fs.readFileSync('/dev/stdin').toString().split(' ');

 //배열 요소를 BigInt로 변환
 const money = BigInt(num.shift()); // 배열 첫 번째 요소 제거 후 반환
 const People = BigInt(num.shift());

 //이 방법도 맞음!
 const money = BigInt(num[0]);
 const People = BigInt(num[1]);

 console.log((money / People).toString());
 console.log((money % People).toString());</code></pre>
<ul>
<li><code>BigInt</code>는 제한 없이 아주 큰 숫자도 정확하게 처리할 수 있기 때문에, 입력 값이 <code>Number</code>의 범위를 초과하는 경우에도 정확한 결과를 제공</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li><code>BigInt</code> : 정확한 큰 정수 표현</li>
<li>갑부는 돈이 생각보다 돈이 정말 많다…😰</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const fs = require('fs');
const num = fs.readFileSync('/dev/stdin').toString().split(' ');
const money = BigInt(num.shift());
const People = BigInt(num.shift());

console.log((money / People).toString());
console.log((money % People).toString());</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://hyemgu.tistory.com/372">[백준/node.js] 1271 엄청난 부자2</a></p>