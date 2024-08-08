<p>프엔 공부 중 빠지지 않는 이벤트 루프!
비동기 처리를 가능하게 해주는 이벤트 루프 제대로 이해해보자고! 😀😀😀
<br /><br /></p>
<blockquote>
<h2 id="이벤트-루프">이벤트 루프</h2>
</blockquote>
<h2 id="🟨-1-자바스크립트와-이벤트-루프">🟨 1. 자바스크립트와 이벤트 루프</h2>
<p>자바스크립트는 싱글 스레드 언어로 한 번에 하나의 코드만 처리할 수 있다.
만약 싱글 스레드로 모든 브라우저 동작이 실행된다면, 우리는 파일 다운로드 중에는 다른 작업을 아무것도 못하고 대기해야 하는 상황이 생긴다. 그렇기 때문에 우리는 파일 다운로드, 이벤트, 네트워크 요청과 같이 비동기처리 방식이 필요할 때가 아주 많이 있다.
이렇게 파일 다운, 타이머, 네트워크 요청과 같이 오래 걸리는 작업들은 동시에 작업 처리를 진행하도록 해야하는 데 이러한 비동기 작업을 효율적으로 관리하는 것이 바로 이벤트 루프이다!
<span style="color: #ffb02e;">💁‍♀️ 자바스크립트에서 여러 작업을 동시에 처리하거나, 여러 작업 중 우선적으로 실행할 작업을 결정하는 관리자 역할을 하는 것이 &quot;이벤트 루프&quot; 이다.</span></p>
<p><br /><br /></p>
<h2 id="🟨-2-이벤트-루프">🟨 2. 이벤트 루프</h2>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/c058f644-3110-4312-b874-dae0f5426ccc/image.png" />자바스크립트는 위 이미지의 구조로 되어있고 Event Loop는 브라우저 내부의 Call Stack, Web APIs, Callback Queue 등의 요소들을 모니터링하며 비동기적으로 실행되는 작업을 관리하고, 이를 순서대로 처리하며 <span style="color: #ffb02e;"><strong>프로그램 실행 흐름을 제어</strong></span>한다.</p>
<ul>
<li>Heap : 선언한 변수, 함수와 같이 메모리가 할당 되는 저장 공간</li>
<li>Call Stack : 코드 실행을 위해 사용하는 메모리 공간 (코드가 쌓이는 공간)</li>
<li><span style="color: #ffb02e;"><strong>Web APIs</strong></span> : 자바스크립트 엔진이 아닌 브라우저에서 제공하는 API 모음으로, 비동기적으로 실행되는 작업(setTimeout, Promise 등)들을 전담하여 처리</li>
<li><span style="color: #ffb02e;"><strong>Callback Queue</strong></span> : 콜 스택에 있는 비동기적 작업이 완료되면 실행되는 함수들이 대기하는 공간<br />

</li>
</ul>
<h3 id="🔸-2-1-callback-queue-종류">🔸 2-1. Callback Queue 종류</h3>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/0b57cffa-7687-4f1e-8b60-5c8345425cbd/image.png" /></p>
<p>Callback Queue에는 macrotask queue(매크로 태스크 큐), microtask queue(마이크로 태스크 큐) 가 있다.</p>
<ul>
<li>macrotask queue : setTimeout, setInterval, fetch, addEventListener 와 같이 비동기로 처리되는 함수들의 콜백 함수가 들어가는 큐 </li>
<li>microtask queue : 우선 시작! promise.then, process.nextTick, MutationObserver 와 같이 우선적으로 비동기로 처리되는 함수들의 콜백 함수가 들어가는 큐</li>
</ul>
<p><span style="color: #ffb02e;">💁‍♀️ Animation Frames?</span></p>
<ul>
<li>animation frames (queue) : 브라우저 큐는 콜백 큐 이외에도 애니메이션 작업 처리를 담당하는 AnimationFrame Queue가 있다.자바스크립트 애니메이션 동작을 제어하는  requestAnimationFrame 메소드를 통해 콜백을 등록하면, 해당 큐에 적재되어 Repaint 작업 직전에 AnimaitionFrame Queue에 있는 작업들을 모두 처리한다.</li>
</ul>
<br />
⭐전체적인 이해를 위해 반드시 알아야하는 실행 순서!⭐<br />
<span style="color: #ffb02e;">실행 순서 : Microtask Queue > Animation Frame > Task Queue</span>

