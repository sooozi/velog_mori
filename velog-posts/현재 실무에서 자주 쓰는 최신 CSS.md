<p>현 퍼블리셔가 말아주는 실무에서 자주 쓰는 최신 CSS 살펴보기 👀</p>
<p>현재 기준 2년 차 퍼블리셔로 일하고 있는 지금!!!
최신 CSS 기술 관련 포스팅을 보고 내가 직접 사용해 보고 정리해 보면 좋을 것 같아 글을 쓰게 되었습니다.👩‍💻 </p>
<p>📕 최신 css 기술과 관련하여 이미 수많은 글을 살펴보면 너무 자세하고 깔끔하게 정리가 되어있는데요.
하지만 진짜 실무에서는 이러한 기술들을 어떻게 쓰고 있는지? 정말로 쓰고 있는지!!! 사용하고 있지만 내가 잘 이해하고 있는지? 궁금..하잖아요? 🫥</p>
<p>그래서! <span style="color: #38c491;">최신 css 기술</span>을 소개해주는 글들을 토대로</p>
<blockquote>
<ul>
<li>현재 실무에서 제가 정말로 사용하고 있는 기술(🐱표기)은 무엇인지!</li>
</ul>
</blockquote>
<ul>
<li>codepen으로 어떻게 적용하는지 알려드리는 것은 물론이고!</li>
</ul>
<p>사용하지 않았지만 앞으로 쓰면 좋을 것 같은 기술들(😿표기)에 대한 <span style="color: #38c491;"><strong>짤막한 제 의견</strong></span>도 함께 소개해보겠습니다 :)
<br /></p>
<hr />
<h2 id="✅안정적인-업그레이드">✅안정적인 업그레이드</h2>
<p>: 오래된 기술을 대체하여 해킹 또는 문제를 해결합니다.</p>
<h3 id="🐱-aspect-ratio">🐱 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio">aspect-ratio</a></h3>
<p>요소의 가로와 세로 비율 설정 시 사용되며, 이미지나 동영상 비율을 조정할 때 유용합니다.</p>
<p>!codepen[mark_sottek/embed/bGZrBoy?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 영원한 나의 선생님 쏘짱에게 해당 속성을 배우고 지금까지 정말 잘 쓰고 있는 중이고 다른 분들에게도 많이 추천드렸던 속성입니다. 해당 속성을 알고 계시면 확실히 반응형에서도 이미지, 비디오 사이즈 조절이 쉬워서 이건 꼭 기억하셨으면 좋겠어요!</span></p>
<h3 id="🐱-object-fit">🐱 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit">object-fit</a></h3>
<p>이미지, 비디오를 부모 요소에 맞게 자동 조절하여 깔끔하게 보이도록 도와줍니다. (오래된 속성이지만, 한 줄의 업그레이드로 중요한 문제를 해결하기에 해당 주제에서 소개되고 있습니다!)</p>
<p>!codepen[hyonixk/embed/QWdaeRZ?default-tab=result]</p>
<p>!codepen[netsi1964/embed/NWgJzWB?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 거의 대부분의 background 속성과 함께 사용하는 속성입니다. 반응형에서도 문제 없이 자동 조절되어서 실무에서 많이 사용됩니다!</span></p>
<h3 id="😿-margin-inline">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline">margin-inline</a></h3>
<p>텍스트나 다른 인라인 요소의 좌우 여백을 설정합니다.</p>
<p>더 쉽게 설명하자면!
한국어처럼 왼쪽에서 오른쪽으로 텍스트를 사용하는 언어의 경우, margin-inline-start는 왼쪽 마진을, margin-inline-end는 오른쪽 마진을 나타냅니다. 반대로, 아랍어처럼 오른쪽에서 왼쪽으로 텍스트를 사용하는 언어의 경우에는 이것이 반대가 될 수 있습니다.</p>
<p>writing-mode 속성은 CSS에서 요소의 텍스트 레이아웃 방향을 지정하는 데 사용됩니다. writing-mode와 함께 margin-inline을 사용하여 텍스트의 인라인 방향 마진을 설정할 수 있어 함께 사용하면 좋은 속성인데요! 이를 통해 다국어 및 다방향 레이아웃을 더욱 유연하게 다룰 수 있습니다.</p>
<p>👇 margin-inline을 지워보세요!</p>
<p>!codepen[alam_tahera/embed/NWOQNZz?default-tab=css%2Cresult]</p>
<p>!codepen[team/sparkbox/embed/BabzqpJ?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 margin-inline은 아직 사용해 보지 않은 속성이라 새로운 속성을 배울 수 있어 좋았다! 가끔 세로로 텍스트를 넣는 시안들이 들어오는데 고런 시안을 진행할 때 꼭 기억했다가 사용해 볼 예정이다!</span></p>
<br />

<h2 id="✅안정적인-개선">✅안정적인 개선</h2>
<p>: 다양한 브라우저, 디바이스에서 원활히 작동되는 최신 속성을 통해 향상된 경험을 제공합니다.</p>
<h3 id="😿-text-underline-offset">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset">text-underline-offset</a></h3>
<p>텍스트의 밑줄과 텍스트 사이의 간격을 설정합니다.</p>
<p>!codepen[seyedi/embed/KKdXQaO?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 실무에서 저어어어어어엉말 많이 사용되는 밑줄쓰...항상 밑줄과 텍스트 사이 간격을 before로 밑줄을 만들었었는데, 기회가 되면 해당 속성으로 꼭 사용해 보고 싶습니다! </span></p>
<h3 id="😿-outline-offset">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-offset">outline-offset</a></h3>
<p>요소의 외곽선과 해당 요소의 경계 사이의 간격을 설정합니다.</p>
<p>!codepen[SitePoint/embed/VLXyZw?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 해당 속성도 아직 사용해 보지 않았지만 꼭 실무에서 한번 사용해 보고 싶어요! 워낙 다양한 디자인을 퍼블하기 때문에 요것도 사용하면 유용할 것 같습니다 :)</span></p>
<h3 id="😿-scroll-margin-topbottom">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-top">scroll-margin-top/bottom</a></h3>
<p>요소가 스크롤되어 보일 때 상단 또는 하단에서 추가 여백을 지정하여 스크롤 시점을 미리 조정할 수 있습니다.</p>
<p>!codepen[andyadams/embed/wNjxMN?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 사용할 일이 있을까 싶지만 언제나 그렇듯 알아두면 언젠가는 사용하니까 codepen 눈이 익혀두기!!!</span></p>
<h3 id="😿-color-scheme">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color-scheme">color-scheme</a></h3>
<p>웹사이트 전체적으로 사용될 색상 체계를 지정하여 사용자가 시스템 환경 설정에 맞게 다양한 테마를 선택할 때 웹사이트의 색상을 자동으로 조정하는 CSS 속성입니다.</p>
<p>무슨...말이지...?</p>
<p>color-scheme(컬러-스키마)은 CSS의 미디어 쿼리에서 사용되는 속성 중 하나입니다. 이 속성은 사용자가 다크 모드나 라이트 모드 등과 같은 색상 테마를 선호하는 경우 유용하게 사용됩니다.</p>
<ul>
<li>auto: 이는 기본 값으로, 브라우저가 사용자의 시스템 설정에 따라 적절한 색상 테마를 자동으로 선택합니다.</li>
<li>light: 사용자가 라이트 모드를 선호하는 경우에 사용됩니다. 웹 페이지는 밝은 색상 테마로 표시됩니다.</li>
<li>dark: 사용자가 다크 모드를 선호하는 경우에 사용됩니다. 웹 페이지는 어두운 색상 테마로 표시됩니다.</li>
</ul>
<p>예를 들어, 다음과 같이 color-scheme 속성을 사용하여 웹 페이지의 색상 테마를 설정할 수 있습니다:</p>
<pre><code>@media (prefers-color-scheme: dark) {
  body {
    color-scheme: dark;
    background-color: #333; /* 다크 모드에 대한 배경색 설정 */
    color: #fff; /* 다크 모드에 대한 텍스트 색상 설정 */
  }
}

@media (prefers-color-scheme: light) {
  body {
    color-scheme: light;
    background-color: #fff; /* 라이트 모드에 대한 배경색 설정 */
    color: #333; /* 라이트 모드에 대한 텍스트 색상 설정 */
  }
}</code></pre><p>!codepen[Ondreas/embed/qBMvNvp?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 굉장히 신기했던 속성쓰..써보고시퍼욤...ㅎㅎㅎ</span></p>
<h3 id="😿-accent-color">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/accent-color">accent-color</a></h3>
<p>웹사이트나 앱에서 강조되는 요소의 색상을 설정하는 CSS 속성입니다.</p>
<p>!codepen[jh3y/embed/qBmeBjw?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 최근에 폼 작업을 진행하게 되면서 해당 속성을 알게 되었는데요. 현재는 모든 태그에 동일하게 적용될 수 있도록 공통 파일에 적용하여 사용하고 있습니다!</span></p>
<h3 id="🐱-widthfit-content">🐱 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content">width:fit-content</a></h3>
<p>요소의 너비를 요소 내용의 크기에 맞게 자동 조절하는 CSS 속성입니다.</p>
<p>!codepen[airen/embed/zYZvGrY?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 반응형이...문제다 문제...ㅠㅠ 반응형에서 넓이 값이 맞지 않아 열심히 찾아보다가 해당 속성을 알게 되어 잘 쓰고 있는 속성 중 하나입니다!</span></p>
<br />

<h2 id="✅점진적인-개선">✅점진적인 개선</h2>
<p>: 아래 속성들은 지원 가능 브라우저에서는 업그레이드된 환경을 제공하며, 지원되지 않는 브라우저에서는 문제가 발생할 우려가 없는 경우 사용 가능합니다.</p>
<h3 id="😿-overscroll-behavior">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior">overscroll-behavior</a></h3>
<p>사용자가 스크롤하는 동안 요소의 오버스크롤(넘치는 스크롤) 동작을 제어하는 CSS 속성입니다.
스크롤 체이닝 현상 관리를 위해 제공된 속성으로, 화면에서 화면 속 콘텐츠의 스크롤 바가 전부 스크롤 다운되었을 때 메인 화면이 스크롤 되는 것을 방지할 때 사용하는 속성입니다.</p>
<p>!codepen[phyesix/embed/VwKxMmz?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 스크롤 체이닝 넘나 시러하는 편! 반드시 기억하게따...ㅂㄷㅂㄷ</span></p>
<h3 id="🐱-text-wrap">🐱 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-wrap">text-wrap</a></h3>
<p>텍스트가 블록의 너비를 벗어날 때 줄 바꿈 동작을 지정하는 CSS 속성입니다.</p>
<p>!codepen[lonekorean/embed/PoLEZJP?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 관리자와 연동되는 프론트 또는 관리자처럼 사용자가 직접 텍스트를 기재하는 곳에 많이 사용합니다. 즤발...넘치지 마러....</span></p>
<h3 id="😿-scrollbar-gutter">😿 <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter">scrollbar-gutter</a></h3>
<p>스크롤바와 내용 사이의 여백을 지정하여 사용자 경험을 향상시키는 CSS 속성입니다.
Demo for <a href="https://brm.us/scrollbar-gutter">https://brm.us/scrollbar-gutter</a></p>
<p>!codepen[shadeed/embed/abwRVgN?default-tab=result]</p>
<p>!codepen[bramus/embed/LYyzKrX?default-tab=result]</p>
<p><br /><span style="display: inline-block; color: gray; font-size: 14px;">👩‍💻 요 스크롤바 여백 때문에 고생했던 적이 많은데...이렇게 좋은 속성이 있다니..!! 해당 속성은 앞으로 정말 많이 사용할 것 같아요!!!!</span></p>
<p><br /><br /><br /><br /><br /><br /></p>
<hr />
<p>✅참고
<em>원문 : <a href="https://moderncss.dev/12-modern-css-one-line-upgrades/">https://moderncss.dev/12-modern-css-one-line-upgrades/</a>
번역 : <a href="https://velog.io/@surim014/12-modern-css-one-line-upgrades">https://velog.io/@surim014/12-modern-css-one-line-upgrades</a></em></p>