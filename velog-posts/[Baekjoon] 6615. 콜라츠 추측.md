<p>문제 링크
<a href="https://www.acmicpc.net/problem/6615">https://www.acmicpc.net/problem/6615</a></p>
<h1 id="problem-💻">Problem 💻</h1>
<hr />
<h2 id="문제">문제</h2>
<p>콜라츠 추측은 흥미로운 현상이다. 이 법칙은 간단해보이지만, 수학적으로 아직까지 증명되어있지 않은 문제이다. 우리는 이 추측이 옳다고 받아들이겠다.</p>
<p>콜라츠 추측을 설명하면 다음과 같다. 우선 다음과 같은 양의 정수 수열 xi 를 생각하자.</p>
<ul>
<li><p>만약 x 가 짝수이면, x=x/2</p>
<p>  i</p>
<p>  i+1</p>
<p>  i</p>
</li>
<li><p>만약 x 가 홀수이면, x=3*x+1 이다.</p>
<p>  i</p>
<p>  i+1</p>
<p>  i</p>
</li>
</ul>
<p>콜라츠 추측은 이렇게 만든 수열은 결국 1이 된다는 것이다.</p>
<p>과학자들은, 컴퓨터를 이용하여 첫 번째 수열이 258 보다 작으면, 이 추측은 참이라고 증명했다.</p>
<p>이제 문제를 보자.</p>
<p>두개의 양의 정수를 준다. 각각의 수에 대해서 콜라츠 추측으로 만든 수열을 생각하자.</p>
<p>각각의 수열을 비교하였을때 처음으로 같은 숫자가 나왔을때 , 각각 몇번째 수열에서 만나는지 구해본다. 문제의 편의를 위해, 이 수열은 1이 나오면 더이상 진행하지 않는다고 하자. ( 1 다음에 나올 수열을 생각하면, 1, 4, 2, 1, 4, 2, 1로 반복되기 때문이다.)</p>
<h2 id="입력">입력</h2>
<p>입력은 몇개의 테스트 케이스로 구성된다. 각 테스트 케이스는 두개의 정수 A와 B가 주어진다. ( 1 ≤ A, B ≤ 1,000,000) 마지막 줄은 두개의 0으로 구성된다.</p>
<h2 id="출력">출력</h2>
<p>각각의 테스트 케이스마다 다음과 같은 문장을 한줄에 출력한다.</p>
<p>&quot;A needs SA steps, B needs SB steps, they meet at C&quot;</p>
<p>SA와 SB는 A와 B로 수열을 만들고, 처음으로 같은 숫자 C가 나왔을때 각각의 수열에서 몇번째 인지 알려주는 숫자이다.</p>
<h2 id="출력-예시">출력 예시</h2>
<h2 id="예제-입력">예제 입력</h2>
<pre><code>7 8
27 30
0 0</code></pre><h2 id="예제-출력">예제 출력</h2>
<pre><code>7 needs 13 steps, 8 needs 0 steps, they meet at 8
27 needs 95 steps, 30 needs 2 steps, they meet at 46</code></pre><h2 id="예제-풀이">예제 풀이</h2>
<h3 id="처리-과정">처리 과정</h3>
<h3 id="첫-번째-테스트-케이스-7-8">첫 번째 테스트 케이스: <code>7 8</code></h3>
<ol>
<li><strong>콜라츠 수열 생성</strong>:<ul>
<li><strong>수 7의 콜라츠 수열</strong>:<ul>
<li>7 (홀수) → 3 * 7 + 1 = 22</li>
<li>22 (짝수) → 22 / 2 = 11</li>
<li>11 (홀수) → 3 * 11 + 1 = 34</li>
<li>34 (짝수) → 34 / 2 = 17</li>
<li>17 (홀수) → 3 * 17 + 1 = 52</li>
<li>52 (짝수) → 52 / 2 = 26</li>
<li>26 (짝수) → 26 / 2 = 13</li>
<li>13 (홀수) → 3 * 13 + 1 = 40</li>
<li>40 (짝수) → 40 / 2 = 20</li>
<li>20 (짝수) → 20 / 2 = 10</li>
<li>10 (짝수) → 10 / 2 = 5</li>
<li>5 (홀수) → 3 * 5 + 1 = 16</li>
<li>16 (짝수) → 16 / 2 = 8</li>
<li>8 (짝수) → 8 / 2 = 4</li>
<li>4 (짝수) → 4 / 2 = 2</li>
<li>2 (짝수) → 2 / 2 = 1</li>
<li>수열: 7 → 22 → 11 → 34 → 17 → 52 → 26 → 13 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1</li>
</ul>
</li>
<li><strong>수 8의 콜라츠 수열</strong>:<ul>
<li>8 (짝수) → 8 / 2 = 4</li>
<li>4 (짝수) → 4 / 2 = 2</li>
<li>2 (짝수) → 2 / 2 = 1</li>
<li>수열: 8 → 4 → 2 → 1</li>
</ul>
</li>
<li><strong>만나는 숫자</strong>:<ul>
<li>두 수열에서 첫 번째로 만나는 공통 숫자는 <code>8</code>입니다.</li>
<li>수 7의 수열에서 8은 13번째 단계에서 나타납니다.</li>
<li>수 8의 수열에서 8은 0번째 단계에서 나타납니다.</li>
</ul>
</li>
</ul>
</li>
<li><strong>결과</strong>:<ul>
<li>&quot;7 needs 13 steps, 8 needs 0 steps, they meet at 8&quot;</li>
</ul>
</li>
</ol>
<h3 id="두-번째-테스트-케이스-27-30">두 번째 테스트 케이스: <code>27 30</code></h3>
<ol>
<li><strong>콜라츠 수열 생성</strong>:<ul>
<li><strong>수 27의 콜라츠 수열</strong> (생략된 단계 포함):<ul>
<li>27 → 82 → 41 → 124 → 62 → 31 → 94 → 47 → 142 → 71 → 214 → 107 → 322 → 161 → 484 → 242 → 121 → 364 → 182 → 91 → 274 → 137 → 412 → 206 → 103 → 310 → 155 → 466 → 233 → 700 → 350 → 175 → 526 → 263 → 790 → 395 → 1186 → 593 → 1780 → 890 → 445 → 1336 → 668 → 334 → 167 → 502 → 251 → 754 → 377 → 1132 → 566 → 283 → 850 → 425 → 1276 → 638 → 319 → 958 → 479 → 1438 → 719 → 2158 → 1079 → 3238 → 1619 → 4858 → 2429 → 7288 → 3644 → 1822 → 911 → 2734 → 1367 → 4102 → 2051 → 6154 → 3077 → 9232 → 4616 → 2308 → 1154 → 577 → 1732 → 866 → 433 → 1300 → 650 → 325 → 976 → 488 → 244 → 122 → 61 → 184 → 92 → 46 → 23 → 70 → 35 → 106 → 53 → 160 → 80 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1</li>
</ul>
</li>
<li><strong>수 30의 콜라츠 수열</strong>:<ul>
<li>30 → 15 → 46 → 23 → 70 → 35 → 106 → 53 → 160 → 80 → 40 → 20 → 10 → 5 → 16 → 8 → 4 → 2 → 1</li>
</ul>
</li>
<li><strong>만나는 숫자</strong>:<ul>
<li>두 수열에서 첫 번째로 만나는 공통 숫자는 <code>46</code>입니다.</li>
<li>수 27의 수열에서 46은 95번째 단계에서 나타납니다.</li>
<li>수 30의 수열에서 46은 2번째 단계에서 나타납니다.</li>
</ul>
</li>
</ul>
</li>
<li><strong>결과</strong>:<ul>
<li>&quot;27 needs 95 steps, 30 needs 2 steps, they meet at 46&quot;</li>
</ul>
</li>
</ol>
<h3 id="최종-출력">최종 출력</h3>
<pre><code>코드 복사
7 needs 13 steps, 8 needs 0 steps, they meet at 8
27 needs 95 steps, 30 needs 2 steps, they meet at 46
</code></pre><hr />
<h1 id="approach">Approach</h1>
<h3 id="알고리즘">알고리즘</h3>
<blockquote>
<p>입력 → 콜라츠 수열 생성 → 수열 비교 → 출력</p>
</blockquote>
<h3 id="의문점">의문점</h3>
<ul>
<li>문제 접근<ol>
<li><strong>콜라츠 수열 생성</strong>:<ul>
<li>주어진 수가 짝수이면, 수를 2로 나눈다.</li>
<li>주어진 수가 홀수이면, 수에 3을 곱하고 1을 더한다.</li>
<li>이 과정을 수가 1이 될 때까지 반복한다.</li>
</ul>
</li>
<li><strong>수열 비교</strong>:<ul>
<li>두 수로부터 각각 콜라츠 수열을 생성한다.</li>
<li>두 수열에서 처음으로 공통되는 숫자를 찾는다.</li>
<li>공통 숫자를 찾을 때, 각각의 수열에서 이 숫자가 나타나는 위치(단계)를 기록한다.</li>
</ul>
</li>
</ol>
</li>
<li>해결 방법<ol>
<li><strong>수열 계산 및 저장</strong>:<ul>
<li>주어진 두 수에 대해 콜라츠 수열을 생성한다.</li>
<li>각 수열을 딕셔너리로 저장하여 빠르게 찾을 수 있게 한다. 이 딕셔너리의 키는 수열의 값, 값은 해당 값이 나타난 단계이다.</li>
</ul>
</li>
<li><strong>수열 비교</strong>:<ul>
<li>두 수열을 동시에 탐색하면서 첫 번째로 만나는 공통 숫자를 찾는다.</li>
</ul>
</li>
</ol>
</li>
</ul>
<hr />
<h3 id="요약">요약</h3>
<ul>
<li><p>콜라츠 수열</p>
<p>  : 주어진 수로부터 시작하여 수열을 생성하는 과정 / 콜라츠 추측을 실험적으로 검증하는 데 사용</p>
<ul>
<li><strong>규칙</strong><ul>
<li>주어진 수가 짝수이면, 다음 수는 현재 수를 2로 나눈 값입니다.</li>
<li>주어진 수가 홀수이면, 다음 수는 현재 수를 3배한 후 1을 더한 값입니다.</li>
</ul>
</li>
</ul>
</li>
<li><p>콜라츠 추측</p>
<p>  : 모든 양의 정수에 대해 콜라츠 수열을 반복하면 결국 1에 도달한다는 수학적 추측</p>
<p>  : 콜라츠 수열의 모든 경우가 1에 도달한다!!!! (주장쓰)</p>
</li>
<li><p>💁‍♀️ 그래서 뭐가 중헌디?</p>
<ul>
<li>콜라츠 수열 문제 : 주어진 숫자에 대해 수열을 생성하는 과정에 초점</li>
<li>콜라츠 추측 문제 : 모든 양의 정수에 대해 수열이 1에 도달한다는 이론적 주장에 초점</li>
</ul>
</li>
</ul>
<hr />
<h1 id="solution-💡">Solution 💡</h1>
<pre><code class="language-jsx">const num = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

