# flex

### 출처 1분 코딩님 flex 강의 정리

<img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/c38322d9-89d1-47d9-99b7-d35c9dcca753/CSS-2.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220104%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220104T163447Z&X-Amz-Expires=86400&X-Amz-Signature=7d71b97f65ffa0e5bd550b9f592c966072b77b15cf9892364026c891be16e430&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22CSS-2.jpg%22&x-id=GetObject">

## flex 컨테이너 속성

아이템을 한번에 정렬한다.

- justify-content
  - flex 진행방향으로의 정렬
  - 기본 값 : flex-start
- align-content
  - flex 진행방향의 반대방향으로 정렬
  - 기본 값 : stretch - 진행 방향의 반대방향으로 쭉 늘려 채운다.

## flex의 아이템 속성

자식요소에 설정한다.

- flex-grow
- flex-basis
- flex-shrink

### flex-grow

- 부모공간의 남은 여백을 flex-grow로 설정한 비율에 맞게 크기를 할당한다.
- grow 기본값은 0
- (공백/grow의 합)이 grow 1 값이 된다.
- 각 아이템은 grow의 값만큼 너비가 더해진다.

### flex-basis

- item들의 기본 크기를 설정 태그
- 기본 값은 auto
- flex 방향으로의 크기이다. row일 때는 width, column 일떄는 세로이다.
- 내가 차지하는 공간을 의미한다.
- 기본 크기보다 basis가 클 경우 basis에 맞춰지고 작을 경우 기본 크기를 유지한다.

### flex-shrink

- flex 박스에 flex-wrap : wrap 속성이 부여되어 있으면 실행되지 않음
- shrink 기본값은 1
- 레이아웃 영역을 넘는 경우 (넘어간 너비/아이템들의 shrink의 합)이 shrink 1 값이 된다.
- 각 아이템은 shrink의 값만큼 너비값을 차감하게 된다.
- shrink를 0을주면 줄어들지 않겠다는 것이다.

### 축약형

- flex : grow shrink basis
- 기본은 flex : 0 1 auto;
- 많이 쓰는 것은 flex : 1 이런 식이다.
  - flex 1 1 auto를 의미한다.

### align-self

- 아이템 중 선택한 하나만 정렬 위치를 바꾼다.

### 꿀 팁

- 반응형으로 화면이 작아질 때 column으로 줄을 바꿀 때 그냥 display: block을 줘라.
  - 이런 경우 basis말고 width를 주는 것이 좋다.
