# 📘 **리액트 컴포넌트 & Props 레포트**

## 1. 컴포넌트(Component)란 무엇인가?

리액트에서 컴포넌트는 **입력(props)을 받아 출력(React Element)을 반환하는 독립적인 UI 조각**이다.  
문서에서도 다음과 같이 설명한다:

> “Component : 입력(props)을 받아 출력(Element) 하는 역할”  
> “리액트는 모든 페이지가 Component로 구성되어 있고… 레고 블록을 조립하듯 끼워 맞춰 새로운 Component를 만들 수 있다.”

즉, 컴포넌트는 웹 페이지를 구성하는 퍼즐 조각이며, 재사용성과 독립성이 매우 높다.

---

## 2. 리액트 컴포넌트의 종류

리액트 컴포넌트는 크게 두 가지로 나뉜다.

### 2.1 Function Component
가장 기본적이고 간단한 형태.

```jsx
function Welcome(props) {
  return <h1>안녕, {props.name}</h1>;
}
```

문서에서는 다음과 같이 설명한다:

> “React Component는 pure 함수 같은 역할을 해야 한다.”

### 2.2 Class Component
ES6 class 문법을 사용하며, 추가 기능(state 등)을 포함할 수 있다.

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>안녕, {this.props.name}</h1>;
  }
}
```

---

## 3. 컴포넌트 이름 규칙

문서에서 강조한 핵심 규칙:

> “Component의 이름은 항상 대문자로 시작해야 한다.”

소문자로 시작하면 HTML 태그로 인식되기 때문이다.

---

## 4. Props(프로퍼티)

Props는 **부모 컴포넌트가 자식 컴포넌트에게 전달하는 데이터**이다.

문서에서는 다음과 같이 정의한다:

> “상위 컴포넌트가 하위 컴포넌트에 값을 전달할 때 사용한다.”  
> “프로퍼티는 수정할 수 없다는 특징이 있다.”

### 4.1 기본 사용 예시

```jsx
<MyComponent name="React" />
```

MyComponent 내부에서는 다음처럼 사용:

```jsx
props.name
```

---

## 5. 다양한 Props 전달 방식

### 5.1 문자열 Props
```jsx
<Main name="홍길동" />
```

### 5.2 숫자 Props
문서에서 강조:

> “문자열 이외에는 중괄호({ }) 사용”

```jsx
<Main name={9} />
```

### 5.3 여러 개의 Props 전달
```jsx
<Main name="갓대희" color="blue" />
```

### 5.4 Boolean Props
```jsx
<Main maleYn />
```

문서 설명:

> “mailYn을 생략하면 false로 처리한다.”

---

## 6. PropTypes를 이용한 타입 정의

문서에서는 다음과 같이 설명한다:

> “프로퍼티의 자료형을 미리 선언할 수 있다… 버그 예방에 도움이 된다.”

예시:

```jsx
Main.propTypes = {
  name: PropTypes.string
};
```

### 기본값 설정(defaultProps)

```jsx
Main.defaultProps = {
  name: '디폴트'
};
```

---

## 7. props.children 활용

Wrapper 컴포넌트처럼 **자식 요소를 감싸는 컴포넌트**를 만들 때 사용한다.

문서 인용:

> “children을 사용하여 내부에 있는 내용을 표현할 수 있다.”

예시:

```jsx
<Wrapper>
  <Main />
</Wrapper>
```

Wrapper 내부:

```jsx
{props.children}
```

---

## 8. 이미지·텍스트 출력 컴포넌트 예시

문서에서는 이미지 파일명을 props로 받아 URL을 구성하는 컴포넌트를 소개한다.

예:

```jsx
<FPhotoText image="desktop" label="Desktop" />
```

컴포넌트 내부:

```jsx
const url = "img/" + props.image + ".png";
```

---

## 9. 리스트 컴포넌트 예시

문서에서는 문자열을 split하여 리스트를 만드는 컴포넌트를 소개한다.

```jsx
const items = this.props.items.split(",");
```

---

## 10. 컴포넌트 추출(Component Extraction)

문서에서는 Comment → UserInfo → Avatar 구조로 컴포넌트를 분리하는 예시를 보여준다.

핵심 문장:

> “기능 단위, 재사용 가능 여부로 추출”
