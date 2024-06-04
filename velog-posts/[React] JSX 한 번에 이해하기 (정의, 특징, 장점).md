<p>👩‍🦳
면접보는데 JSX도 모르고 갈끄야?!!!!!!! (나한테 하는 말임)</p>
<h2 id="✅-jsx란">✅ JSX란?</h2>
<p>JavaScript Xml
자바스크립트 안에 HTML 코드를 쓸 수 있게 해주는 문법입니다. 
브라우저는 JSX 파일을 직접 읽을 수 없기 때문에 브라우저 실행 전 &quot;바벨&quot;과 같은 컴파일러를 통해 일반 자바스크립트 형태의 코드로 변환됩니다.</p>
<pre><code>// 실제 JSX 예시

function App() {
    return (
      &lt;h1&gt;Hello, World!&lt;/h1&gt;
    );
}

위와 같이 작성 시 바벨이 다음과 같이 자바스크립트로 해석

function App() {
    return React.createElement(&quot;h1&quot;, null, &quot;Hello, World!&quot;);
}</code></pre><br />
<span style="color: #38c491;">🤷‍♀️ 브라우저는 왜 JSX를 읽을 수 없는걸까?</span><br />
👩‍💻 브라우저가 이해하는 기본 언어가 자바스크립트, HTML, CSS이기 때문입니다. JSX는 자바스크립트와 HTML을 결합한 리액트 라이브러리에서 사용되는 자바스크립트의 확장 문법입니다! JSX는 자바스크립트가 아니기 때문에 컴파일러를 통해 자바스크립트 코드로 변환해야 브라우저가 읽을 수 있어요!

<p>JSX(외국인) &gt; 컴파일러(번역가) &gt; 브라우저(외국말을 모르는 한국인)</p>
<h2 id="✅-jsx-장점">✅ JSX 장점</h2>
<p>물론, JSX를 사용하는 것은 필수가 아닙니다! 하지만 왜! 
많은 개발자들이 리액트와 함께 JSX 문법을 사용하는 걸까요?</p>
<ol>
<li><p>직관적이다
UI를 HTML처럼 작성할 수 있기 때문에 해당 문법을 사용하면 자바스크립트 코드 안에서 UI를 더 직관적으로 작성할 수 있습니다. </p>
<pre><code>const element = &lt;h1&gt;Hello, world!&lt;/h1&gt;;</code></pre></li>
<li><p>에러 메시지
원활한 개발을 위해 정확한 에러 및 경고 메시지를 표시해줍니다.</p>
</li>
</ol>
<h2 id="✅-jsx-특징">✅ JSX 특징</h2>
<ol>
<li>반드시 하나의 부모로 감싸기<pre><code>//오류
function App() {
 return (
     &lt;div&gt;Hello&lt;/div&gt;
     &lt;div&gt;World!&lt;/div&gt;
 );
}
</code></pre></li>
</ol>
<p>//반드시 하나의 부모로 감싸기
function App() {
    return (
        <div> 또는 &lt;&gt;
            <div>Hello</div>
            <div>World!</div>
        </div> 또는 &lt;/&gt;
    );
}</p>
<pre><code>
2. 자바스크립트 표현식 사용</code></pre><p>function App() {
    const name = 'World';
    return (
        <div>
            <div>Hello</div>
            <div>{name}!</div>
        </div>
    );
}</p>
<pre><code>
3. 조건에 따라 삼항연산자</code></pre><p>function App() {
    const loginYn = 'Y';
    return (
        &lt;&gt;
            <div>
                {loginYn === 'Y' ? (
                    <div>회원 입니다.</div>
                ) : (
                    <div>비회원 입니다.</div>
                )}
            </div>
        &lt;/&gt;
    );
}</p>
<pre><code>
4. 스타일링은 카멜케이스로 표기</code></pre><p>function App() {
    const style = {
        backgroundColor: 'red',
        fontSize: '12px'
    }
    return (
        <div>Hello!</div>
    );
}</p>
<pre><code>
&lt;br&gt;&lt;br&gt;&lt;br&gt;
🎓JSX란 무엇인가요?



&lt;br&gt;&lt;br&gt;&lt;br&gt;
✅ 참고
_https://ko.legacy.reactjs.org/docs/introducing-jsx.html
https://goddaehee.tistory.com/296_</code></pre>