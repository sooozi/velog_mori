<h1 id="문제">문제</h1>
<p>풀페이지 중간에 가로 스크롤 섹션 추가</p>
<p>풀페이지 무료 버전 사용으로 커스텀 필요</p>
<p>아래와 같이 풀페이지 + 스와이퍼를 사용해 페이지 구현
But! 가로 스크롤 시 스크롤한 만큼만 움직이는 “freeMode: true” 상태 구현요청</p>
<p>스와이퍼 freeMode:true 수정 후 문제점 :
스와이어 섹션 진입 시 바로 이전 섹션으로 스크롤하면 스크롤 안됨
=&gt; 이유 : 섹션에 진입하면 스와이퍼를 위한 스크롤로 변경되도록 지정했기 때문
슬라이드 앞 뒤로 빈 슬라이드를 만들어 슬라이드 섹션으로 진입 시 무조건 슬라이드가 되도록 설정했지만 오히려 전체적으로 보았을 때 어색해보임</p>
<p>=&gt; 결론 풀페이지.js + 스와이퍼 사용 시 스와이퍼 freeMode:false 사용 추천</p>
<p class="codepen" style="height: 300px; display: flex; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/sooozi/pen/poYXONQ">
  GSAP(Fullpage) + Swiper</a> by sooozi (<a href="https://codepen.io/sooozi">@sooozi</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>