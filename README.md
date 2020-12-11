# Look UP
## 딥러닝을 활용한 스마트 옷장 관리 어플리케이션

## CTRL_S 유튜브 채널
https://www.youtube.com/channel/UCD8cOZayQ3FosrTvUVdCQqg

## 시연영상 링크

## 프로젝트 레포지토리 정리
- 얼굴인식 MinjungShin/Look-UP/얼굴인식

- 윤곽선 추출 MinjungShin/Look-UP/얼굴인식

## 프로젝트 소개
매일 아침마다 핸드폰의 날씨 어플리케이션에서 기온을 살펴보고, 일정과 메모 어플리케이션을 실행해
오늘 약속이 무엇인지 확인한 후에야 입을 옷을 정하기 시작한다. 바쁜 와중에 찾으려는 옷이 어디있는지
상의와 어울리는 하의가 무엇인지 고민을 하느라 시간에 쫓기기 마련이다. 또한 옷장 구석에 박혀있는 
옷을 잊고 비슷한 상품을 다시 사거나 심혈을 기울여 골라 산 옷이지만 기존에 갖고 있던 옷과 매치하기
어려워 기대와 달리 반품을 진행하는 일도 다반사이다.

이때, 누군가 매일 아침마다 나를 대신해 그날의 예정된 활동, 방문 장소, 날씨 그리고 내가 평소 선호한 
스타일대로 코디를 해준다면 어떨까 고민해보았다. 옷은 항상 우리와 밀접하게 닿아있는 생활요소이기에
선택하는 데에서 오는 스트레스와 소요되는 시간, 불필요한 소비를 크게 줄이고자 해당 서비스를 고안하였다.

## Look UP 대표 기능 3가지
1. 간편한 옷장 추가 기능

    1-1. 앨범 통한 자동 추가
  
     <img width="315" alt="1" src="https://user-images.githubusercontent.com/55148494/101899037-7d946880-3bf0-11eb-9a21-5bf62b4e8110.JPG">
  
    1-2. 실시간 카메라 통한 추가
  
     <img width="315" alt="2" src="https://user-images.githubusercontent.com/55148494/101899045-7ec59580-3bf0-11eb-97fc-50a3385700e4.JPG">
  
    1-3. URL 통한 추가(인터넷 쇼핑)
  
     <img width="315" alt="3" src="https://user-images.githubusercontent.com/55148494/101899046-7f5e2c00-3bf0-11eb-8cfa-f4d8158d2b8d.JPG">
     
  <img width="315" alt="4" src="https://user-images.githubusercontent.com/55148494/101899047-7f5e2c00-3bf0-11eb-90cd-3d88c0ac13f4.JPG">
  
2. 맞춤형 옷 정리법 제공
  
    <img width="315" alt="5" src="https://user-images.githubusercontent.com/55148494/101899048-7ff6c280-3bf0-11eb-8b2d-984de886bd83.JPG">

3. 룩북
  
    <img width="315" alt="6" src="https://user-images.githubusercontent.com/55148494/101899050-7ff6c280-3bf0-11eb-8ec2-d5b02612e6cb.JPG">
  
<전체 주요 프로토타입>
   
   <img width="315" alt="KakaoTalk_20201211_204414886" src="https://user-images.githubusercontent.com/55148494/101900617-1e842300-3bf3-11eb-9f56-1d4cc57f7e9c.png">

## 사용 기술 소개
1. 이미지 객체 인식(얼굴 인식, 옷 인식)

   1-1. 얼굴 인식  
    - 사진첩에서 사용자의 사진을 분류하기 위해서는 객체 인식 알고리즘이 활용되어야 한다. 이때, 다른 
      물체들과 얼굴을 분류하여 얼굴 영역을 검출하는 face detection, 여러 사람들 간의 얼굴을 식별하고 
      동일인 여부를 확인하는 face recognition 기술이 필요하다.
    - 얼굴 감지 및 식별에 대한 프로그램의 알고리즘 및 코드는 Open Cv 또는 텐서플로우를 기반으로 하며 
      여러 학습 모델들이 많이 구현되어 있으며 쉽게 찾아 볼 수 있다. 
  
   1-2. 옷 인식 및 분류
    - CNN 모델을 이용하여 옷을 인식하고 이 옷의 속성(패턴, 색, 종류 등)을 파악할 수 있는 선행연구가 있고 
      이를 훈련하기 위한 데이터(패션 MNIST)를 확보한 상태이다.

