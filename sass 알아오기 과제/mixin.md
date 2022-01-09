# Mixin

코드를 재사용하기 위해 만들어진 기능이다.

매번 사용하는 스타일을 하나로 묶어서 사용

- 서로 연관성있는 스타일 속성끼리 묶어야 더 사용성이 높다.
- 관계없는 선택자에서 조금 다른 스타일을 적용할 때 사용한다.

파일로 만들어 import해 사용하면 유용

```jsx
@mixin 이름(매개변수) 생성
@include 이름(인수) 사용

//응용
@mixin center-xy{ //정의
	display: flex;
	justify-content : center;
	align-items : center;
}

.card{
	@include center-xy; //사용
}
```

### Arguments

1. 인수 mixin이름 뒤에 인수를 넣어서 사용할 수 있음

매개변수와 인수의 개수가 같아야한다.

$size : 10px 과 같이 값이 들어오지 않는 경우 기본값 설정도 가능하다.

```jsx
@mixin image-style($ul,  $repeat, $positionX, $positionY ,$size : 10px) {
  background-image: url($ul);
  background-size: $size;
  background-repeat: $repeat;
  background-position: $positionX $positionY;
}
//background관련 스타일 코드가 들어있다.
//mixin의 인수에 따라 조금씩 다른 스타일링이 가능하다.

.profile {
  @include image-style("./assets/user.jpg", cover, no-repeat, center, center);
}

.box-one {
  @include image-style(url("/images/poster1.svg"), cover, no-repeat, 40%, 50%);
}
```

### Content

@content를 사용하면 원하는 부분에 스타일을 추가하여 전달할 수 있다.

```jsx
// 정의하는 곳에서
@mixin sample{
	display: flex;
	justify-content: center;
	align-items: center;
  @content //여기를 @content해두면
}

a {
	@include sample{
        //@include로 해당 mixin의 content부분을 채울 수 있음
	    color: white;
	}
}
```
