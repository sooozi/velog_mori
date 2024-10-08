<h1 id="jest-란">Jest 란?</h1>
<p>Jest는  페이스북에서 개발된 <strong>테스팅 라이브러리</strong>로, React와 함께 많은 자바스크립트 개발자들로부터 인기를 얻고 있는 프레임워크이다. 출시 초기에는 주로 프론트엔드에서 사용되었으나, 최근에는 백엔드에서도 기존 테스팅 라이브러리를 대체하고 있다.</p>
<p>Jest의 가장 큰 장점은 Test Runner(테스트 파일을 찾아 실행하고 결과를 알려주는 도구), Test Matcherm(테스트에서 실제 값과 기대한 값이 일치하는지 비교하는 함수들), Test Mock(실제 기능을 가짜(mock)로 만들어 테스트 속도를 높이고 외부 의존성을 제거하는 도구)을 모두 포함한 올인원 테스팅 프레임워크라는 점이다. </p>
<p>Jest는 이 세 가지 기능을 모두 지원하기 때문에, 테스트를 쉽게 작성하고 실행할 수 있어 많은 개발자들이 선호하는 대세 테스트 프레임워크가 되었다!</p>
<h2 id="jest-설치">Jest 설치</h2>
<p>원하는 프로젝트에 Jest 설치</p>
<pre><code class="language-jsx">npm i -D jest</code></pre>
<p>설치 완료 후 package.json 파일을 열어 test 스크립트를 jest로 수정하기!</p>
<p>수정 후 터미널에 npm test 를 입력하면 jest 커멘드 실행 가능!</p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/d85f3dd1-bb74-4b6a-afaa-437529015419/image.png" /></p>
<h2 id="jest-기본-문법">Jest 기본 문법</h2>
<p>test 파일 만들기 ⇒ test파일은 ‘<strong>테스트할함수파일명.test.js</strong>’로 한다.
타입스크립트의 경우 ‘<strong>테스트할함수파일명.spec.ts</strong>’로 제작!</p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/d8d168a0-7e63-4b69-b4d3-de51f46afbd6/image.png" /></p>
<pre><code class="language-jsx">describe('테스트 그룹 설명', () =&gt; {
  it('테스트 케이스 설명', () =&gt; {
    // 테스트 코드
  });

  // 또는
  test('테스트 케이스 설명', () =&gt; {
    // 테스트 코드
  });
});

//비동기 테스트
test('비동기 테스트', async () =&gt; {
  const data = await fetchData();
  expect(data).toEqual(expectedData);
});</code></pre>
<p><code>describe</code> : 여러 테스트를 그룹으로 묶어주는 역할을 한다. 이 안에 콜백 함수로 테스트에 사용할 변수나 객체 등을 선언하면, 그 값들은 해당 테스트 그룹 내에서만 일회용으로 사용된다. ⇒ 테스트들을 하나의 상자에 모아두고, 그 안에서만 필요한 것들을 사용할 수 있게 해주는 기능</p>
<p><code>it</code> 또는 <code>test</code> : 실제 테스트 케이스를 정의할  때 사용한다.</p>
<p><code>toXxx</code> : Test Matcher 함수를 의미하는 일반적인 표현이다. to로 시작하는 다양한 Matcher 함수들이 있는데, Xxx는 실제로 사용되는 함수 이름들을의미하는 자리이다.</p>
<p>예를 들어:</p>
<ul>
<li><code>toBe()</code>는 기본형 값이 같은지 비교할 때 사용</li>
<li><code>toEqual()</code>는 객체나 배열 같은 복합 구조의 값이 같은지 비교할 때 사용</li>
<li><code>toContain()</code>는 배열이나 문자열 안에 특정 값이 있는지 확인할 때 사용</li>
</ul>
<p>⇒ <code>toXxx</code>는 <code>to</code>로 시작하는 Test Matcher 함수들이 여러 가지 있다는 걸 표현하는 방식으로 <code>toBe</code>, <code>toEqual</code>, <code>toContain</code> 등 다양하게 바뀔 수 있다.</p>
<h2 id="jest-테스트-파일-실행">Jest 테스트 파일 실행</h2>
<p>Jest는 기본적으로 test.js로 끝나거나, <strong>test</strong>디렉터리(폴더) 안에 있는 파일들은  모두 테스트 파일로 인식한다. npm test 실행 시 프로젝트 내 모든 테스트 파일을 찾아 테스트를 실행한다. </p>
<ul>
<li>모든 테스트 파일 실행 : npm test</li>
<li>특정 테스트 파일 실행 : npm test &lt;파일명이나 경로&gt;</li>
</ul>
<p>참고</p>
<p><a href="https://jestjs.io/docs/getting-started">Getting Started · Jest</a></p>
<p><a href="https://inpa.tistory.com/entry/JEST-%F0%9F%93%9A-jest-%EB%AC%B8%EB%B2%95-%EC%A0%95%EB%A6%AC">[JEST] 📚 JEST 소개 &amp; 기본 사용법 정리</a></p>
<p><a href="https://www.daleseo.com/jest-basic/">Jest로 기본적인 테스트 작성하기</a></p>