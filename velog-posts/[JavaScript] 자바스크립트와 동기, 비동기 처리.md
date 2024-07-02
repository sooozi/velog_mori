<p>알면 알수록 알 수 없는 자바스크립트 세상~
튼튼한 기본기를 위해 기초부터 다시한번 제대로 이해해보자고! 아자아자아자! 😀😀😀
<br /><br /></p>
<blockquote>
<h2 id="intro">INTRO</h2>
</blockquote>
<h2 id="🟨-1-동기-비동기자바스크립트-엔진">🟨 1. 동기, 비동기...자바스크립트 엔진?</h2>
<p>개발을 접하면서 동기, 비동기처리에 대한 이야기를 정말 많이 들어보았다. 하지만 누군가 나에게 동기랑 비동기가 모에오? 라고 물어본다면 제대로 답변을 할 수 없었고 자바스크립트는 싱글 스레드 언어인데 이게...뭐지? 싶었다. 
<span style="color: #ffb02e;">💁‍♀️ 자바스크립트와 동기, 비동기 처리가 어떻게 연관이 되어있는지 살펴보러 가보자구</span></p>
<p><br /><br /></p>
<blockquote>
<h2 id="동기와-비동기">동기와 비동기</h2>
</blockquote>
<h2 id="🟨-2-동기-비동기">🟨 2. 동기, 비동기</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/15dae2a8-1a94-426a-88cc-fe5ad0d6e4a4/image.png" />
동기와 비동기는 사진으로 보았을 때 차이점을 더 확실하게 느낄 수 있다. 이미지로 보면 확연한 차이를 느낄 수 있는 것처럼 둘은 <span style="color: #ffb02e;"><strong>작업 수행 방식</strong></span>과 <span style="color: #ffb02e;"><strong>결과 반환 시점</strong></span>에 차이가 있다.
<br /></p>
<h3 id="🟨-2-1-syncsynchronous-동기">🟨 2-1. Sync(Synchronous) 동기</h3>
<p>요청 작업에 대해 완료 여부를 따져 <strong>순차대로 처리</strong>한다. 작업 실행 후 해당 작업을 완료할 때까지 대기하며 해당 작업 완료 전까지는 다른 작업을 수행하지 않는다. </p>
<ul>
<li>😸장점 : 설계가 간단, 직관적, 요청&amp;응답 순서 보장</li>
<li>😿단점 : 작업이 많아지면 자원, 시간 낭비 및 속도 저하, 병렬적 여러 작업 수행 불가능</li>
<li>🗨️예시 : 메일 작성 후 보내기 버튼 클릭 (전체 페이지 업데이트)<br />

</li>
</ul>
<h3 id="🟨-2-2-asyncasynchronous-비동기">🟨 2-2. Async(Asynchronous) 비동기</h3>
<p>요청 작업에 대해 <strong>완료 여부를 따지지 않고 다음 작업을 그대로 수행</strong>한다. 작업 실행 중 다른 작업 수행이 가능하며 결과는 작업이 완료될 때 반환한다. </p>
<ul>
<li>😸장점 : 속도, 성능 향상, 병렬적 여러 작업 수행 가능, 사용자 경험 개선 가능</li>
<li>😿단점 : 설계 복잡, 요청&amp;응답 순서 보장 불가</li>
<li>🗨️예시 : 블로그 및 카페 댓글 작성 후 작성 버튼 클릭 (댓글 영역만 업데이트)</li>
</ul>
<br />
<span style="color: #ffb02e;">💁‍♀️ 그러면 자바스크립트가 싱글 스레드 언어인데 어떻게 비동기 처리를 하는걸까?</span>

<p><br /><br /></p>
<blockquote>
<h2 id="자바스크립트">자바스크립트</h2>
</blockquote>
<h2 id="🟨-3-자바스크립트는-싱글-스레드-언어">🟨 3. 자바스크립트는 싱글 스레드 언어</h2>
<p>자바스크립트는 싱글 스레드 언어로 한 번에 하나의 작업만 가능하다.
마치 건물을 짓는 인부가 한명이라고 생각하면 이해가 더 쉬워진다! 자바스크립트에는 인부가 한명인 것이다!
<img alt="" src="https://velog.velcdn.com/images/sooozi/post/9d450629-da66-4b05-91a8-4e72a10b3362/image.png" />
인부가 한 번에 하나의 동작(시멘트를 바르고 벽돌 쌓기)만 할 수 있는 것처럼 자바스크립트도 동시 작업이 불가하고 한 번에 하나의 작업만 가능하다. 하나의 함수가 실행되고 끝나야 그 다음 함수 실행이 가능하다는 이야기이다.
<strong>함수가 실행되고 끝나고 실행되고 =&gt; 이것은 위에서 이야기한 '동기' 처리 방식이다.</strong>
그래서! <span style="color: #ffb02e;">자바스크립트는 동기 방식으로 실행이 되는 것이다! </span></p>
<p><strong>하지만, 비동기 실행이 불가능한 것은 아니다.</strong> 인부 한 명으로도 비동기 실행이 가능하다. 함수들을 동시에 실행시키는 것이 아니라 비동기처럼 보여지도록 &quot;완료 여부를 따지지 않고 다음 작업을 수행&quot;하게 해주는 것이다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/b837a71e-9459-4834-9587-26c4c26c7610/image.png" /></p>
<p><strong>싱글 스레드 언어인 자바스크립트에서 비동기 처리를 가능하게 해주는 친구</strong>는 바로 우리가 많이 들어보았던 <span style="color: #ffb02e;">🎉<strong>이벤트 루프</strong>🎉</span>이다!</p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/8f658213-cefb-4dda-9539-0510ce4f7d2f/image.gif" /></p>
<p>그래서! 다음에는 자바스크립트에서 어떻게 <strong>이벤트 루프</strong>로 비동기 처리를 할 수 있는지 찾아보고 정리해보는 시간을 가져보겠다! ㅎ.ㅎ</p>
<p>그럼 이만 ^-------------------------------------------------^</p>
<p><br /><br /><br />
✅ 참고
<em><a href="https://inpa.tistory.com/entry/WEB-%F0%9F%8C%90-%EB%B9%84%EB%8F%99%EA%B8%B0Async%ED%86%B5%EC%8B%A0-%EB%8F%99%EA%B8%B0Sync%ED%86%B5%EC%8B%A0">https://inpa.tistory.com/entry/WEB-%F0%9F%8C%90-%EB%B9%84%EB%8F%99%EA%B8%B0Async%ED%86%B5%EC%8B%A0-%EB%8F%99%EA%B8%B0Sync%ED%86%B5%EC%8B%A0</a></em>
<em><a href="https://ingg.dev/js-work/">https://ingg.dev/js-work/</a>
<a href="https://devyihyun.tistory.com/160">https://devyihyun.tistory.com/160</a></em></p>