<p><br /><br /></p>
<h2 id="🟨-3-이벤트-루프-동작-과정">🟨 3. 이벤트 루프 동작 과정</h2>
<p><img alt="" src="https://blog.kakaocdn.net/dn/bfVyEB/btsvNysLSVD/Qg3G7SIl2KrYMdfslBw50k/img.gif" /></p>
<p>이벤트 루프는 비동기 작업을 Web API에 옮기고 작업이 완료되면 Queue에 적재했다가 Call Stack에 <strong>작업을 관리, 옮기는 역할</strong>을 한다.
Call Stack, Task Queue에 작업이 남아있는지 반복적으로 무한 루프하며 확인하기 때문에 <span style="color: #ffb02e;">이벤트 &quot;루프&quot;</span>이다.</p>
<h3 id="🔸-3-1-settimeout-동작-과정">🔸 3-1. setTimeOut 동작 과정</h3>
<pre><code>function bar() {
  setTimeout(() =&gt; {
      console.log(&quot;Second&quot;)
  }, 500);
}

function foo() {
  console.log(&quot;First&quot;);
}

function baz() {
  console.log(&quot;Third&quot;);
}

bar();
foo();
baz();

//노출 순서
First
Second
Third</code></pre><p>위 스크립트는 아래 코드 실행 과정으로 진행된다.
<img alt="" src="https://blog.kakaocdn.net/dn/PLDmM/btsae6cCQlI/hddR9cc75XkgnsO3EUqSoK/img.gif" /></p>
<ol>
<li>bar() 함수 호출 -&gt; setTimeout() -&gt; stack -&gt; 콜백 함수 -&gt; web api이동 타이머 진행</li>
<li>foo() 함수 호출 -&gt; stack -&gt; 콘솔 출력 <span style="color: #ffb02e;">First</span></li>
<li>5초 완료 시 web api 콜백 함수 -&gt; task queue 이동</li>
<li>baz() 함수 호출 -&gt; stack -&gt; 콘솔 출력 <span style="color: #ffb02e;">Second</span></li>
<li>이벤트 루프가 비어진 Call Stack 확인 후 task queue에 있던 콜백 함수를 Call Stack으로 이동</li>
<li>콘솔 출력 <span style="color: #ffb02e;">Third</span><br />


</li>
</ol>
<h3 id="🔸-3-2-promise-동작-과정">🔸 3-2. Promise 동작 과정</h3>
<p><span style="color: #ffb02e;">💁‍♀️ 코드와 gif를 비교하며 보면 이해가 훨씬 쉽다 ㅎ.ㅎ</span></p>
<pre><code>console.log('Start!');

setTimeout(() =&gt; {
    console.log('Timeout!');
}, 0);

Promise.resolve('Promise!').then(res =&gt; console.log(res));

console.log('End!');

//노출 순서
Start!
End!
Promise!
Timeout!</code></pre><ol>
<li>콘솔 코드 stack 적재 -&gt; 콘솔 출력 <span style="color: #ffb02e;">Start!</span>
<img alt="" src="https://blog.kakaocdn.net/dn/cuMsKp/btsvMFMyMIr/UMlnMLQdGZD71Q9DQTKDqk/img.gif" /></li>
<li>setTimeout -&gt; stack -&gt; 콜백 함수 -&gt; web api이동 타이머 진행 (0초라 바로 타이머 종료)
<img alt="" src="https://blog.kakaocdn.net/dn/bTgarW/btsajdaqFYo/GZo7cnWmdNj2ReoYZEQq31/img.gif" /></li>
<li><strong>이벤트 루프</strong>에 의해 setTimeout 콜백 함수는 MacroTask Queue 적재</li>
<li>Promise 코드 -&gt; stack -&gt; <strong>이벤트 루프</strong>에 의해 then 핸들러의 콜백 함수 MicroTask Queue 적재
<img alt="" src="https://blog.kakaocdn.net/dn/qU8M0/btsafe2PCgw/OJzzPhbPwnsknK065db4y0/img.gif" /></li>
<li>콘솔 코드 stack 적재 -&gt; 콘솔 출력 <span style="color: #ffb02e;">End!</span>
<img alt="" src="https://blog.kakaocdn.net/dn/bvPkz8/btsaepD56CQ/zebvq7iDfESjMcndjQwXok/img.gif" /></li>
<li>Call Stack에 동기 작업 없음 =&gt; 비워짐!</li>
<li><strong>이벤트 핸들러</strong>에 의해 queue에 있는 작업들을 stack으로 이동</li>
<li>항상 MicroTask Queue 작업 먼저 우선 처리 -&gt; 콘솔 출력 <span style="color: #ffb02e;">Promise!</span>
<img alt="" src="https://blog.kakaocdn.net/dn/bWjCGD/btsafqCaL58/24KWYAif1iBKJ5Ec0tE4dk/img.gif" /></li>
<li>MacroTask Queue -&gt; 콘솔 출력 <span style="color: #ffb02e;">Timeout!</span>
<img alt="" src="https://blog.kakaocdn.net/dn/tr16U/btsaibjF5gy/g3cKJDWWCoakGef1H30w41/img.gif" /></li>
</ol>
<br />

