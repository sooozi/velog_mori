<p>코테 문제풀이 중 만난 배열 중복 제거 방법!
배열과 관련된 문제들이 많았던 것 같아 배열 중복 제거부터 제대로 뽀개보자고! 😀😀😀
<br /><br /></p>
<blockquote>
<h2 id="배열-중복-제거">배열 중복 제거</h2>
</blockquote>
<h2 id="🟨set">🟨set</h2>
<ol>
<li><p><code>Set</code></p>
<ul>
<li><p>개념<br />: 중복되지 않는 값들의 집합을 나타내는 객체</p>
<ul>
<li><p>가장 빠르고 간단한 방법, 배열이 크거나 중복된 값이 많을  때 유리 / 중복된 값 제거 &amp; 정렬 순서 유지할 때 적합</p>
<pre><code class="language-jsx">let setArr = [...new Set(arr)];</code></pre>
</li>
<li><p>단점 : 동일한 내용의 객체라도 서로 다른 메모리 주소를 가지면(객체의 참조 값만 비교) 서로 다르다고 간주하여 완전한 중복 제거가 어려울 수 있음 ⇒ <code>JSON.stringify</code>를 사용해서 객체를 문자열로 변환한 후 중복을 제거</p>
<pre><code class="language-jsx">let obj1 = { name: &quot;John&quot; };
let obj2 = { name: &quot;John&quot; };
let arr = [obj1, obj2];

let uniqueArr = [...new Set(arr)];
console.log(uniqueArr); //[{ name: &quot;John&quot; }, { name: &quot;John&quot; }]</code></pre>
</li>
<li><p><em>// 객체를 문자열로 변환하여 중복 제거*</em>
let uniqueArr = [...new Map(arr.map(obj =&gt; [JSON.stringify(obj), obj])).values()];</p>
<p>console.log(uniqueArr); // [{ name: &quot;John&quot; }]</p>
<pre><code></code></pre></li>
</ul>
</li>
<li><p>예시</p>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5];   // 중복된 값이 있는 배열
  **let setArr = [...new Set(arr)];    // 중복을 제거하고 배열로 변환**
  console.log(setArr);               // 출력: [1, 2, 3, 4, 5]</code></pre>
<ul>
<li>코드 설명<ul>
<li>new Set(arr) ⇒ 중복값 제거<ul>
<li><code>Set</code> : 중복을 허용하지 않는 데이터 구조, 객체에서 사용!</li>
<li>예를 들어, <code>arr</code>가 <code>[1, 2, 2, 3, 4, 4, 5]</code>(배열)라면, <code>new Set(arr)</code>는 <code>Set { 1, 2, 3, 4, 5 }</code>(객체)라는 중복 없는 값들로 구성된 <code>Set</code>을 반환</li>
</ul>
</li>
<li><code>...</code> (전개 연산자, 스프레드 문) ⇒ 객체, 배열을 분해<ul>
<li>예를 들어, <code>Set</code>이 <code>Set { 1, 2, 3, 4, 5 }</code>라면, <code>...new Set(arr)</code>는 <code>1, 2, 3, 4, 5</code>로 분해</li>
</ul>
</li>
<li><code>[...]</code> (배열 리터럴) ⇒ 배열로 생성<ul>
<li>내부에 있는 요소들을 배열로 제작<h2 id="🟨filter와-indexof">🟨<code>filter</code>와 <code>indexOf</code></h2>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li><p><code>filter</code>와 <code>indexOf</code></p>
<ul>
<li><p><code>filter</code>와 <code>indexOf</code> 개념</p>
<ul>
<li><p><code>filter</code>와 <code>indexOf</code></p>
<ul>
<li>배열의 순서를 유지하며 중복  제거 가능 / 값이 처음 등장한 위치만 남기고 중복 제거</li>
<li>단점 : 성능이 <code>set</code>에 비해 떨어지고 배열이 클  경우 속도 저하</li>
</ul>
</li>
<li><p><code>filter</code> : 배열의 각 요소를 확인해 조건에 맞는 값만 새로운 배열에 남김</p>
<pre><code class="language-jsx">  array.filter(function(element, index, array) {
    // 조건을 반환 (true 또는 false)
  });</code></pre>
</li>
<li><p><code>indexOf</code> : 배열에서 특정 값이 처음으로 등장하는 인덱스 반환</p>
<pre><code class="language-jsx">  array.indexOf(찾고자 하는 값, 검색 시작 위치(선택) 기본값 0)</code></pre>
</li>
</ul>
</li>
<li><p>예시</p>
<p>  배열에서 숫자가 처음으로 등장한 인덱스와 현재 인덱스가 다르면 false로 포함 X</p>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5];
  **//배열에서 처음 등장한 값만 남기고, 중복된 값들은 버림**
  **let uniqueArr = arr.filter((value, index) =&gt; arr.indexOf(value) === index);**
  console.log(uniqueArr); // [1, 2, 3, 4, 5]</code></pre>
