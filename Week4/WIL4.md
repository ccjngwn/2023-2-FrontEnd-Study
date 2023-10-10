# 계산기 만들기

# 1. 계산기 화면 분석

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b9ba95b-fe7d-4e0d-bd6f-e95f92a3be44/c68b9a6e-1bce-4ef1-8321-3304ee658a70/Untitled.png)

이렇게 생긴 계산기를 구현한다. 전체 계산기를 container 클래스로 만들고 각 줄 별로 구현한다. 각 줄에서 operator 부분과 number 부분으로 나눠서 구현한다.

# 2. 구현 중 생긴 문제점

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b9ba95b-fe7d-4e0d-bd6f-e95f92a3be44/d6410f90-f44a-45a6-b036-a2c086b9a583/Untitled.png)

1번의 사진처럼 되어야 하는데, html과 css 구조를 따라가며 작성하다 보니 위와 같은 형태로 만들어졌다. 뭔가 row-wrapper에 문제가 있는 것 같아 살펴보았다.

```css
.row-wrapper {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
```

코드가 다음과 같이 되었어야 한다. width를 100%로 지정하고 justify-content를 space-between으로 설정해서 전체 화면에 균일하게 퍼지게 만들었어야 한다. 그런데 화면이 이상했던 코드는 width를 100으로 지정하여 이상하게 된 것이다.

# 3. 구현하면서 배운 점

1. css ::

.input-text::placeholder라는 부분이 있었다. 이건 input-text 클래스에서 placeholder의 속성을 지정하는 것이다.

1. css transparent

투명을 지정하는 것이다. none과의 차이점이 거의 없다고 한다.

1. css align-items와 justify-content

전자는 요소들의 세로 배열을 지정한다. 전자가 start로 지정되면 맨 위에서부터 정렬되고, end로 지정되면 맨 아래서부터 정렬된다. 후자는 가로 배열을 지정한다. space-between이라면 가로 길이에 맞춰서 서로 일정 간격을 두고 정렬된다.

1. class 두 개 사용

class=”reset reset-operator”라는 부분이 있었다. 여기서 reset과 reset-operator 둘 다의 속성을 받는다. 이 때 css 문서에서 뒤에 선언된 클래스의 우선순위가 더 높다.

1. css button.number

button.number라는 부분이 있었다. 이건 button 태그 중에서 number 클래스를 가진 태그의 속성을 지정해주는 것이다.
