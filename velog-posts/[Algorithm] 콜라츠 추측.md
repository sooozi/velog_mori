<p>알고리즘 공부 시작! 콜라츠 추측 반으로 뽀개기 🐻‍❄️
<br /></p>
<hr />
<blockquote>
<h3 id="콜라츠-추측-콜라츠-수열"><strong>콜라츠 추측, 콜라츠 수열</strong></h3>
</blockquote>
<h2 id="🟨-1-콜라츠-추측이란">🟨 1. 콜라츠 추측이란?</h2>
<p><span style="color: #ffb02e;">💁‍♀️ 콜라츠 추측</span>
1937년 Collatz란 사람에 의해 제기된 이 추측은,
<strong>주어진 수가 1이 될 때까지 다음 작업을 반복하면, 모든 수를 1로 만들 수 있다는 추측</strong>이다.
콜라츠 추측은 특정 수를 가지고 어떤 과정을 반복했을 때 항상 1에 도달한다는 이론적 주장!
콜라츠 수열은 그 과정을 실제로 나타내는 수열!</p>
<p><span style="color: #ffb02e;">💁‍♀️ 콜라츠 추측 규칙</span>
1-1. 입력된 수가 짝수라면 2로 나눈다. <strong>n=n/2</strong>
1-2. 입력된 수가 홀수라면 3을 곱하고 1을 더한다. <strong>n=3n+1</strong>
2. 결과로 나온 수에 같은 작업을 1이 될 때까지 반복한다. <strong>n=1에 도달할 때까지 반복</strong>
<br /></p>
<h2 id="🟨-2-콜라츠-추측-in-코테">🟨 2. 콜라츠 추측 in 코테</h2>
<p>콜라츠 추측을 구현하는 과정에서 콜라츠 수열을 사용할 때 중요한 포인트는 <strong>재귀 함수와 반복문</strong>이다!</p>
<ol>
<li><p><span style="color: #ffb02e;">재귀 함수, 반복문</span>
간단한 규칙에 따라 수를 변환하며 반복하기 때문에 구현 과정에서 재귀 함수, 반복문을 사용한다.</p>
</li>
<li><p><span style="color: #ffb02e;">짝수, 홀수 조건</span>
주어진 수가 짝수, 홀수에 따라 다른 계산법이 적용되기 때문에 조건문을 사용한다.</p>
</li>
</ol>
<br />
🧡 꼭 기억하기 🧡

<ul>
<li>n이 1이 되기까지 몇 번이 걸리는지</li>
<li>입력된 수가 2개일 때, 겹치는 숫자 알아내기 (객체로 순서와 숫자 뽑아내기)</li>
</ul>
<br />         

<h2 id="🟨-3-예시">🟨 3. 예시</h2>
<p><span style="color: #ffb02e;">📝 문제</span>
콜라츠 추측에 따르면, 주어진 자연수 n에 대해 다음의 과정을 반복하면 언젠가 1에 도달하게 됩니다.</p>
<ol>
<li>n이 짝수이면, n을 2로 나눕니다.</li>
<li>n이 홀수이면, n에 3을 곱하고 1을 더합니다.</li>
<li>이 과정을 반복하여 n이 1이 되면 종료합니다.</li>
</ol>
<p>자연수 6이 주어졌을 때, 콜라츠 추측을 따라 1에 도달하기까지 몇 번의 연산이 필요한지를 계산하는 함수를 작성하세요.</p>
<p><span style="color: #ffb02e;">✏️ 풀이</span></p>
<p>✅ while 반복문</p>
<pre><code class="language-jsx">function collatzSteps(n) {
    let steps = 0;
    while (n !== 1) {
        if (n % 2 === 0) {
            n /= 2;  // 짝수일 경우 2로 나눔
        } else {
            n = 3 * n + 1;  // 홀수일 경우 3을 곱하고 1을 더함
        }
        steps++;  // 연산 횟수 증가
    }
    return steps;
}

const n1 = 6;
console.log(collatzSteps(n1));  // 출력: 8

// 추가 설명
//n=6일 때: 6 → 3 → 10 → 5 → 16 → 8 → 4 → 2 → 1 (총 8번의 과정)</code></pre>
<br />

