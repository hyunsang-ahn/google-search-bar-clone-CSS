# CSS 정리

### 1. CSS 선언하는법

- 스타일 태그를 선언하기

```css
<style>
    a {
    color : red;
    }
</style>

```

- 기존 태그에 스타일 속성을 사용한다.(하나의 선택자에 대해서만 삽입이 가능해짐.)

```
<a href="" style="color : red">스타일 속성</a>
```

### 2. 클래스 선택자/id 선택자

- 클래스 선택자를 선택시에는 class="saw" 의 경우

```
<style>
    .saw{
    color : gray
    }
</style>
```

- 아이디 선택자의 경우(id="saw")

```
<style>
    #saw{
    color : gray
    }
</style>
```

- id 선택자가 가장 강하고 그다음이 class 그다음은 태그 순으로 강하다.

- 그 이유는 id는 오직 유일하기 때문에 선택자로서 매우 강함.
- 기존 태그 선택자에 비해서 클래스 선택자가 더 유일하기 때문에
- id > class > 태그 순으로 강함.

### 3. 박스 모델

- h1 태그는 자동으로 줄바꿈이 된다.
- a 태그는 줄바꿈이 안된다.
- 그 이유는 h1 태그는 화면 전체를 쓰고 a 태그는 컨텐츠의 부피만큼의 크기를 사용
- 화면 전체를 쓰는 태그 = block level element
- 자신의 부피만큼만을 쓰는 것 = inline element

- 위의 방법을 사용하여 display 에도 적용이 가능하다.
- display="inline" / display="block"

<img src="https://www.dummies.com/wp-content/uploads/415895.image0.jpg">

- 컨텐츠를 감싸는것 = border
- 컨텐츠와 border 사이 = padding
- box와 box 사이 = margin

### 4. 그리드 기능(gird)

- 이전 display : flex에 비해서 최신의 기술은 display : grid를 사용한다.
- 그리드는 열이나 행으로 놓고 싶은 것들을 하나의 div로 넣은뒤 div에 display : gird를 선언한뒤 사용한다.

```
div{
	display : gird
	grid-template-columns: auto 100px 1fr 2fr;
}
```

- 여기에서 auto는 컨텐츠의 크기만큼의 너비를 갖는다.
- 두번째 100px는 선언한 100px만큼의 크기를 갖는다.
- fr은 유연한 크기를 갖는 단위임.(fraction)
- 여기에서 fr은 총 3개를 갖고있음. 즉, 남은 영역을 모두 3개로 나눈값이 1fr 임.
- 세번째는 남은공간의 1/3 (총 fr) 만큼의 공간을 갖는다.
- 네번째는 남은공간의 2/3 (총 2fr) 만큼의 공간을 갖는다.

### 5. 미디어 쿼리

- 오늘날 여러 디스플리이에 적응할수 있는 화면기술, 즉 반응형 디자인이라는 것이 생겼다.
- 이것은 화면의 크기에 따라서 웹 페이지의 각 요소가 반응하여 동작함.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0" />
    <title>Document</title>
    <style>
      div {
        border: 10px solid green;
        font-size: 60px;
      }

      @media (min-width: 800px) {
        div {
          display: none;
        }
      }
    </style>
  </head>
  <body>
    <div>
      Responsive
    </div>
  </body>
</html>
```

- 위의 코드에서 min-width : 800 px 이란 최소 너비가 800px 즉, 800px 보다 큰 값에서 display를 none 한다는 의미이다.

### 6. CSS의 재사용성

- CSS를 선언하는 방법은 크게 2가지가 있다.

  - style.css 파일을 만들어 html 파일의 link 태그로 가져오는것

  - ```html
    <link rel="stylesheet" href="style.css" />
    ```

  - 직접 html 안에 style 태그를 통해서 선언하는방법.

- style.css 파일을 따로 만드는것이 유지 보수 및 자원관리면에서 훨씬 용이한 방법이다.

- 그 이유는 한개의 파일을 통해서 유지보수가 용이하며,

- 네트워크 측면에서 각 페이지에 각각 style태그를 통해서 선언하는것이 더 빠르지만, 캐싱이라는 측면에서 볼때 홈페이지에 접근한뒤 style.css 파일을 불러오기만 하면 홈페이지의 어느공간에서도 css를 불러오기 편하기 때문에 훨씬더 빠르고 트래픽을 더 적게 쓸수 있다.

- 결과적으로 자원의 용이성, 유지보수의 용이성 측면에서 style.css 처름 css 파일을 따로 두는것이 더 좋다!

### 마무리

- 주말을 이용해서 간단하게 css에 대한 생활코딩-css편을 보고 간단하게 정리를 하였다.
- 헷갈렷던 margin,padding 등에 대해서 조금더 알게 되었고 grid 시스템, style 선언등에대한 부분을 새롭게 알게 되었다.
- 마지막으로 간단하게 클론 google 을 하여서 간단하게 구글 검색창을 따라서 만들어보았다(css만 사용해서??) - index.html 파일을 열어 확인해 볼수 있습니다.
- 완성본은 아래와 같습니다.

![ahngle](\ahngle.PNG)
