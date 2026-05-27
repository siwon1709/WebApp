1. 핵심 개념 요약
State 정의

컴포넌트 내부에서 관리되는 변경 가능한 데이터

값이 변하면 자동으로 재렌더링 발생

일반 변수와 달리 UI와 연결되어 화면에 반영됨

State 사용 이유

일반 변수는 값이 변해도 화면이 갱신되지 않음

useState를 사용하면 값 변경 시 UI가 자동 업데이트

setState 특징

비동기적 동작 → 여러 업데이트를 모아 batch update 처리

같은 키 값은 마지막 값으로 덮어씌워짐

최신 값을 반영하려면 업데이터 함수(setCount(prev => prev+1)) 사용

2. 함수형 vs 클래스형 컴포넌트
함수형 컴포넌트

useState Hook으로 상태 관리

간결하고 직관적

클래스형 컴포넌트

constructor에서 this.state 초기화

값 변경은 반드시 this.setState() 사용

직접 this.state 수정은 금지

3. Event Handling
JSX 이벤트 문법

카멜케이스 사용 (onClick, onChange)

문자열이 아닌 함수 전달

예시

버튼 클릭 시 카운트 증가

체크박스 상태 관리

객체/배열 상태 업데이트 시 spread 연산자 활용

4. 주요 코드 예시
jsx
// 함수형 컴포넌트 카운터
import { useState } from 'react';
const Counter = () => {
  const [count, setCount] = useState(0);
  return (
    <div>
      <h2>{count}</h2>
      <button onClick={() => setCount(count+1)}>+</button>
      <button onClick={() => setCount(count-1)}>-</button>
    </div>
  );
};
5. 학습 포인트
State는 UI와 데이터 흐름을 연결하는 핵심 개념

비동기적 업데이트와 업데이터 함수 활용이 중요

클래스형과 함수형의 차이를 이해하고, 현대 React에서는 Hook 기반 함수형 컴포넌트가 주류