// [**콜라츠 수열을 생성]** 각 숫자가 등장하는 단계를 기록하는 함수
function collatzSteps(x) {
    const steps = new Map(); // 숫자와 그 숫자가 등장하는 단계를 저장할 맵
    let step = 0; // 현재 단계
    while (x !== 1) { // 수열이 1이 될 때까지 반복
        if (steps.has(x)) break; // 이미 처리된 숫자라면 반복 종료
        steps.set(x, step++); // 현재 숫자와 단계 저장 후 단계 증가
        if (x % 2 === 0) x /= 2; // 짝수인 경우, 2로 나누기
        else x = 3 * x + 1; // 홀수인 경우, 3배 후 1 더하기
    }
    steps.set(1, step++); // 1도 수열의 마지막에 포함시킴
    return steps; // 단계 정보를 담고 있는 맵을 반환
}

//collatzSteps(3)
//{
//    3: 0,
//    10: 1,
//    5: 2,
//    16: 3,
//    8: 4,
//    4: 5,
//    2: 6,
//    1: 7
//}

// [**수열 비교]** 두 수의 콜라츠 수열에서 만나는 첫 공통 숫자와 단계 정보를 찾는 함수
function findMeetingPoint(a, b) {
    const aSteps = collatzSteps(a); // 수 a의 콜라츠 수열 단계 정보를 얻음
    const bSteps = collatzSteps(b); // 수 b의 콜라츠 수열 단계 정보를 얻음

    let meetingValue = -1; // 두 수열에서 만나는 숫자 (-1은 유효한 콜라츠 수열이 아님! 공통 숫자가 수열에서 발견되지 않음을 의미)
    let aStepIndex = 0; // 수 a의 수열에서 공통 숫자의 단계 (0은 공통 숫자가 발견되지 않았을 때의 기본값, 수열은 0부터 시작)
    let bStepIndex = 0; // 수 b의 수열에서 공통 숫자의 단계

    // 수 a의 수열에서 각 숫자를 확인하면서 수 b의 수열에서도 존재하는지 체크
    for (const [key, value] of aSteps.entries()) {
        if (bSteps.has(key)) { // 수 b의 수열에서도 숫자 존재 확인
            meetingValue = key; // 공통 숫자 저장
            aStepIndex = value; // 수 a에서의 단계 저장
            bStepIndex = bSteps.get(key); // 수 b에서의 단계 저장 / bSteps 맵에서 key에 해당하는 값(value) 가져오기 /Map 객체의 get() 메서드
            break; // 첫 번째 공통 숫자를 찾았으므로 반복 종료
        }
    }

    return { aStepIndex, bStepIndex, meetingValue }; // 결과 반환
}

