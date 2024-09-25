<p>문제 링크
<a href="https://www.acmicpc.net/problem/9498">https://www.acmicpc.net/problem/9498</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>시험 점수를 입력받아 90 ~ 100점은 A, 80 ~ 89점은 B, 70 ~ 79점은 C, 60 ~ 69점은 D, 나머지 점수는 F를 출력하는 프로그램을 작성하시오.</p>
<h2 id="입력">입력</h2>
<p>첫째 줄에 시험 점수가 주어진다. 시험 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.</p>
<h2 id="출력">출력</h2>
<p>시험 성적을 출력한다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h3 id="예제-입력">예제 입력</h3>
<pre><code>100</code></pre><h3 id="예제-출력">예제 출력</h3>
<pre><code>A</code></pre><h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 구현 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>if문을 사용해 점수 조건을 추가하여 등급으로 나눈다.</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">const num = parseInt(require('fs').readFileSync('/dev/stdin').toString());

if (num &gt;= 90) {
    console.log('A');
} else if (num &gt;= 80) {
    console.log('B');
} else if (num &gt;= 70) {
    console.log('C');
} else if (num &gt;= 60) {
    console.log('D');
} else {
    console.log('F');
}</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li><p>더 좋은 답변 찾아보기</p>
<hr />
<pre><code class="language-jsx"> const num = parseInt(require('fs').readFileSync('/dev/stdin').toString());

 switch (true) {
     case (num &gt;= 90):
         console.log('A');
         break;
     case (num &gt;= 80):
         console.log('B');
         break;
     case (num &gt;= 70):
         console.log('C');
         break;
     case (num &gt;= 60):
         console.log('D');
         break;
     default:
         console.log('F');
 }</code></pre>
<p> switch문 : 가독성이 좋아짐 / 조건이 명확하게 구분</p>
<p> switch문은 특정 조건에 대한 여러 범위를 처리하는 데 유용하다!</p>
</li>
</ol>
<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li>가독성이 좋은 코드를 짜보자!</li>
</ul>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://ko.javascript.info/switch">switch문</a></p>