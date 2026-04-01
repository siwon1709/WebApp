# 📘 Web Programming Report (Part 2)  
### ― React, Virtual DOM, Rendering, 개발환경, 프로젝트 구조 ―

## 1. React란 무엇인가?
React는 사용자 인터페이스(UI)를 만들기 위한 JavaScript 라이브러리로, 2013년 Facebook이 발표한 오픈소스 프레임워크이다. 문서에서는 React를 “사용자 인터페이스를 구축하기 위한 선언적이고 효율적이며 유연한 Javascript 라이브러리”라고 설명한다.

React의 핵심 특징은 다음과 같다.

- **컴포넌트 기반 구조**  
  작은 단위의 컴포넌트를 조합하여 복잡한 UI를 구성한다.
- **Virtual DOM 기반 렌더링**  
  변경된 부분만 효율적으로 업데이트하여 성능을 향상한다.
- **JSX(JavaScript XML)**  
  HTML과 유사한 문법을 JavaScript 안에서 사용할 수 있게 한다.
- **SPA(Single Page Application) 개발에 최적화**

---

## 2. React의 장점
문서에서는 React의 장점을 10가지로 정리하고 있다.

- 완성도 높은 개발 워크플로우
- 유연성과 호환성
- 컴포넌트 재사용성
- Virtual DOM 기반 고성능
- Flux/Redux를 통한 상태 관리
- 다양한 개발 도구 제공
- React Native로 모바일 개발 가능
- 거대한 커뮤니티
- JSX 문법 지원
- React Hooks 제공

React는 Netflix, Twitter, Airbnb, PayPal 등 다양한 글로벌 기업에서 사용되고 있다.

---

## 3. 브라우저 로딩 과정(Rendering Pipeline)
문서에서는 브라우저 렌더링 과정을 다음 5단계로 설명한다.

### 1) 파싱(Parsing)
HTML과 CSS를 파싱하여 각각 **DOM Tree**, **CSSOM Tree**를 생성한다.

### 2) 스타일(Style)
DOM과 CSSOM을 결합하여 **Render Tree**를 구성한다.  
문서에서는 “렌더링 트리에는 페이지를 렌더링하는 데 필요한 노드만 포함”된다고 설명한다.

### 3) 레이아웃(Layout)
각 요소의 크기와 위치를 계산한다.

### 4) 페인트(Paint)
계산된 스타일을 실제 픽셀로 그린다.

### 5) 합성(Compositing)
Transform, opacity 등 GPU 가속이 필요한 요소를 레이어로 합성한다.

---

## 4. DOM, CSSOM, Render Tree
문서에서는 HTML과 CSS가 어떻게 구조화되는지 예시를 통해 설명한다.

### DOM Tree
HTML을 파싱하여 생성된 트리 구조.  
예시 문장: “StartTag: html → StartTag: head → … → Nodes: html, head, meta, body…”

### CSSOM Tree
CSS 규칙을 파싱하여 생성된 스타일 트리.  
예시 규칙:  
- `body { font-size: 16px }`  
- `span { color: red }`  
- `p span { display: none }`

### Render Tree
DOM + CSSOM을 결합하여 화면에 필요한 요소만 포함한 트리.

---

## 5. Virtual DOM
문서에서는 Virtual DOM을 다음과 같이 설명한다.

> “구 가상돔(Old Node)과 새 가상돔(New Node)을 비교하여 변경된 내용만 DOM에 적용한다.”

Virtual DOM의 핵심 과정:

1. 상태 변경 발생
2. 새로운 Virtual DOM 생성
3. 기존 Virtual DOM과 비교(diffing)
4. 변경된 부분만 실제 DOM에 반영(patching)

이를 통해 전체 렌더링 비용을 줄이고 성능을 향상한다.

---

## 6. Real DOM vs Virtual DOM
문서에서는 실제 DOM 구조와 Virtual DOM 객체 구조를 비교하며, Virtual DOM이 어떻게 JavaScript 객체 형태로 UI를 표현하는지 보여준다.

예시 Virtual DOM 코드:

```js
virtualDom('div', { id: 'app' },
  virtualDom('ul', null,
    virtualDom('li', null,
      virtualDom('input', { type: 'checkbox', className: 'toggle' }),
      'todo list item 1',
      virtualDom('button', { className: 'remove' }, 'I ')
    )
  )
);
```

---

## 7. React 개발 환경

### 필수 도구
| 프로그램 | 용도 | 비고 |
|---------|------|------|
| Node.js | 웹 서버 개발 플랫폼 | 필수 |
| VSCode | 코드 편집기 | 권장 |
| Chrome | 브라우저 | 권장 |
| Scoop/Homebrew | 패키지 매니저 | 선택 |

Node.js는 **14.0.0 이상**, npm은 **5.6 이상** 필요.

---

## 8. npm, npx, nvm, yarn

- **npm**: Node 패키지 관리자  
- **npx**: 패키지를 설치하지 않고 실행  
- **nvm**: Node 버전 관리  
- **yarn**: Facebook이 만든 패키지 매니저

---

## 9. Babel
문서에서는 Babel을 “JavaScript 컴파일러”라고 설명하며, 다음 기능을 수행한다고 말한다.

- 최신 문법(ES6+)을 구 문법(ES5)으로 변환 (트랜스파일링)
- 폴리필 제공(babel-polyfill)
- JSX 변환

---

## 10. Webpack
Webpack은 “자바스크립트로 만든 프로그램을 배포하기 좋은 형태로 묶어주는 도구”이다.

- Entry, Output, Loader, Plugin 구조
- JS, CSS, 이미지 등을 모두 모듈로 보고 번들링

---

## 11. React 프로젝트 시작하기

```bash
npx create-react-app my-app
cd my-app
npm start
```

---

## 12. 폴더 구조

### 주요 폴더
- **node_modules**: 설치된 라이브러리
- **public**: 정적 파일(index.html 등)
- **src**: React 코드가 위치하는 핵심 폴더

### src 내부 구조
- **components**: 재사용 컴포넌트
- **pages**: 라우팅되는 페이지
- **hooks**: 커스텀 훅
- **services**: API 요청
- **styles**: CSS/SCSS
- **utils**: 공통 함수
- **contexts**: 상태 관리(Context API)

---

## 13. Development vs Production

### 개발 모드
```
npm start
```

### 프로덕션 빌드
```
npm run build
```

빌드된 파일은 `build/` 폴더에 생성되며, 실제 배포 시 사용된다.

---

## 14. index.html, index.js, App.js 관계

문서에서는 다음과 같이 설명한다.

- **index.html**: 템플릿 파일, `root` div 포함
- **index.js**: React 앱의 진입점, App.js를 root에 렌더링
- **App.js**: 실제 화면을 구성하는 컴포넌트

구조 흐름:

```
App.js → index.js → index.html → 브라우저 출력
```
