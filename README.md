## 🎥B10 이꾸조 

### 1. 프로젝트 소개
영화 정보 공유사이트 TMDB API를 사용해 영화와 tv를 검색하고, 소개하고 
localStorage를 사용해 리뷰를 등록,삭제 수정할 수 있는 사이트만들기

### 2. 프로젝트 기간
2024.05.01 ~ 2024.05.08

### 3. 개발환경

#### 사용언어
![html](https://camo.githubusercontent.com/d30449fa2dbae519940a0d08f0202996163310b8c6b9336480232cfb48d38286/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f68746d6c352d4533344632363f7374796c653d666f722d7468652d6261646765266c6f676f3d68746d6c35266c6f676f436f6c6f723d7768697465)
![css](https://camo.githubusercontent.com/f432d617c378401551c4ba1fa6670f2e4e4ec6676cf3b8370096f3f8b66554ee/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6373732d3135373242363f7374796c653d666f722d7468652d6261646765266c6f676f3d63737333266c6f676f436f6c6f723d7768697465)
![js](https://camo.githubusercontent.com/835ac33106b566924b6984fd422f9ce2ec7f07bf98906ee2f515034b1808c572/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f6a6176617363726970742d4637444631453f7374796c653d666f722d7468652d6261646765266c6f676f3d6a617661736372697074266c6f676f436f6c6f723d626c61636b)

#### 코드컨벤션
![코드컨벤션](https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/2fca726c-f559-44ca-a2a8-f5eb6bdb9953)


### 4. 팀원소개 및 역할 
| 윤문열 | 진수민 | 한소영 | 윤기준(리더) | 이혜진 | 
|----------|----------|----------|----------|----------|
| main-page   |  movie-page  | tv-page   | detail-page upper   | detail-page review   |


### 5. 주요기능 
전체적인 구상

<img width="635" alt="스크린샷 2024-05-09 오후 6 18 43" src="https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/5333bd30-f64f-45bb-a706-deba5050be9c">

메인페이지, 영화페이지, tv페이지, 상세페이지 총 4 페이지로 구성이 되어있습니다. 

<br>
<br>
<img width="1280" alt="스크린샷 2024-05-09 오후 6 58 47" src="https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/4f51dd9c-d7c4-4a14-8467-7b1c579d5819">
<br>
TMDB API 통해 현재 trending 중인 영화 및 티비 시리즈 데이터베이스에 접근해 각 포스터 이미지들을 가져왔고, 
이를 기반으로 CSS에서 키프레임 애니메이션을 구현해 eye-catching 한 랜딩페이지로 구현해냈습니다. 
포스터 이미지들은 API를 통해서 TMDB 서버에서 가져왔으므로 TMDB의 트렌딩 영화 및 TV 시리즈 리스트를 실시간으로 반영합니다.
사용자는 여기서 TV시리즈나 영화의 포스터 트랙을 클릭하거나, 상단 헤더 내 movie 와 tv 카테고리를 클릭하는 것을 통해서 tv시리즈 페이지나 영화 페이지를 선택해서 이동할 수 있습니다. 
<br>
<br>
<img width="1304" alt="스크린샷 2024-05-09 오후 6 59 01" src="https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/7c0a73be-e824-4bf9-83bd-9a40b1bb2cce">
<br>
기본적으로 티비 시리즈 페이지와 영화 페이지는 동일한 구조를 갖고 있으며, 어떤 TMDB api를 활용해 어떤 정보를 가져오느냐의 차이만 존재합니다. <br>
TMDB API 통해 현재 trending 중인 영화 및 티비 시리즈 데이터베이스에 접근해 각 tv시리즈 또는 영화의 포스터 이미지와 해당 tv시리즈 또는 영화가 
TMDB 데이터베이스 상에서 갖는 id값을 가져왔고, CSS에서 grid 형 display를 활용해 각 영화, 티비 포스터가 카드 형식으로 한 페이지에 20개씩 정렬되도록 구현했습니다.
<br>
<br>
<img width="1280" alt="스크린샷 2024-05-09 오후 7 00 19" src="https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/8ac0236d-cde7-4da7-8553-be9d0a886bbe">
<br>
상세 페이지의 자바스크립트는 이전 페이지에 클릭된 카드가 갖는 id값과 더불어, 해당 클릭이 영화 페이지에서 일어났는지 tv 페이지에서 일어났는지에 대한 정보를
url의 type 파라미터와 media_id 파라미터를 통해서 전달받습니다.
자바스크립트는 현재 상세페이지 url 내 타입 파라미터가 tv이면 TV 시리즈 데이터베이스에서 media_id 파라미터를 통해 전달받은 아이디를 통해 클릭된 대상 티비 시리즈의 정보를 가져오는 TMDB api를 실행하고, 
반대로 url 내 타입 파라미터가 movie라면 
영화 데이터베이스에서 media_id 파라미터를 통해 전달받은 아이디를 통해 클릭된 대상 영화의 정보를 가져오는 TMDB api를 실행합니다.
이를 통해 페이지를 구성하는데 필요한 백드롭이미지, 포스터이미지, 제목, 평점, 오버뷰 등을 가져오며, 이를 innerHTML메서드를 통해 html 문서에 표시되게끔 했습니다.
<br>
<br>
<img width="796" alt="스크린샷 2024-05-09 오후 7 01 09" src="https://github.com/hyejinleeee/TeamB10-movie-tv-page-project/assets/159586671/57f71094-dd9c-4631-9c8d-f6de0b53657f">
<br>
상세페이지 하단에는 해당 영화나 티비시리즈에 대해 사용자가 의견을 남길 수 있는 기능을 구현했습니다. 
각 의견은 50자를 넘기지 않도록, 비밀번호는 4자리 숫자만 가능하도록, 그리고 모든 인풋창이 입력된 상태에서만 의견 등록이 가능하도록 제한했고 
이를 위한 유효성 검사 및 제한 기능을 구현했습니다. 
의견을 입력하고 등록버튼을 누르면 입력한 정보와 해당페이지 url의 id값이 localStrage에 저장이 되며, 이 값들을 통해서 해당 영화나 티비 시리즈에 대한 의견들만이 불러와지도록 구현했습니다.
