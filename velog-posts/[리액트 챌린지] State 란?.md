<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/f36cd121-fdf6-40aa-b3cc-41a1773f3072/image.png" /></p>
<p>호기롭게 신청했던 노마드코더 리액트 챌린지 🚢....
하지만 직장인의 삶에 치이고 게으름을 이기지 못해 다시 처음부터 강의를 싸악 보는 중에 확실히 전보다 더 강의, 리액트에 대한 이해도가 높아졌다는 것을 깨달았음미다 👼
이래서 복습이 정말 중요한거였어요...ㅎㅎㅎ
오늘은 리액트 state 뽀개러 가보자구 😉</p>
<blockquote>
<h2 id="state란">State란?</h2>
</blockquote>
<h2 id="🟦-01-state">🟦 01. State</h2>
<pre><code class="language-javascript">import { useState } from 'react';

function App() {
    const [count, setCount] = useState(0);
    return (
        &lt;div&gt;
            &lt;p&gt;{count}번 클릭&lt;/p&gt;
            &lt;button onClick={() =&gt; setCount(count + 1)}&gt;클릭&lt;/button&gt;
        &lt;/div&gt;
    );
}</code></pre>
<ul>
<li>리액트에서 이벤트에 의해 변경되는 <span style="color: #38c491;"><strong>동적인 값</strong></span>을 말합니다. (ex. 버튼 클릭 onClick, input 입력 onChange)</li>
<li>컴포넌트 안에서 <span style="color: #38c491;"><strong>지속적인 변경이 일어나는 값을 관리</strong></span>하기 위해 사용합니다.</li>
<li>값 변경 후 재렌더링 시 변경되는 부분만 렌더링합니다.</li>
</ul>
<p>🌱 state는 간단히 말하자면 <strong>변수</strong>입니다. 하지만 우리가 알고있는 const, let과 다르게 동적인 값을 다룰 수 있는 변수입니다 :)</p>
<p>🌱 state는 배열을 만들어주고 배열의 첫 번째 아이템은 value, 두번째는 val입니다.</p>
<h2 id="🟦-02-state-사용하기">🟦 02. State 사용하기</h2>
<ol>
<li>파일 상단에 useState를 임포트<pre><code class="language-javascript">import { useState } from 'react';</code></pre>
</li>
<li>useState()를 선언<pre><code class="language-javascript">const [count, setCount] = useState(초기값(생략 가능));</code></pre>
</li>
</ol>
<ul>
<li>{ useState } Hooks를 활용하여 state를 사용합니다.</li>
<li>useState란 리액트의 기본 Hook 중 하나로, 컴포넌트에서 state를 추가할 때 사용합니다.</li>
<li><span style="color: #38c491;">💡 state 값 변경을 위해서는 <strong>반드시 setState 함수를 이용</strong>해야합니다.  <span></li>
</ul>
<p>!codepen[sooozi/embed/xxmymaE?default-tab=html%2Cresult]</p>
<h2 id="🟦-03-state-변경하는-방법">🟦 03. State 변경하는 방법</h2>
<ol>
<li>직접 값 설정<pre><code class="language-javascript">const [count, setCount] = useState(0);
setCount(count + 1);</code></pre>
</li>
<li>함수 사용<pre><code class="language-javascript">const [count, setCount] = useState(0);
</code></pre>
</li>
</ol>
<p>setCount((current) =&gt; {
    return current + 1
})</p>
<p>```</p>
<ul>
<li>현재 값을 기반으로 state를 변경할 때는 함수를 사용하는 것이 좋습니다 👼</li>
</ul>
<h2 id="📓-04-my-note">📓 04. MY NOTE</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/e3acc624-db03-409e-a85e-08771e3c8d63/image.png" /></p>
<h2 id="💬-reference">💬 Reference</h2>
<p>  <a href="https://life-with-coding.tistory.com/510">https://life-with-coding.tistory.com/510</a>
<a href="https://lakelouise.tistory.com/260">https://lakelouise.tistory.com/260</a>
<a href="https://velog.io/@hamham/%EB%A6%AC%EC%95%A1%ED%8A%B8%EC%97%90%EC%84%9C-state%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0">https://velog.io/@hamham/%EB%A6%AC%EC%95%A1%ED%8A%B8%EC%97%90%EC%84%9C-state%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0</a></p>