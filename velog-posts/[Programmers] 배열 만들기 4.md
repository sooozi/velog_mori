<p>문제 링크
<a href="https://school.programmers.co.kr/learn/courses/30/lessons/181918">https://school.programmers.co.kr/learn/courses/30/lessons/181918</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>정수 배열 <code>arr</code>가 주어집니다. <code>arr</code>를 이용해 새로운 배열 <code>stk</code>를 만드려고 합니다.</p>
<p>변수 <code>i</code>를 만들어 초기값을 0으로 설정한 후 <code>i</code>가 <code>arr</code>의 길이보다 작으면 다음 작업을 반복합니다.</p>
<ul>
<li>만약 <code>stk</code>가 빈 배열이라면 <code>arr[i]</code>를 <code>stk</code>에 추가하고 <code>i</code>에 1을 더합니다.</li>
<li><code>stk</code>에 원소가 있고, <code>stk</code>의 마지막 원소가 <code>arr[i]</code>보다 작으면 <code>arr[i]</code>를 <code>stk</code>의 뒤에 추가하고 <code>i</code>에 1을 더합니다.</li>
<li><code>stk</code>에 원소가 있는데 <code>stk</code>의 마지막 원소가 <code>arr[i]</code>보다 크거나 같으면 <code>stk</code>의 마지막 원소를 <code>stk</code>에서 제거합니다.</li>
</ul>
<p>위 작업을 마친 후 만들어진 <code>stk</code>를 return 하는 solution 함수를 완성해 주세요.</p>
<h2 id="제한사항">제한사항</h2>
<ul>
<li>1 ≤ <code>arr</code>의 길이 ≤ 100,000<ul>
<li>1 ≤ <code>arr</code>의 원소 ≤ 100,000</li>
</ul>
</li>
</ul>
<h2 id="입출력-예">입출력 예</h2>
<table>
<thead>
<tr>
<th>arr</th>
<th>result</th>
</tr>
</thead>
<tbody><tr>
<td>[1, 4, 2, 5, 3]</td>
<td>[1, 2, 3]</td>
</tr>
</tbody></table>
<h2 id="입출력-예-설명">입출력 예 설명</h2>
<p>입출력 예 #1</p>
<ul>
<li>각 작업을 마친 후에 배열의 변화를 나타내면 다음 표와 같습니다.</li>
</ul>
<table>
<thead>
<tr>
<th>i</th>
<th>arr[i]</th>
<th>stk</th>
</tr>
</thead>
<tbody><tr>
<td>0</td>
<td>1</td>
<td>[]</td>
</tr>
<tr>
<td>1</td>
<td>4</td>
<td>[1]</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>[1, 4]</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>[1]</td>
</tr>
<tr>
<td>3</td>
<td>5</td>
<td>[1, 2]</td>
</tr>
<tr>
<td>4</td>
<td>3</td>
<td>[1, 2, 5]</td>
</tr>
<tr>
<td>4</td>
<td>3</td>
<td>[1, 2]</td>
</tr>
<tr>
<td>-</td>
<td>-</td>
<td>[1, 2, 3]</td>
</tr>
<tr>
<td>- 따라서 [1, 2, 3]을 return 합니다.</td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h1 id="approach-📝">Approach 📝</h1>
<hr />
<h2 id="알고리즘">알고리즘</h2>
<blockquote>
<p>입력 → 연산 → 출력</p>
</blockquote>
<h2 id="문제-풀기-전-생각해보기-🤷♀️">문제 풀기 전 생각해보기 🤷‍♀️</h2>
<p>for문 안에 각각의 기준을 if문으로 넣는다.</p>
<h2 id="my-solution-💡">My Solution 💡</h2>
<pre><code class="language-jsx">function solution(arr) {
    let stk = [];
    for(let i = 0; i &lt; arr.length; i++){
        if(stk.length === 0) {
            stk.push(arr[i]);
        } else if(stk[stk.length - 1] &lt; arr[i]) {
            stk.push(arr[i]);
        } else if(stk[stk.length - 1] &gt;= arr[i]){
            stk.pop();
        }
    }
    return stk;
}</code></pre>
<p>ㅠㅠ</p>
<h2 id="other-solution-💡">Other Solution 💡</h2>
<pre><code class="language-jsx">function solution(arr) {
    var stk = [];
    for(let i =0;i&lt;arr.length;){
        if(stk.length === 0){
            stk.push(arr[i++]);
        }
        else if(stk[stk.length-1] &lt; arr[i]){
            stk.push(arr[i++]);
        }
        else if(stk[stk.length-1] &gt;= arr[i]){
            stk.pop();
        }
    }
    return stk;
}</code></pre>
<pre><code class="language-jsx">function solution(arr) {
    let stk = [];
    for (let i = 0; i &lt; arr.length; i++) {
        // 스택의 마지막 요소가 현재 요소보다 크거나 같을 때 제거
        while (stk.length &gt; 0 &amp;&amp; stk[stk.length - 1] &gt;= arr[i]) {
            stk.pop();
        }
        // 현재 요소를 스택에 추가
        stk.push(arr[i]);
    }
    return stk;
}</code></pre>
<h2 id="알게-된-것">알게 된 것</h2>
<ol>
<li><p>pop, slice, push</p>
<hr />
<ul>
<li><p>pop()</p>
<p>  배열 마지막 요소 제거 후 해당 요소 반환</p>
<pre><code class="language-jsx">  let arr = [1, 2, 3];
  let lastElement = arr.pop();
  console.log(lastElement); // 3
  console.log(arr); // [1, 2]</code></pre>
