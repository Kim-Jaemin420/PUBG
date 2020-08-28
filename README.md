# PUBG clone coding  

## PUBG를 클론한 이유.   
짧지만 길었던 미니 프로젝트(스타벅스 클론 코딩)을 마치고 아쉬움이 남았다.  
수업시간에도 반응형 수업시간은 1주로 짧았고, 프로젝트 기간도 짧아 반응형 레이아웃으로 설계하기엔 무리가 있었다.  
이대로 자바스크립트로 넘어가기엔 반응형 레이아웃으로 해보고 싶은 마음이 들었다.  
그래서 평소 관심있던 PUBG 사이트를 선택해 클론 코딩을 시작했다.  

## PUBG 마크업.  
먼저 웹사이트를 보면서 내 방식대로 마크업을 시작했다.  
마크업을 끝내고 pubg의 마크업을 살펴보니 스타벅스 페이지와는 비교가 안될정도로 시멘틱했다.  
적절한 시멘틱 태그를 사용했고 이로 인해 컨텐츠에 대한 개발자의 의도를 알 수 있었다.  

## PUBG 레이아웃 방식.  
배틀그라운드 한국서버임에도 불구하고 아직 국내 점유율이 많은 IE를 고려하지않은 레이아웃 방식을 사용했다.  
flex나 object-fit, picture 태그등에서 IE를 완전히 배제했다는 것을 알 수 있었다.  
물론 최신 레이아웃 기법을 사용하면 고전 레이아웃 기법보다 훨씬 편하고 고려해야할 사항이 적다.  
또한, 이제는 크롬 점유율이 앞서가는 것을 알 수 있다.  

그러나, 크롬이 익숙하지 않지만 구매력을 지니고 있는 사용자도 접근이 가능하도록 하면 매출에 도움이 될 것이라고 생각했다.  
아직은 IE 사용자를 완전히 배제하기는 이르고, 또 좀 더 신경쓸게 많은 고전 레이아웃 기법을 좀 더 연습해보고 싶다는 생각에 flex를 완전히 배제하고 레이아웃을 잡았다.  

## 내가 겪은 어려움.  
먼저 메인 네비게이션에서부터 문제가 많았다.  
flex를 사용하지 않다보니 화면 크기를 줄였을때 자연스럽게 줄어드는 모습을 구현하기 어려웠다.  
또, svg이미지를 다뤄본적이 없어 어떤 방법으로 삽입해야 하는지 애를 먹었다.  


## 해결방법.  
flex를 사용하지 않고 화면 크기를 줄였을 때 자연스럽게 줄어들게 하기 위해 로고이미지의 크기와 "지금구입"버튼의 크기를 줄였다.  
또, 링크 아이콘이 없어도 소비자들이 버튼이라고 인지할 것이라 생각했다. 또한, 링크 태그를 이용해 마크업했기 때문에 스크린리더 사용자도 음성 정보를 통해 링크인 것을 인지할 것이라 생각했다.  
svg이미지의 경우 기존 PUBG페이지는 html파일에 직접 svg를 삽입했다. 이 방식은 용량 문제가 있을 수 있다고 생각해 따로 svg 파일을 만들어 삽입했다.  
그런데, 이 방법은 파일을 관리하거나 효과를 주기에 불편했다. 결국 직접 삽입하는 방법과 따로 파일을 생성하는 방법 모두 사용했다.  


## PUBG의 문제점과 나의 생각.  
- 웹페이지에서 h1태그는 한 번만 사용되어야 하는데 각 섹션의 제목태그를 모두 h1태그를 사용하였다.  
- 건너뛰기 링크가 제공된다면 좋겠다고 생각했다.  
- 메인 네비게이션의 경우, 하위 목록이 있을 경우 엔터를 누르면 목록이 펼쳐지도록 구현하는 것이 키보드 접근자에게 편할 것이라 생각했다.  
  PUBG 기존 사이트를 보면 아래로 향한 꺽쇠가 있는데 엔터를 누르면 아무런 반응이 일어나지 않는다.  
  자바스크립트를 통해 탭키를 이용해 접근할 수 있도록 구현하도록 하겠다.  
- 탭 접근에 대한 부분이 아쉬웠다. 메인 베너, 배그 르포, 패치노트 같은 부분은 버튼만 탭 접근이 가능해 무엇에 대한 더보기 버튼인지 알 수 없었다. 이 부분은 탭인덱스를 추가해 보완하였다.  
- 마크업 부분에서는 메인안에 footer가 들어있었다. div안에 main태그와 footer태그가 있었다. 레이아웃적으로 그게 더 편할 수도 있으나 시멘틱하지 않다고 생각해 메인과 푸터를 분리하였다.  

## 느낀점  
스타벅스 홈페이지와 달리 PUBG의 페이지는 훨씬 시멘틱하고 접근성도 많이 고려한 것을 볼 수 있었다.  
아이콘에도 대체텍스트를 주었고 role 속성도 사용했다. 생각하지 못했던 부분이라 많이 배우는 계기가 되었다. 또, 한국 페이지임에도 Flex와 grid를 사용한 것이 아쉽기도 하지만 개발자 입장에서 보면 매우 좋은 근무환경으로 보이기도 했다. 고전 레이아웃 기법 대신 flex와 grid를 사용하면 작업 시간을 훨씬 단축할 수 있어 효율적으로 보였다.  
다른 사이트에 비해 글자크기도 크고 색깔도 뚜렷했다. 찾아본 결과 노랑색 글자인 #f2a900과 바탕색의 명암비는 9.01, 회색인 글자 #adadad와 바탕색의 명암비는 8.06으로 최소 명암비인 4.5를 훌쩍 넘겼다. 이것까지 신경써서 작업했는지는 모르겠지만 저시력 사용자도 문제없이 사이트를 이용할 수 있을 것 같다.  
열심히 노력해서 PUBG에서 직접 코드 수정을 하길 바라며 md를 마치겠다.


