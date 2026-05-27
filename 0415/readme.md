1. Hook 등장 배경
과거: 클래스형 컴포넌트만 상태와 생명주기 관리 가능

문제점: 코드 복잡, 재사용성 낮음, 최적화 어려움

해결책: React v16.8에서 Hook 도입 → 함수형 컴포넌트에서도 상태 관리 가능

2. Hook 개요
React Hook: 함수형 컴포넌트에서 상태와 생명주기 기능 제공

대표 Hook: useState, useEffect, useContext, useRef 등

모든 Hook 이름은 use로 시작

3. Hook 규칙
최상위 레벨에서만 호출 (조건문, 반복문, 이벤트 핸들러 내부 X)

React 함수 컴포넌트 또는 Custom Hook에서만 호출 가능

Linter 플러그인으로 규칙 자동 강제

4. useState 상세
기본 문법

jsx
const [state, setState] = useState(initialValue);
특징

배열 구조 분해 할당으로 값과 setter 함수 반환

setter 함수 호출 시 컴포넌트 리렌더링 발생

동일 값이면 최적화로 리렌더링 생략

5. useState 활용 예시
숫자 카운터

jsx
const [count, setCount] = useState(0);
<button onClick={() => setCount(count+1)}>+</button>
문자열 입력

jsx
const [text, setText] = useState("hello");
<input value={text} onChange={e => setText(e.target.value)} />
객체 상태 관리 (spread 활용)

jsx
setForm({
  ...form,
  firstName: e.target.value
});
배열 상태 관리

jsx
setTodos(todos.filter(t => t.id !== todoId));
업데이터 함수 활용

jsx
setAge(prev => prev+1);
6. 고급 활용
중첩 객체 업데이트: 상위 객체까지 복사 후 교체

Immer 라이브러리: 불변성 유지하면서 간결한 코드 작성 가능

7. 학습 포인트
Hook은 함수형 컴포넌트의 상태 관리 혁신

useState는 가장 기본적이고 중요한 Hook

객체·배열 상태 업데이트 시 불변성 유지 필수

최신 React 개발은 Hook 중심 패러다임