</li>
<li><p>slice()</p>
<p>  배열 일부 복사 후 새로운 배열 반환</p>
<ul>
<li><p><strong>문법</strong></p>
<pre><code>  array.slice(start, end)</code></pre><ul>
<li><code>start</code>: 복사할 시작 인덱스 (포함)</li>
<li><code>end</code>: 복사할 종료 인덱스 (포함되지 않음)</li>
</ul>
<pre><code class="language-jsx">let arr = [1, 2, 3, 4, 5];
let newArr = arr.slice(1, 4);
console.log(newArr); // [2, 3, 4]
console.log(arr); // [1, 2, 3, 4, 5] (원본 배열은 변경되지 않음)</code></pre>
</li>
</ul>
</li>
<li><p>push()</p>
<p>  배열 끝에 하나 이상의 요소 추가, 배열의 새로운 길이 반환</p>
<ul>
<li><p><strong>문법</strong></p>
<pre><code>  array.push(element1, ..., elementN)</code></pre><ul>
<li><code>element1, ..., elementN</code>: 추가할 요소들</li>
</ul>
<pre><code class="language-jsx">let arr = [1, 2, 3];
let newLength = arr.push(4, 5);
console.log(newLength); // 5 (새로운 배열의 길이)
console.log(arr); // [1, 2, 3, 4, 5]</code></pre>
</li>
</ul>
</li>
</ul>
</li>
</ol>
<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li>배열 메서드<ul>
<li><strong><code>pop()</code></strong>: 배열의 마지막 요소를 제거하고 반환</li>
<li><strong><code>slice()</code></strong>: 배열의 일부분을 복사하여 새로운 배열로 반환 (원본 배열은 변경되지 않음).</li>
<li><strong><code>push()</code></strong>: 배열의 끝에 요소를 추가하고 새로운 배열의 길이를 반환</li>
</ul>
</li>
</ul>
<h2 id=""></h2>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://velog.io/@hovelopin/JS-%EB%B0%B0%EC%97%B4-%EB%82%B4%EC%9E%A5%ED%95%A8%EC%88%98-pop-push-shift-unshift-splice-slice-indexOf-findIndex">JS 배열 내장함수 (pop , push ,shift , unshift , splice , slice , indexOf , findIndex)</a></p>