# 📘 Web Programming Report  
### ― HTML, CSS, DOM, Rendering, SPA/MPA, Web Server, React ―

## 1. HTML(Hyper Text Markup Language)
HTML은 웹사이트의 구조를 기술하기 위한 마크업 언어로, 문서의 형태와 구조를 정의한다. 문서에서는 HTML을 “웹사이트의 모습을 기술하기 위한 마크업 언어”라고 설명하며, Hyper Text는 “참조(하이퍼링크)를 통해 독자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트”라고 정의한다.

HTML 문서는 `<!DOCTYPE html>` 선언으로 시작하며 `<head>` 영역에는 메타데이터, 스타일, 스크립트가 포함되고 `<body>` 영역에는 실제 화면에 표시되는 콘텐츠가 위치한다.

---

## 2. CSS(Cascading Style Sheets)
CSS는 HTML 요소에 스타일을 적용하는 스타일시트 언어이다. 문서에서는 CSS를 “HTML 문서의 색이나 모양 등 외관을 꾸미는 언어”라고 설명하며, CSS3가 현재 표준으로 사용되고 있음을 언급한다.

CSS의 주요 기능은 다음과 같다.

- 색상, 배경, 텍스트, 폰트
- 박스 모델(Box Model)
- 리스트, 테이블, UI 요소 스타일링

또한 Sass와 같은 CSS 전처리기를 통해 CSS의 단점을 보완할 수 있다.

---

## 3. ECMAScript & JavaScript
JavaScript는 웹 페이지의 동작을 담당하는 스크립트 언어이며, ECMAScript는 JavaScript의 표준 규격이다. 문서에서는 JavaScript를 “웹 페이지가 동작하는 것을 담당하는 스크립트 언어”라고 설명한다.

---

## 4. DOM(Document Object Model)
DOM은 HTML 문서를 객체 기반 구조로 표현한 모델이다. HTML 태그마다 DOM 객체가 생성되며, 이를 통해 화면의 콘텐츠나 스타일을 동적으로 변경할 수 있다.

문서에서는 DOM 객체가 다음 요소로 구성된다고 설명한다.

- **프로퍼티(property)**
- **메소드(method)**
- **컬렉션(collection)**
- **이벤트 리스너(event listener)**
- **CSS 스타일 객체**

예시로 `<p id="firstP">` 태그의 DOM 객체는 `innerHTML`, `style`, `onclick` 등의 속성을 가진다.

또한 `createElement()`, `appendChild()`, `removeChild()` 등을 이용해 DOM 트리에 동적으로 요소를 추가하거나 삭제할 수 있음을 코드 예제로 보여준다.

---

## 5. Rendering(렌더링 과정)
브라우저는 웹 페이지를 다음 순서로 렌더링한다.

1. HTML 파싱 → **DOM 트리 생성**
2. CSS 파싱 → **CSSOM 트리 생성**
3. DOM + CSSOM 결합 → **렌더 트리 생성**
4. 각 노드의 크기와 위치 계산 → **레이아웃(Reflow)**
5. 화면에 그리기 → **페인트(Repaint)**

문서에서는 이를 “실시간으로 웹사이트가 그려지는 과정”이라고 설명하며, Critical Rendering Path(CRP)를 도식으로 제시한다.

---

## 6. SPA vs MPA

### 6.1 SPA(Single Page Application)
SPA는 하나의 HTML 페이지에서 필요한 데이터만 받아 화면을 갱신하는 방식이다. 문서에서는 SPA를 “서버로부터 완전한 새로운 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성하는 웹사이트”라고 설명한다.

**장점**
- 빠른 화면 전환, 깜빡임 없음
- 최초 로딩 후 캐싱 활용 가능
- 모바일 앱과 동일한 API 사용 가능
- FE/BE 분리 용이, 컴포넌트 재사용성 높음

**단점**
- 초기 로딩 속도 느림
- SEO 취약
- 보안 이슈(XSS 등)
- CSR 기반이므로 JS 의존도가 높음

---

### 6.2 MPA(Multi Page Application)
MPA는 페이지 이동 시마다 서버에서 새로운 HTML을 받아오는 방식이다.

**장점**
- 첫 로딩 속도 빠름
- SEO에 유리
- 페이지 수 확장 용이
- 오랜 역사로 자료가 풍부함

**단점**
- 페이지 이동 시 깜빡임 발생
- 매번 전체 페이지 렌더링
- 클라이언트/서버 모두 관리 필요
- 유지보수 복잡

---

## 7. Web Server(IIS, Tomcat, Apache)

### 7.1 IIS(Internet Information Services)
Windows 10/11에 기본 포함된 웹 서버로, `C:\Inetpub\wwwroot` 경로를 기본 웹 루트로 사용한다. 문서에서는 `default.asp` 파일을 작성해 “Hello Asp”를 출력하는 테스트를 보여준다.

### 7.2 Tomcat
Java 기반 웹 서버로, Eclipse와 연동하여 JSP 파일을 실행할 수 있다. 예제에서는 `index.jsp`에 “Helllo JSP”를 출력하는 코드를 작성한다.

### 7.3 Apache
Laragon, XAMPP, MAMP 등과 함께 사용되며 PHP 실행 환경을 제공한다. 문서에서는 `hello.php` 파일을 통해 “Hello PHP”를 출력하는 예제를 보여준다.

---

## 8. React
React는 웹 및 네이티브 UI를 구축하기 위한 라이브러리이다. 문서에서는 React의 핵심 요소로 다음을 제시한다.

- 컴포넌트
- 데이터 흐름
- 생명주기
- 이벤트
- JSX

React는 SPA 개발에 널리 사용되며, 컴포넌트 기반 구조로 재사용성과 유지보수성이 뛰어나다.

---

# 📌 결론
본 문서는 웹 프로그래밍의 기초 요소인 HTML, CSS, JavaScript, DOM, 렌더링 과정부터 SPA/MPA 아키텍처, 웹 서버(IIS, Tomcat, Apache), 그리고 React까지 웹 개발의 핵심 개념을 폭넓게 다루고 있다. 특히 DOM 조작, 렌더링 과정, SPA/MPA 비교는 현대 웹 개발에서 매우 중요한 개념으로, 프론트엔드 개발자로 성장하기 위한 필수 지식임을 확인할 수 있다.

---

필요하다면 **표지**, **목차**, **요약본**, **발표자료(PPT용)** 형태로도 재구성해 줄 수 있어요.
