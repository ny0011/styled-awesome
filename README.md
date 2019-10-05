# Styled Components

1. 예전 방식대로 버튼 코딩해보자

- 버튼 하나하나에 클래스 일일이 지정하고 여러개가 붙어서 css를 변경함
- 지저분함ㅜ

2. Hello World with Styled Components

- styled. 뒤에 넣고싶은 html 태그를 쓴다
- ``에 CSS 속성을 넣는다

```
const Button = <Button className = {}>
=>
const Button = styled.button`
border-radius: 50px;
padding:5px;`
```

- 버튼 색은 어떻게 바꿀까?
- Component는 props를 가진다. component의 props를 가져와서 props에 따라 색을 바꿔준다

```
background-color: ${props => (props.danger ? "#e74c3c" : "#2ecc71")}
```

3. createGlobalStyle and styled

- body 부분의 css를 변경하기 위해 css파일을 만들어야 할까? ㄴㄴ
- createGlobalStyle 을 불러온다(injectGlobal 없어졌음)
  https://www.styled-components.com/docs/faqs#what-do-i-need-to-do-to-migrate-to-v4
- 만약 이미 있는 태그의 스타일을 가져오고 싶다면 태그 객체.withComponent()를 사용하자

```
const Anchor = Button.withComponent("a");
-> Anchor는 a태그지만 Button의 style을 가짐
```

- Anchor에 밑줄을 없애고 싶을 때? styled()`` 를 사용한다(?)
  https://github.com/styled-components/styled-components/issues/1546

4. Animations

- 애니메이션을 사용할 때 keyframes, css component를 import한다

```
import {css, keyframes} from "styled-components"

keyframes`` 안에 css keyframes설정을 해두고 animation을 사용할 곳에 css`animation: ${변수이름} 2s linear infinite` 로 해준다

```

- 변수를 설정해서 css를 바꾸는 것 뿐만 아니라 props의 변수들로 css를 바꾸는 것도 가능함

```
<Button danger rotationTime="{1}>

animation: ${rotation} ${rotationTime}s
```