<p>  중복된 값만  구하고 싶을때는 <code>!==</code></p>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5, 3, 2, 4];
  **let uniqueArr = arr.filter((value, index) =&gt; arr.indexOf(value) !== index);**
  console.log(uniqueArr); //[2, 4, 3, 2, 4]

  **//중복된 값이 하나씩 나오고 싶을 때**
  let arr = [1, 2, 2, 3, 4, 4, 5, 3, 2, 4];
  **let uniqueArr = [...new Set(arr.filter((value, index) =&gt; arr.indexOf(value) !== index))];**
  uniqueArr.sort((a, b) =&gt; a - b); // 오름차순 정렬
  console.log(uniqueArr); // [2, 3, 4]</code></pre>
<h2 id="🟨reduce">🟨reduce</h2>
</li>
</ul>
</li>
<li><p><code>reduce</code></p>
<ul>
<li><p>개념<br />: 배열을 순회하며 중복된 값 제거한 누적된 새로운 값 제작</p>
<ul>
<li><p>배열을 순회하며 중복 제거와 동시에 다른 변환  작업을 같이 하고 싶을 때 유용</p>
</li>
<li><p>단점 : <code>set</code>보다 성능이 느리고, <code>filter</code>보다 복잡할 수 있다.</p>
<pre><code class="language-jsx">array.reduce((accumulator, currentValue, index, array) =&gt; {
  // 실행할 코드
}, initialValue);</code></pre>
</li>
<li><p><em>//매개변수*</em>
//accumulator:각 단계에서 누적된 결과 저장
//currentValue: 현재 처리 중인 배열 요소
//index (선택적): 현재 요소의 인덱스
//array (선택적): reduce가 호출된 원본 배열</p>
<pre><code></code></pre></li>
</ul>
</li>
<li><p>예시</p>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5];
  // 배열에서 처음 등장한 값만 남기고, 중복된 값들은 버림
  **let uniqueArr = arr.reduce((acc, cur) =&gt; {
      // accr에 cur가 포함되어 있지 않으면 추가
      if (!acc.includes(cur)) {
          acc.push(cur);
      }
      return acc; // 누적된 배열 반환
  }, []); // 초기값은 빈 배열**
  console.log(uniqueArr); // [1, 2, 3, 4, 5]</code></pre>
<h2 id="🟨foreach">🟨forEach</h2>
</li>
</ul>
</li>
<li><p><code>forEach</code></p>
<ul>
<li><p>개념<br />: 객체를 이용한 중복 체크 후 배열 반환</p>
<ul>
<li><p>배열의 순서를 유지하며 명시적으로 중복을 관리하고 싶을 때 / 중복  확인 조건을 커스터마이징 할 때 유용!</p>
</li>
<li><p>단점 : 코드가 더 복잡해짐</p>
<pre><code class="language-jsx">array.forEach((element, index, array) =&gt; {
  // 각 요소에 대해 수행할 작업
});</code></pre>
</li>
</ul>
</li>
<li><p>예시</p>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5];
  let uniqueObj = {};

  **arr.forEach(value =&gt; {
      uniqueObj[value] = true; // 중복 체크
  });**

  let uniqueArr = **Object.keys**(uniqueObj)**.map(Number)**;
  // Object.keys(uniqueObj) : 키를 배열로 변환
  // map(Number) : 키를 숫자로 변환 후 새로운 배열 제작
  console.log(uniqueArr); // [1, 2, 3, 4, 5]</code></pre>
<pre><code class="language-jsx">  let arr = [1, 2, 2, 3, 4, 4, 5];
  let uniqueObj = {};
  let resultArr = []; // 결과를 저장할 배열

  **arr.forEach(value =&gt; {
     if (!uniqueObj[value]) { // uniqueObj에 중복 값이 없을 때만 실행
        uniqueObj[value] = true; // uniqueObj에 중복 체크를 위해 값을 저장
        resultArr.push(value); // 중복되지 않은 값을 resultArr에 추가
     }
  });**

  console.log(uniqueObj); // [1, 2, 3, 4, 5]</code></pre>
<h2 id="🟨결론">🟨결론</h2>
</li>
</ul>
</li>
<li><p>결론</p>
<ul>
<li>작은 배열 : 간결하고 이해하기 쉬운 <code>Set</code> <code>filter</code>  추천</li>
<li>큰 배열 : 성능을 고려해 <code>Set</code> <code>forEach와 객체</code> 추천</li>
<li>유연한 로직 필요한 경우 : <code>reduce</code> 로 중복 제거 후 다양한 누적 로직 구현 추천</li>
</ul>
</li>
</ol>
<br />

<hr />
<h2 id="요약-💁♀️">요약 💁‍♀️</h2>
<ul>
<li><strong>간단하고 빠르게 중복 제거, 최고 성능!</strong>: <code>Set</code></li>
<li><strong>배열의 순서를 유지하면서 중복 제거</strong>: <code>filter</code> 또는 <code>reduce</code></li>
<li><strong>명시적이고 유연한 중복 관리</strong>: <code>forEach</code></li>
</ul>
<hr />
<p><br /><br /><br />
✅ 참고</p>
<p><a href="https://likedev.tistory.com/entry/Javascript-%EB%B0%B0%EC%97%B4-%EC%A4%91%EB%B3%B5-%EC%A0%9C%EA%B1%B0%ED%95%98%EA%B8%B0">[Javascript] 배열 중복 제거하기</a></p>
<p><a href="https://blacklobster.tistory.com/13">빠르게 찾아보자! 자바스크립트(JS) 문자열, 배열 중복값 찾기 / 체크</a></p>