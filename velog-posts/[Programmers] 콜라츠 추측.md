<p>문제 링크
<a href="https://school.programmers.co.kr/learn/courses/30/lessons/12943">https://school.programmers.co.kr/learn/courses/30/lessons/12943</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>1937년 Collatz란 사람에 의해 제기된 이 추측은, 주어진 수가 1이 될 때까지 다음 작업을 반복하면, 모든 수를 1로 만들 수 있다는 추측입니다. 작업은 다음과 같습니다.</p>
<p><code>1-1. 입력된 수가 짝수라면 2로 나눕니다. 
1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더합니다. 
2. 결과로 나온 수에 같은 작업을 1이 될 때까지 반복합니다.</code></p>
<p>예를 들어, 주어진 수가 6이라면 6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1 이 되어 총 8번 만에 1이 됩니다. 위 작업을 몇 번이나 반복해야 하는지 반환하는 함수, solution을 완성해 주세요. 단, 주어진 수가 1인 경우에는 0을, 작업을 500번 반복할 때까지 1이 되지 않는다면 –1을 반환해 주세요.</p>
<h3 id="제한-사항">제한 사항</h3>
<ul>
<li>입력된 수, <code>num</code>은 1 이상 8,000,000 미만인 정수입니다.</li>
</ul>
<h2 id="입출력">입출력</h2>
<h2 id="입출력-예-설명">입출력 예 설명</h2>
<p>입출력 예 #1</p>
<p> 6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1 이 되어 총 8번 만에 1이 됩니다. </p>
<p>입출력 예 #2</p>
<p>16 → 8 → 4 → 2 → 1 이 되어 총 4번 만에 1이 됩니다.</p>
<p>입출력 예 #3</p>
<p>626331은 500번을 시도해도 1이 되지 못하므로 -1을 리턴해야 합니다.</p>
<hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>콜라츠 추측</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ol>
<li><p>재귀함수</p>
<hr />
<pre><code class="language-jsx"> function recursiveFunction(parameters) {
     // 기본 사례: 재귀 호출을 종료하는 조건
     if (baseCondition) {
         return baseResult;
     }

     // 재귀 사례: 문제를 단순화하고 자신을 호출
     return recursiveFunction(simplifiedParameters);
 }</code></pre>
<ul>
<li>함수 내부에서 ‘자기 자신을 호출’하는 함수</li>
<li>이를 통해 함수가 자신을 반복적으로 호출하며 원하는 결과 도출 가능</li>
<li>단, 재귀함수 사용 시 함수 호출이 계속되며 쌓이기 때문에 호출 스택이 많아저 성능 저하 우려</li>
<li><strong>재귀함수 작성 시 무한루프에 빠지지 않도록 종료 조건을 명확하게 설정할 것!</strong></li>
</ul>
</li>
</ol>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li>콜라츠 추측 문제 풀이 시 재귀함수, while 반목문을 사용</li>
<li>조금 더 간결하고 직관적인 코드를 짤 수 있도록 노력하자!</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<ul>
<li><p>내 코드</p>
<pre><code class="language-jsx">  function solution(num, arr = [], count = 0) {
      if (num === 1) {
          return count === 0 ? 0 : arr.length;
      }
      if (count &gt;= 500) {
          return -1;
      }
      arr.push(num);     
      if (num % 2 === 0) {
          return solution(num / 2, arr, count + 1);
      } else {
          return solution(3 * num + 1, arr, count + 1);
      }
  }</code></pre>
</li>
<li><p>남 코드</p>
<pre><code class="language-jsx">  // 문제가 개편되었습니다. 이로 인해 함수 구성이나 테스트케이스가 변경되어, 과거의 코드는 동작하지 않을 수 있습니다.
  // 새로운 함수 구성을 적용하려면 [코드 초기화] 버튼을 누르세요. 단, [코드 초기화] 버튼을 누르면 작성 중인 코드는 사라집니다.
  function collatz(num) {
      var answer = 0;
      while(num !=1 &amp;&amp; answer !=500){
          num%2==0 ? num = num/2 : num = num*3 +1;
      answer++;
    }
      return num == 1 ? answer : -1;
  }
  // 아래는 테스트로 출력해 보기 위한 코드입니다.
  console.log( collatz(6) );</code></pre>
</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://adjh54.tistory.com/194">[Java/알고리즘] 재귀 함수(Recursion Function) 이해하기</a></p>