const results = []; // 결과를 저장할 배열

// 각 입력 줄을 처리
for (const line of num) {
    const [A, B] = line.split(' ').map(Number); // 입력값을 숫자로 변환
    if (A === 0 &amp;&amp; B === 0) break; // 종료 조건 (0 0을 만나면 반복 종료)
    const { aStepIndex, bStepIndex, meetingValue } = findMeetingPoint(A, B); // 공통 숫자와 단계 정보 얻기
    results.push(`${A} needs ${aStepIndex} steps, ${B} needs ${bStepIndex} steps, they meet at ${meetingValue}`); // 결과 포맷에 맞게 저장
}

// 모든 결과를 줄바꿈으로 연결하여 출력
console.log(results.join('\n'));</code></pre>
<hr />
<h1 id="reference-📄">Reference 📄</h1>
<p><a href="https://measurezero.tistory.com/12">[BOJ 5393 // C++] 콜라츠</a></p>
<p><a href="https://yhc509.tistory.com/65">[Baekjoon] 5393 콜라츠</a></p>
<p><a href="https://jindo1801.tistory.com/entry/%EC%89%AC%EC%9B%8C%EB%B3%B4%EC%9D%B4%EB%8A%94%EB%8D%B0-%EC%95%84%EB%AC%B4%EB%8F%84-%EB%AA%BB%ED%91%B8%EB%8A%94-%EB%AC%B8%EC%A0%9C-%EC%BD%9C%EB%9D%BC%EC%B8%A0-%EC%B6%94%EC%B8%A1#google_vignette">쉬워보이는데 아무도 못푸는 문제 (콜라츠 추측)</a></p>
<p><a href="https://ko.javascript.info/map-set">맵과 셋</a></p>
<p><a href="https://ko.javascript.info/keys-values-entries">Object.keys, values, entries</a></p>