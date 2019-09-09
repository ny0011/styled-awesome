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