<p>✅ 재귀 함수</p>
<pre><code>재귀 함수 : 함수가 자기 자신을 호출</code></pre><ol>
<li>기본 사례 : n이 1면 연산 stop</li>
<li>재귀 사례 : n이 1이 아니라면, n이 짝수 또는 홀수일 경우로 나누어 재귀 호출 수행<pre><code class="language-jsx">function collatzSteps(n) {
 if (n === 1) {
     return 0;  // 기본 사례: 1에 도달했으므로 연산 횟수는 0
 }
 if (n % 2 === 0) {
     return 1 + collatzSteps(n / 2);  // 짝수인 경우, 2로 나누고 재귀 호출
       //1 + 하는 이유 : 
       //현재 단계에서 수행된 연산을 포함하고 이후 연산 횟수를 누적해 전체 연산 횟수를 계산
 } else {
     return 1 + collatzSteps(3 * n + 1);  // 홀수인 경우, 3을 곱하고 1을 더하고 재귀 호출
 }
}
</code></pre>
</li>
</ol>
<p>// 예시 사용
console.log(collatzSteps(6));  // 출력: 8</p>
<p>```</p>
<br />              


<h2 id="🟨-4-문제-추천">🟨 4. 문제 추천</h2>
<p>난이도에 따라 <strong>프로그래머스 &gt; 백준</strong> 순서대로 문제 풀기를 추천!</p>
<p><span style="color: #ffb02e;">프로그래머스</span></p>
<ul>
<li>콜라츠 수열 만들기
<a href="https://velog.io/@sooozi/Programmers-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%88%98%EC%97%B4-%EB%A7%8C%EB%93%A4%EA%B8%B0">https://velog.io/@sooozi/Programmers-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%88%98%EC%97%B4-%EB%A7%8C%EB%93%A4%EA%B8%B0</a></li>
<li>콜라츠 추측
<a href="https://velog.io/@sooozi/Programmers-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%B6%94%EC%B8%A1">https://velog.io/@sooozi/Programmers-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%B6%94%EC%B8%A1</a></li>
</ul>
<p><span style="color: #ffb02e;">백준</span></p>
<ul>
<li>콜라츠 추측
<a href="https://velog.io/@sooozi/Baekjoon-10926-nr93l32f">https://velog.io/@sooozi/Baekjoon-10926-nr93l32f</a></li>
<li>콜라츠 (콜라츠를 활용한 문제)
<a href="https://velog.io/@sooozi/Baekjoon-5393.-%EC%BD%9C%EB%9D%BC%EC%B8%A0">https://velog.io/@sooozi/Baekjoon-5393.-%EC%BD%9C%EB%9D%BC%EC%B8%A0</a></li>
</ul>
<p><br /><br />      </p>
<hr />
<p><br /><br /><br /><img alt="" src="https://velog.velcdn.com/images/sooozi/post/4f5ea979-6725-47a2-876a-d83c1e44c8b3/image.png" /></p>
<p>아직 더 많은 알고리즘이 남아있는고야~
화이탱탱탱🫶</p>
<p><br /><br /><br />
✅ 참고
<em><a href="https://jindo1801.tistory.com/entry/%EC%89%AC%EC%9B%8C%EB%B3%B4%EC%9D%B4%EB%8A%94%EB%8D%B0-%EC%95%84%EB%AC%B4%EB%8F%84-%EB%AA%BB%ED%91%B8%EB%8A%94-%EB%AC%B8%EC%A0%9C-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%B6%94%EC%B8%A1">https://jindo1801.tistory.com/entry/%EC%89%AC%EC%9B%8C%EB%B3%B4%EC%9D%B4%EB%8A%94%EB%8D%B0-%EC%95%84%EB%AC%B4%EB%8F%84-%EB%AA%BB%ED%91%B8%EB%8A%94-%EB%AC%B8%EC%A0%9C-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%B6%94%EC%B8%A1</a>
<a href="https://namu.wiki/w/%EC%BD%9C%EB%9D%BC%EC%B8%A0%20%EC%B6%94%EC%B8%A1">https://namu.wiki/w/%EC%BD%9C%EB%9D%BC%EC%B8%A0%20%EC%B6%94%EC%B8%A1</a>
<a href="https://ko.wikipedia.org/wiki/%EC%BD%9C%EB%9D%BC%EC%B8%A0">https://ko.wikipedia.org/wiki/%EC%BD%9C%EB%9D%BC%EC%B8%A0</a></em>%EC%B6%94%EC%B8%A1
<a href="https://velog.io/@dongjun187/%EC%9E%AC%EA%B7%80-%ED%95%A8%EC%88%98Recursion-Function%EC%9D%98-%EC%9E%A5%EC%A0%90%EA%B3%BC-%EB%8B%A8%EC%A0%90">https://velog.io/@dongjun187/%EC%9E%AC%EA%B7%80-%ED%95%A8%EC%88%98Recursion-Function%EC%9D%98-%EC%9E%A5%EC%A0%90%EA%B3%BC-%EB%8B%A8%EC%A0%90</a>_</p>