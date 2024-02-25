<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/d208562c-5273-40ff-acf3-dc18a7466db5/image.png" /></p>
<p>많이 사용해 보았지만 제대로 파헤쳐 본 적 없었던 화살표 함수!
오늘은 챗지피티가 말아주는 화살표 함수로 뽀개보자고! 아자아자아자! 😀😀😀</p>
<blockquote>
<h2 id="javascript-화살표-함수">JavaScript 화살표 함수</h2>
</blockquote>
<h2 id="🟨-1-화살표-함수란">🟨 1. 화살표 함수란?</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/1a8a6e64-0b6c-4f66-af99-7d49f496012c/image.png" /></p>
<ul>
<li>ES6부터 화살표 함수라는 새로운 문법 방식으로 함수를 만들 수 있게 되었다.</li>
<li>화살표 함수는 =&gt; 기호를 사용하여 function 키워드 생략이 가능하다.</li>
</ul>
<h2 id="🟨-2-화살표-함수-문제풀이">🟨 2. 화살표 함수 문제풀이</h2>
<ol>
<li>화살표 함수는 어떻게 선언하나요?
a) function myFunction() {}</li>
</ol>
<p><strong>b) const myFunction = () =&gt; {}</strong>
c) arrowFunction = () =&gt; {}</p>
<ol start="2">
<li><p>화살표 함수의 주요 특징 중 하나는 무엇인가요?
a) this 키워드가 바인딩되지 않는다.
b) 다른 함수와 이름이 충돌하지 않는다.
c) 변수를 선언할 필요가 없다.</p>
</li>
<li><p>다음 화살표 함수의 결과는 무엇인가요?
a) 2
b) 3
c) 5</p>
<pre><code class="language-javascript">const add = (a, b) =&gt; a + b;
console.log(add(2, 3));</code></pre>
</li>
</ol>
<ol start="4">
<li><p>화살표 함수는 어떤 상황에서 주로 사용되나요?
a) 클래스 메서드 정의
b) 이벤트 핸들러 함수
c) 간단한 인라인 함수</p>
</li>
<li><p>화살표 함수와 일반 함수(함수 선언식 또는 함수 표현식) 사이의 주요 차이점은 무엇인가요?
a) 화살표 함수는 항상 익명 함수이다.
b) 화살표 함수는 함수 스코프를 가지지 않는다.
c) 화살표 함수는 return 키워드를 사용하지 않는다.</p>
</li>
</ol>
<h3 id="🟨-정답-확인">🟨 정답 확인!</h3>
<ol>
<li><p>화살표 함수는 어떻게 선언하나요?
정답: b) const myFunction = () =&gt; {}</p>
</li>
<li><p>화살표 함수의 주요 특징 중 하나는 무엇인가요?
정답: a) this 키워드가 바인딩되지 않는다.</p>
</li>
<li><p>다음 화살표 함수의 결과는 무엇인가요?
정답: c) 5</p>
</li>
</ol>
<pre><code class="language-javascript">const add = (a, b) =&gt; a + b;
console.log(add(2, 3));</code></pre>
<ol start="4">
<li><p>화살표 함수는 어떤 상황에서 주로 사용되나요?
정답: c) 간단한 인라인 함수</p>
</li>
<li><p>화살표 함수와 일반 함수(함수 선언식 또는 함수 표현식) 사이의 주요 차이점은 무엇인가요?
정답: a) 화살표 함수는 항상 익명 함수이다.</p>
</li>
</ol>