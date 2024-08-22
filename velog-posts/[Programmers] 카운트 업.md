<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>정수 <code>start_num</code>와 <code>end_num</code>가 주어질 때, <code>start_num</code>부터 <code>end_num</code>까지의 숫자를 차례로 담은 리스트를 return하도록 solution 함수를 완성해주세요.</p>
<h2 id="입출력">입출력</h2>
<table>
<thead>
<tr>
<th>start_num</th>
<th>end_num</th>
<th>result</th>
</tr>
</thead>
<tbody><tr>
<td>3</td>
<td>10</td>
<td>[3, 4, 5, 6, 7, 8, 9, 10]</td>
</tr>
</tbody></table>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-1">예제 1</h2>
<pre><code>3부터 10까지의 숫자들을 담은 리스트 [3, 4, 5, 6, 7, 8, 9, 10]를 return합니다.</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<ol>
<li>l이상 r이하의 정수 찾기
⇒ 루프로 돌려서 해당되는 정수만 노출</li>
</ol>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>제공된 숫자부터 숫자까지 노출</p>
<hr />
<pre><code class="language-jsx"> function solution(start_num, end_num) {
     let answer = [];
     for(let i = start_num; i &lt;= end_num; i++) {
         answer.push(i);
     }
     return answer;
 }</code></pre>
<ul>
<li>루프로 해당 숫자 모두 배열에 넣기</li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>for 루프로 해당 숫자 모두 배열에 넣기</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<ul>
<li><p>내 코드</p>
<pre><code class="language-jsx">  function solution(start_num, end_num) {
      let answer = [];
      for(let i = start_num; i &lt;= end_num; i++) {
          answer.push(i);
      }
      return answer;
  }</code></pre>
</li>
<li><p>남 코드</p>
<pre><code class="language-jsx">  없음...ㅎ.ㅎ</code></pre>
<p>  지난번과 동일한 코드 사용이 가능해 주워먹은 문제🥰</p>
</li>
</ul>