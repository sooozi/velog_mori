<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>정수 <code>l</code>과 <code>r</code>이 주어졌을 때, <code>l</code> 이상 <code>r</code>이하의 정수 중에서 숫자 &quot;0&quot;과 &quot;5&quot;로만 이루어진 모든 정수를 오름차순으로 저장한 배열을 return 하는 solution 함수를 완성해 주세요.</p>
<p>만약 그러한 정수가 없다면, -1이 담긴 배열을 return 합니다.</p>
<h2 id="입출력">입출력</h2>
<table>
<thead>
<tr>
<th>l</th>
<th>r</th>
<th>result</th>
</tr>
</thead>
<tbody><tr>
<td>5</td>
<td>555</td>
<td>[5, 50, 55, 500, 505, 550, 555]</td>
</tr>
<tr>
<td>10</td>
<td>20</td>
<td>[-1]</td>
</tr>
</tbody></table>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-1">예제 1</h2>
<pre><code>5 이상 555 이하의 0과 5로만 이루어진 정수는 작은 수부터 5, 50, 55, 500, 505, 550, 555가 있습니다. 따라서 [5, 50, 55, 500, 505, 550, 555]를 return 합니다.</code></pre><h2 id="예제-2">예제 2</h2>
<pre><code>10 이상 20 이하이면서 0과 5로만 이루어진 정수는 없습니다. 따라서 [-1]을 return 합니다.</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<ol>
<li>l이상 r이하의 정수 찾기
⇒ 루프로 돌려서 해당되는 정수만 노출<ol start="2">
<li>해당 정수 중 숫자0과 5로만 이루어진 정수로 필터링
⇒ if문으로 조건 걸기</li>
<li>해당 숫자 배열로 넣기</li>
<li>!조건, 이런 정수가 없다면 -1이 담긴 배열 retrun</li>
</ol>
</li>
</ol>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>문자열 변경</p>
<hr />
<pre><code class="language-jsx"> let numStr = i.**toString()**;</code></pre>
<ul>
<li>각 자릿수를 쉽게 검사 가능하기 때문!</li>
</ul>
</li>
<li><p>every 함수</p>
<hr />
<pre><code class="language-jsx"> if (numStr.split('').**every(str =&gt; str === '0' || str === '5')**) {
             answer.push(i);
         } else if(answer.length === 0) {
             return [-1];
         }</code></pre>
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
<ul>
<li><p>내 코드</p>
<pre><code class="language-jsx">  function solution(l, r) {
      let answer = [];

      for (let i = l; i &lt;= r; i++) {
          let numStr = i.toString(); // 정수 -&gt; 문자열

          // 모든 문자가 '0' 또는 '5'인지 확인
          if (numStr.split('').every(char =&gt; char === '0' || char === '5')) {
              answer.push(i);
          }
      }

      // 조건을 만족하는 정수가 없으면 [-1] 반환
      //for 루프 안에 위치하는 경우 for 루프 종료 전 정수가 없다고 판단 =&gt; 오류 발생
      if (answer.length === 0) {
          return [-1];
      }

      return answer;
  }</code></pre>
</li>
<li><p>남 코드</p>
<pre><code class="language-jsx">  // 숫자 5로 현혹시켰지만 사실 이건 이진수 문제임.

  //1부터 시작하여 모든 정수를 이진수로 변환 -&gt; 다시 숫자로 변환 -&gt; 결과를 5배하여 생성
  **function* gen50() { //제네레이터 함수**
      let i = 1;

      while(true) { //무한루프
              //Number(i).toString(2) : 이진수 문자열로 변환
              //yield Number(Number(i).toString(2)) * 5 : 해당 값을 5배하여 생성
          yield Number(Number(i).toString(2)) * 5;
          i++;
      }
  }
  function solution(l, r) {
      const n = gen50();
      let a = 0;
      const arr = [];

          //범위 시작값 찾기 : 루프는 a가 1보다 작을 때까지 제너레이터로부터 값을 계속 생성하여 a에 저장
          //1보다 작은 값을 건너뛰고 1 이상인 값부터 시작
      while(a &lt; l) { a = n.next().value; }

      //범위 내 값 수집 : 루프는 a가 r이하일 때까지 제너레이터로부터 값을 생성하고 arr 배열에 추
      while(a &lt;= r) { arr.push(a); a = n.next().value; }

      return arr.length ? arr : [-1];
  }</code></pre>
<p>  문제에 대해 규칙(특정한 패턴)을 파악하여 문제 해결!</p>
<p>  하지만 다 이해하지 못한 내 자신 반성해…😰</p>
</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://jerryjerryjerry.tistory.com/200">[JavaScript] 자바스크립트 some()과 every()</a></p>
<p><a href="https://ji-musclecode.tistory.com/56">JS - generator 함수와 yield</a></p>