<h3 id="🔸-3-3-animation-frames-동작-과정">🔸 3-3. Animation Frames 동작 과정</h3>
<p>Animation Frames는 브라우저가 화면을 다시 그릴 때 실행되는 함수들을 담아두는 공간이다.</p>
<p><strong>👇requestAnimationFrame 메소드 예시</strong>
!codepen[seonhyungjo/embed/MRVPxL?default-tab=result]</p>
<p>Animation Frames의 실행 순서와 우선순위는 브라우저에 따라 다를 수 있으며, 이벤트 루프의 명세가 명확하게 정의되지 않은 부분이 있기 때문에 브라우저마다 동작이 다를 수 있다.
위 설명과 같이 <span style="color: #ffb02e;">Microtask Queue &gt; Animation Frame &gt; Task Queue 순서가 일반적</span>이지만, 항상 보장되는 것은 아니다.
특정 브라우저의 동작 방식이나 업데이트된 이벤트 루프에 따라 다를 수 있기에, 정확한 확인을 위해서는 크로스 브라우저 테스트가 필요하다.</p>
<p><strong>실제 브라우저 동작 예</strong></p>
<ul>
<li><strong>Chrome, Firefox</strong>: Microtask Queue가 비어있을 때, requestAnimationFrame 콜백이 실행된 후에 Task Queue가 처리</li>
<li><strong>Safari</strong>: 일부 경우 requestAnimationFrame 콜백이 Task Queue보다 먼저 실행될 수 있지만, 명확히 정의되지 않은 경우도 있다.</li>
</ul>
<br />
<span style="color: #ffb02e;">💁‍♀️ Animation Frames 동작 과정</span>

<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/c7919b65-c1bc-42b7-818d-64f7d04a76b0/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/ff03bcd9-1bd0-4502-aa0e-f35424720e81/image.png" /></p>
<ol>
<li>콘솔 출력 <span style="color: #ffb02e;">script start</span></li>
<li>setTimeout -&gt; stack -&gt; 콜백 함수 -&gt; web api이동 타이머 진행 (0초라 바로 타이머 종료)</li>
<li>Promise 코드 -&gt; stack -&gt; <strong>이벤트 루프</strong>에 의해 then 핸들러의 콜백 함수 “promise1” MicroTask Queue 적재</li>
<li>requestAnimationFrame 함수 -&gt; stack -&gt; <strong>이벤트 루프</strong>에 의해 콜백 함수 AnimationFrame 적재</li>
<li>콘솔 출력 <span style="color: #ffb02e;">script end</span></li>
<li>콘솔 출력 <span style="color: #ffb02e;">promise1</span></li>
<li>Promise 코드 -&gt; stack -&gt; <strong>이벤트 루프</strong>에 의해 then 핸들러의 콜백 함수 “promise2” MicroTask Queue 적재</li>
<li>콘솔 출력 <span style="color: #ffb02e;">promise2</span></li>
<li>콘솔 출력 <span style="color: #ffb02e;">animation</span></li>
<li>콘솔 출력 <span style="color: #ffb02e;">setTimeout</span></li>
</ol>
<br />

<h2 id="🟨-4-이벤트-루프-추천-사이트">🟨 4. 이벤트 루프 추천 사이트</h2>
<p>👩‍💻프엔이라면 반드시 알아야 할 이벤트 루프!
직접 코드를 써보고 조작해볼 수 있는 사이트와 함께 순서를 확인해보자</p>
<p><a href="http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7%21%21%21PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D"><strong>🔎직접 이벤트 루프 사용해보기</strong></a>
<a href="http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7%21%21%21PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D"><img alt="" src="https://velog.velcdn.com/images/sooozi/post/b1b52988-7805-423e-8be4-7b3e62953369/image.png" /></a></p>
<hr />
<p><img alt="" src="https://velog.velcdn.com/images/sooozi/post/67066427-358d-46da-bd57-8f724b5438c4/image.png" /></p>
<p>처음 이벤트 루프를 접했을 때는 동공지진이 왔었지만, 계속 반복해서 다양한 자료들을 찾아보니 점점 이해가 되었다! 역시 복습이 체고 🫶</p>
<p><br /><br /><br />
✅ 참고
<em><a href="https://inpa.tistory.com/entry/%F0%9F%94%84-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A3%A8%ED%94%84-%EA%B5%AC%EC%A1%B0-%EB%8F%99%EC%9E%91-%EC%9B%90%EB%A6%AC">https://inpa.tistory.com/entry/%F0%9F%94%84-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A3%A8%ED%94%84-%EA%B5%AC%EC%A1%B0-%EB%8F%99%EC%9E%91-%EC%9B%90%EB%A6%AC</a>
<a href="https://hudi.blog/async-javascript/">https://hudi.blog/async-javascript/</a>
_<a href="https://meetup.nhncloud.com/posts/89">https://meetup.nhncloud.com/posts/89</a></em>
<em><a href="https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/">https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/</a></em></p>