2. 이미지 윤곽선 추출
   - 옷을 크롤링한 후 옷장데이터로 추가하기 위해서는 윤곽선 추출 절차가 필요하다. 배경을 제거를 위해서는 
     총 9단계로 진행된다. 아래의 링크에서 상세히 설명되어 있기 때문에 실현이 가능할 것으로 보인다.
   - OpenCV, 파이썬 : 배경이 제거된 옷 사진을 데이터에 저장한다. 이 데이터들은 옷장 속 옷들을 조합하는 
     룩북 기능에서 사용된다. 

3. 텍스트 파싱
    - 정보를 추출하고자 하는 웹사이트 URL를 입력 받아서 그 페이지를 크롤링 및 파싱한다.
    - Python Beautiful Soup 활용
  
4. 선호도 기반 맞춤형 추천 알고리즘
   - 선호도를 반영해서 사용자에게 맞춤 정보를 제공하기 위해서는 데이터가 필요한데, 이는 크라우드소싱을 
     이용해 대중이 추구하는 스타일을 파악한다. 예를 들어,  “해당 상의(혹은 하의)에 어울리는 하의 
     (혹은 상의)를 골라라” , 혹은 “특정 상황에서는 옷을 어떻게 입을지 선택하여라” 등과 같이 다양한 상황을 
     가정하여 사람들의 답변을 메트릭스로 수치화한다. 메트릭스에 수치화한 값을 토대로 추후 사용자의 옷과
     어울리도록 다른 아이템들을 추천해준다. 이러한 방법은 아래의 논문에서도 상세히 기술, 구현되어 있기 
     때문에 LookUP에서도 구현 가능할 것으로 보인다.
   - Attribute Value Matrix (AVM) 을 이용하여 사용자의 선호도 정보를 저장한 후 추후 추천알고리즘에 
     활용한다.
   
5. 어플리케이션 개발
   - 안드로이드 스튜디오(Android Studio)와 LayOut Editor: 안드로이드 기반 어플리케이션 서비스를 제공하기 위해 해당 툴을 이용하여 서비스 기능과 UI를 빌드한다. 
   - AWS Storage 연동: 저장소(Storage) 내 옷 영상/이미지를 가져와 화면에 디스플레이하며 촬영한 영상은
     서비스 내 가상 옷장에 저장한다. 안드로이드에 옷 종류 별 Matrix를 저장하여 촬영하거나 로드한 옷의 
     속성이 무엇인지 파악하기 위해 사용한다. 

## 기술 블로그
- 김연재 https://yj-tech.tistory.com/

   =>배경 제거 및 윤곽선 추출, KNN 알고리즘을 활용한 얼굴 인식과 판별, 개인화 추천 시스템

- 신민정 https://mj-lab.tistory.com/

   =>CNN 모델, Tensorflow를 활용한 옷 분류, Tensorflow를 활용한 Object Detection

- 이소림 https://sr-algo.tistory.com/

   =>얼굴인식 알고리즘 스터디 및 KNN 알고리즘을 활용한 얼굴 인식과 판별, Tensorflow lite를 활용한 face detection
   
## Reference

- 실시간 얼굴인식(안드로이드 스튜디오)

  https://medium.com/@estebanuri/real-time-face-recognition-with-android-tensorflow-lite-14e9c6cc53a5

- Face Detection(안드로이드 스튜디오)

  https://www.youtube.com/watch?v=iSf1gD5LgjI

- KNN 알고리즘을 활용한 face detection & recognition

  https://thecodingnote.tistory.com/8

- 배경제거 및 윤곽선 추출

http://blog.naver.com/PostView.nhn?blogId=samsjang&logNo=220606250662&categoryNo=66&parentCategoryNo=0&viewDate=&currentPage=3&postListTopCurrentPage=&from=postList&userTopListOpen=true&userTopListCount=10&userTopListManageOpen=false&userTopListCurrentPage=3
