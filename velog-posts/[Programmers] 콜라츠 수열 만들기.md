<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>모든 자연수 <code>x</code>에 대해서 현재 값이 <code>x</code>이면 <code>x</code>가 짝수일 때는 2로 나누고, <code>x</code>가 홀수일 때는 <code>3 * x + 1</code>로 바꾸는 계산을 계속해서 반복하면 언젠가는 반드시 <code>x</code>가 1이 되는지 묻는 문제를 <strong>콜라츠 문제</strong>라고 부릅니다.</p>
<p>그리고 위 과정에서 거쳐간 모든 수를 기록한 수열을 <strong>콜라츠 수열</strong>이라고 부릅니다.</p>
<p>계산 결과 1,000 보다 작거나 같은 수에 대해서는 전부 언젠가 1에 도달한다는 것이 알려져 있습니다.</p>
<p>임의의 1,000 보다 작거나 같은 양의 정수 <code>n</code>이 주어질 때 초기값이 <code>n</code>인 콜라츠 수열을 return 하는 solution 함수를 완성해 주세요.</p>
<h2 id="입출력">입출력</h2>
<table>
<thead>
<tr>
<th>n</th>
<th>result</th>
</tr>
</thead>
<tbody><tr>
<td>10</td>
<td>[10, 5, 16, 8, 4, 2, 1]</td>
</tr>
</tbody></table>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-1">예제 1</h2>
<table>
<thead>
<tr>
<th>연산 횟수</th>
<th>x</th>
<th>홀짝 여부</th>
</tr>
</thead>
<tbody><tr>
<td>0</td>
<td>10</td>
<td>짝수</td>
</tr>
<tr>
<td>1</td>
<td>5</td>
<td>홀수</td>
</tr>
<tr>
<td>2</td>
<td>16</td>
<td>짝수</td>
</tr>
<tr>
<td>3</td>
<td>8</td>
<td>짝수</td>
</tr>
<tr>
<td>4</td>
<td>4</td>
<td>짝수</td>
</tr>
<tr>
<td>5</td>
<td>2</td>
<td>짝수</td>
</tr>
<tr>
<td>6</td>
<td>1</td>
<td>홀수</td>
</tr>
</tbody></table>
<pre><code>따라서 [10, 5, 16, 8, 4, 2, 1]을 return 합니다.</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>콜라츠 수열</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>while을 사용하는 이유</p>
<hr />
<pre><code class="language-jsx"> while (current !== 1) {
   // current가 1이 아닌 동안, 즉 1이 될 때까지 계속 반복
 }</code></pre>
<ul>
<li>다른 반복문(for, do…while)도 가능하지만 while문은 조건에 따라 반복을 수행하는 상황에서 매우 직관적이고 간단하게 코드 작성이 가능하다.</li>
<li><strong>while문</strong> : 반복 횟수가 불확실할 때 / 반복이 특정 조건에 의해 언제 끝날지 모를 때 사용</li>
<li><strong>for문</strong> : 반복 횟수가 명확하거나 반복 회수를 알고 있는 경우 사용</li>
</ul>
</li>
<li><p>콜라츠 수열 마지막은 무조건 1</p>
<hr />
<pre><code class="language-jsx"> result.push(1);</code></pre>
<ul>
<li>반복문이 끝나면 1 꼭 넣어주기!</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>콜라츠 수열은 종료 조건이 명확하기 때문에 <strong>while 반목문을 사용</strong>하자!</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<ul>
<li><p>내 코드</p>
<pre><code class="language-jsx">  function solution(n) {
      const result = [];
      while(n !== 1) {
          result.push(n);
          if(n%2 === 0) {
              n = n/2;
          } else {
              n = 3*n+1
          }
      }
      result.push(1);
      return result;
  }</code></pre>
</li>
<li><p>남 코드</p>
<pre><code class="language-jsx">  function solution(n, arr = []) { 
      arr.push(n) //현재 숫자n을 배열에 추가 =&gt; 이후 재귀 호출이 진행되며 다음 숫자들이 차례대로 배열에 추가
      if (n === 1) return arr  //종료 조건
      if (n % 2 === 0) return solution(n / 2, arr)  //재귀호출: 짝수처리 =&gt; 짝수인지 확인 후 다시 solution 호출
      return solution(3 * n + 1, arr) //재귀호출: 홀수처리
  }</code></pre>
<ul>
<li>재귀함수 :  자기 자신을 호출하는 함수 / 장점 : 반복적인 계산을 간결하게 표현 가능</li>
<li>각 재귀호출마다 숫자가 갱신되어 콜라츠 수열이 완성</li>
</ul>
</li>
</ul>
<p><br /><br /><br />처음으로 만난 콜라츠 문제! 콜라츠에 대해 잘 기억해두자 😀</p>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://ko.javascript.info/while-for">while과 for 반복문</a></p>
<p><a href="https://ko.javascript.info/recursion">재귀와 스택</a></p>