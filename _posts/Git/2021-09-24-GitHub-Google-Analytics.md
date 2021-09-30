---
title: Github (Jekyll)에서 Google Analytics 사용하기
layout: single
author_profile: true
comments: true
share: true

categories:
- Git

tags:
- [Github, Jekyll, Google Analytics]

date: 2021-09-24
last_modified_at: '2021-09-24 21:46:00 +08000'

toc: true
toc_sticky: true
toc_label: Content
---

## 1. Google Analytics란?

[구글 애널리틱스(Google Analytics)](https://analytics.google.com/)는 웹사이트 트래픽을 측정 및 수집하고 분석을 해주는 무료 서비스입니다.
구글은 2005년 11월 Urchin을 인수한 이후 Google Analytics 서비스를 런칭했습니다.
사용자의 페이지 이동, 페이지 체류 시간, 클릭, 스크롤, 사용자 별 이벤트 수, 국가 별 이벤트 수 등의 내용을 상세히 분석하여 제공합니다.

![Google_Analytics_Set_Up_00](\assets\images\post\github\google_analytics.png){: .align-center .open-new}


Google Analytics 가입 및 설정이 완료 된 분들은 [4. Github  설정] 부분만 보시면 됩니다.



## 2. Google Analytics 가입

이제부터 Google Analytics를 GA로 기재하도록 하겠습니다.



### 2.1 홈페이지

- https://analytics.google.com/

![Google_Analytics_Set_Up_00](\assets\images\post\github\google_analytics_set_up_00.png){: .align-center .open-new}



### 2.2 계정 추가

지금 입력하는 계정은 GA 내부적으로 사용되는 계정입니다.
GA에 구글 계정으로 로그인 할 시 다수의 계정을 생성 및 관리 할 수 있고, 하나의 계정에는 다수의 사이트 정보를 추가 할 수 있습니다.

대부분 계정 이름을 회사명, 단체명 등을 사용하고 있습니다.
본인이 구분하기 위한 용도로 사용되니 적당한 이름을 사용하면 됩니다.

![Google_Analytics_Set_Up_01](\assets\images\post\github\google_analytics_set_up_01.png){: .align-center .open-new}



### 2.3 속성 추가

속성이란 하나의 사이트 관리를 위한 단위라고 생각하시면 될 것 같습니다.
하나의 계정에는 다수의 속성을 생성하여 관리 할 수 있으니,  속성 이름은 사이트를 대표하는 키워드로 설정하는 것이 좋습니다.

보고 시간대 및 통화를 대한민국으로 변경해주고 다음으로 넘어갑니다.

![Google_Analytics_Set_Up_02](\assets\images\post\github\google_analytics_set_up_02.png){: .align-center .open-new}



### 2.4 비즈니스 설정

업종 카테고리는 최대한 사이트에 관련 된 것으로 선택합니다.
GA 를 어떻게 사용 할지에 대한 선택사항 체크 후 다음으로 넘어갑니다.

![Google_Analytics_Set_Up_03](\assets\images\post\github\google_analytics_set_up_03.png){: .align-center .open-new}



### 2.5 약관 동의

![Google_Analytics_Set_Up_04](\assets\images\post\github\google_analytics_set_up_04.png){: .align-center .open-new}



## 3. Google Analytics 설정 

### 3.1 속성 설정

약관 동의를 마치셨으면 아래와 같은 화면이 보여집니다.
해당 항목은 좌측 최하단에 있는 설정 메뉴를 통해 활성화 시킬 수 있습니다.

[2.3 속성 추가] 단계에서 추가 된 속성을 설정하는 단계입니다.
자신의 상황에 맞게 웹, Android 앱, iOS 앱 중 하나를 선택합니다.
해당 글은 Github(Jekyll)에 GA 적용을 목표로 하고 있으니 웹 항목을 선택합니다.

![Google_Analytics_Set_Up_05](\assets\images\post\github\google_analytics_set_up_05.png){: .align-center .open-new}



### 3.2 데이터 스트림 생성 및 설정

GA를 적용하고자 하는 사이트의 URL 및 스트림 이름을 작성 후 스트림을 생성합니다.
데이터 스트림 역시 하나의 속성에 다중으로 생성이 가능합니다.

정확하게 구분한다면 데이터 스트림 하나가 웹 사이트 하나와 대응되는 구조입니다.
사이트와 관련 된 앱들도 등록하면 같이 관리 될 수 있습니다.
하지만 하나의 속성에 여러 웹 스트림을 추가한다면 일관성 없는 결과를 얻을 수 있습니다.



Github 블로그에 GA 적용을 하려는 목표를 생각하면 하나의 속성에 하나의 데이터 스트림을 생성하는 것을 추천드립니다.

![Google_Analytics_Set_Up_06](\assets\images\post\github\google_analytics_set_up_06.png){: .align-center .open-new}




데이터 스트림을 생성하면 생성 된 스트림의 상세 정보가 보여집니다.

![Google_Analytics_Set_Up_07](\assets\images\post\github\google_analytics_set_up_07.png){: .align-center .open-new}



##  4. Github 설정

### 4.1 환경

```
Google Analytics 4
Jekyll v4.2.0
```




Google Analytics 4 속성을 사용하는 경우 추적 ID 대신 측정 ID가 사용됩니다.

```
추적 ID : UA-XXXXXX-X
측정 ID : G-XXXXXXX
```



### 4.2 Google Analytics 적용

_config.yml 수정

- provider 항목에 "google-gtag" 추가

- tracking_id 항목에 측정 ID 추가
  

[commit 090131d](https://github.com/enigmaslayer/enigmaslayer.github.io/commit/090131d698b1897dfd38b60131ba6bb2ff9382bf?branch=090131d698b1897dfd38b60131ba6bb2ff9382bf&diff=split) 참조

```
# Analytics
analytics:
  provider               : "google-gtag"
  google:
    tracking_id          : G-WXHRG8LQHW
    anonymize_ip         :
```




GA 4 에서는 <u>자바스크립트의 추가 없이</u> 측정 ID만 입력하면 적용이 완료 됩니다.

![Google_Analytics_Set_Up_00](\assets\images\post\github\google_analytics_set_up_08.png){: .align-center .open-new}







