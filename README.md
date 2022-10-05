# cp2_team3

# **1. 서론**

- **프로젝트 배경**
    - E-commerce 기업의 로그 데이터 분석 및 시각화를 통한 인사이트 도출과 이에 따른 액션 플랜 제시, 액션 플랜에 따른 추천 알고리즘 구성
    
        
    

- **프로젝트 목적**
    
     1.  데이터 분석을 통한 인사이트 도출
    
    1. 액션 플랜 제시
    2. 추천 알고리즘 구성
    

    

# 2. **연구 및 개발 방법**

- **개발에 필요한 데이터 소개**
1. **어떠한 데이터가 왜 필요한지**
    
    what : E-commerce 기업의 로그 데이터 
    
    why : 
    
    1. RFM분석과 다양한 브랜드, 카테고리 분석을 위해서 필요
    2. 추천 알고리즘 CF, CB를 구현하기 위해 로그 데이터의 유저와 아이템의 정보가 필요  

1. **데이터의 수집 방법 혹은 출처**
    1. kaggle-oct.csv
        
        ([https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store))
        

1. **데이터 설명** 
    
    Data = (42448764, 9)
    
    index : 로그 데이터
    
    columns : 시간, 행동, 상품id, 카테고리id, 카테고리 code, 브랜드, 가격, 유저 id, 세션
    
    ![image](https://user-images.githubusercontent.com/97610185/193975681-9171d534-b931-4dc5-886e-c88cd91dde49.png)
    

1. **전처리** 
    1. 카테고리 코드 → 대분류, 중분류, 소분류로 구분
    2. 카테고리 id 제거
    3. 시간(str) → date
    4. event_type → labeling(view > 1, cart > 2, purchase > 3)

  

- **연구 및 개발에 필요한 기술 스택 정리**
1. 프로젝트에서 자신이 담당한 기술의 정의
    - python : 파이썬을 활용한 데이터 전처리 진행
    - CounterVertorizer: 모델링을 통한 기능 구현
    - pyplot : 시각화
    - sklearn : CounterVertorizer, cosine_similarity 사용
    - CF Algorithm : 추천 알고리즘 구현
    - CB Algorithm: 추천 알고리즘 구현
2. 해당 기술(또는 연구방법)의 최근 장점과 단점
    - CounterVectorizer
        - 장점
            - 횟수를 사용해서 벡터를 만들기 때문에 직관적이고 간단해서 여러 상황에서 사용할 수 있다.
        - 단점
            - 횟수만을 특징으로 잡기 때문에 큰 의미가 없지만 자주 사용되는 단어들, 조사 또는 지시 대명사가 높은 값을 가지기 때문에 유의미하게 사용하기 어려울 수 있다.
    - CF Algorithm
        - 장점
            - CF는 상호작용의(rating, 구매빈도..) 데이터만 있으면 적용할 수 있다. 따라서 도메인에 의존되지 않고 사용할 수 있다.
            - 일반적으로 content based보다 좋은 성능을 가진다.
        - 단점
            - 하지만 단점으로는 cold start문제가 있다. 새로운 item이나 user들에 대한 feedback(상호작용 데이터)이 부족하기 때문이다.
    - CB Algorithm
        - 장점
            - User IndependenceCB Filtering은 한 유저의 과거 행동을 분석해 그 유저만을 위한 Profile을 만든다. CF Filtering이 다른 유저의 행동까지 고려해야 한다는 점과는 대조적이다.
            - Transparency추천 시스템이 어떻게 추천 결과를 냈는지에 대한 설명이 가능하다. 추천된 아이템의 특성 벡터를 보면 해당 아이템과 유저가 과거에 좋아했던 아이템이 얼마나 유사한지 볼 수 있다.
            - New Item새로 등록된 아이템에 대해서도 추천이 가능하다.
        - 단점
            - Limited Content AnalysisCB Filtering은 아이템 추천에 사용할 특성(Features)의 수가 제한적이라는 한계가 있다.
            - Over-SpecializationCB Filtering은 유저가 좋아했던 아이템과 비슷한 아이템만 추천하기 때문에 유저가 예상치 못한 아이템을 추천해줄 수 없다. 이 문제를 Serendipity Problem이라고 한다.
            - New UserCB Filtering이 User Profile을 완성하기까지 충분히 많은 rating이 있어야 한다. 새로 가입한 유저의 경우 신뢰 할 만한 추천을 받기 힘듦.
    
3. 기간 내 구현 가능한 범위 설정
    - 데이터 분석 및 시각화
    - 추천 알고리즘 구현

# 3. **개발 일정 & 진행 상황**

  **7/7(목):**  팀원과 첫 미팅, 진행 방향 설정

  **7/8(금)~7/14(목):** E-Commerce 도메인 학습

  **7/15(금)~7/20(목):** 데이터 분석 및 인사이트 도출

  **7/21(금)~7/24(일):** 분석 결과를 통한 액션 플랜 제시

  **7/25(월)~8/3(수):** 추천 학습 및 모델 구현

  **8/4(목) :** 프로젝트 보고서 제출

  **8/5(금) :** 영상 및 최종 제출

- **협업 방식**

  정해진 시간에 맞춰 Discord와 Gather.town을 활용하여 이슈 발생 공유&아이디어 공유

  

- **업무 분담**

  **서경하(DA) :** 데이터 전처리 & 데이터 분석, 액션 플랜 제시, POPULAR, CF, CB 알고리즘 구현 

  **남창석(DA) :** 데이터 전처리 & 데이터 분석, 액션 플랜 제시, 베이스 라인 모델 구현

# 4. **결과**
  ## 1. 분석
  ### 액션플랜 1
  1. ![image](https://user-images.githubusercontent.com/97610185/193971345-9368b257-0886-4cb0-9513-983d9283712c.png)  
  총 판매액으로 전자, 가전, 컴퓨터 순이다.  
  
  2. ![image](https://user-images.githubusercontent.com/97610185/193971568-87c3a38e-10ae-44d5-bf7b-9afd259702e0.png)  
  총 판매 수이다. 
  
  3. ![image](https://user-images.githubusercontent.com/97610185/193971635-e1d5bb5c-46d7-4573-a5fc-87ce32669427.png)  
  판매 전환율이다.  
  
        
  - 이를 놓고 보았을 때 이커머스 기업은 다른 카테고리가 아닌 전자, 가전, 컴퓨터에 강세를 두어 마케팅하여 이용자들에게 이 분야에서의 전문성과 강점을 보여주어야 한다고 생각된다. 왜냐하면 전문성은 고객의 신뢰도와 연관되어 있다고 생각된다. 이는 곧 매출 증가로 이어질 것이라고 생각된다.
  
  ### 액션플랜 2
  1. ![image](https://user-images.githubusercontent.com/97610185/193972640-4c8c5344-5bf6-4aef-b8a8-de0faa74e85b.png)  
  전자제품 군의 브랜드 평균 재구매 횟수이다.  
  2. ![image](https://user-images.githubusercontent.com/97610185/193972768-bd3094a0-9f54-48a2-b4cb-00f3d27221e9.png)  
  브랜드 점유율  
  3. ![image](https://user-images.githubusercontent.com/97610185/193972836-5eae075d-510e-4ddf-803b-13382ab9c8ec.png)  
  브랜드 판매액  
  
  - 전자제품의 경우 대부분의 매출을 애플과 삼성이 점유하고 있는 것을 볼 수 있다. 또한 재구매 횟수를 보면 상위 2개의 브랜드는 비교적 다른 브랜드보다 생태계가 잘 구성되어있다고 생각된다. 때문에 전자제품 같은 경우 브랜드관을 런칭하여 해당 브랜드의 제품에 편의성 좋게 다가갈 수 있도록 하는 것이다. 또한 스마트폰과 같이 오디오 제품이나 시계 제품을 구매할 시 혜택을 부여하면 매출의 증가를 기대할 수 있을 것이라 생각된다.

  ### 액션플랜 3
  1. ![image](https://user-images.githubusercontent.com/97610185/193973676-27e97453-e5b7-441c-960a-6f966f194dfc.png)  
  브랜드 점유율
  
  - 가전제품의 경우 사용 주기가 전자제품에 비해 길다. 때문에 한 번 구매를 하고 나면 오랜 기간 같은 제품군을 구매하지 않게 된다. 현재 전자와 가전의 생태계를 구축하는 브랜드나 혹은 앱을 활용하여 전자제품과의 연계성을 높이는 노력을 하는 추세이다. 하지만 오래된 가전기기들은 호환이 되지않고 좀 더 아날로그 방식으로 접근해야한다는 불편함이 있다. 때문에 사람들은 전자제품과 함께 호환해서 사용할 수 있는 제품의 수요가 늘 것이라고 생각된다. 하지만 가전기기의 경우 사용 주기가 길기도 하고 가격대도 높게 설정되어 이용자들이 무턱대고 바꾸기에는 부담이 된다. 때문에 액션플랜으로 렌탈서비스를 제안한다. 렌탈 혹은 리스는 이용자들의 단기적인 부담을 줄여주어 가전기기의 사용주기를 줄여줄 것이라고 기대된다. 또한 이로 인해 기업은 가전기기에 대한 매출이 텀이 긴 매출이 아닌 단기적으로 매출을 올릴 수 있을 것이라 예상된다. 


  ### 액션플랜 4
  1. ![image](https://user-images.githubusercontent.com/97610185/193974915-3e602444-a406-4aae-90f8-8bd65bec17f5.png)  
  브랜드 점유율  
  2. ![image](https://user-images.githubusercontent.com/97610185/193974979-6920a28d-f0f7-4c28-929f-a70448e00289.png)  
  브랜드 평균 단가  
  3. ![image](https://user-images.githubusercontent.com/97610185/193975042-0a4f41bd-da00-4dec-9413-d04291eb0fbe.png)  
  브랜드 판매액
  
  - 컴퓨터 제품의 경우 대부분 평균 단가가 낮은 브랜드가 점유율이 높은 것을 볼 수 있다. 즉 컴퓨터 구매자들은 가성비가 좋은 브랜드를 찾아서 구매한다는 것을 볼 수 있다.  
  기업은 가성비 브랜드와의 협업 혹인 브랜드의 제품을 미리 선점해두면 매출 상승을 기대 할 수 있을 것이라 생각된다.
  
  ### 추천 알고리즘
  ![image](https://user-images.githubusercontent.com/97610185/193975497-8a53bbe8-5d9e-42bb-a364-e106ac20d6bd.png)




# 5. **결론(고찰)**

1. CP2 프로젝트 전반에 대한 고찰 진행
    1. **연구 및 개발 통해 알게된 점**
        1. 빅데이터를 어떻게 다뤄야 하는가에 대해 알 수 있었다.
        2. 다양한 추천 알고리즘을 공부함으로써 기업의 추천 시스템에 대하여 좀 더 깊게 통찰 할 수 있었다. 
        3. 결과: 
            
            [https://pricey-menu-1dc.notion.site/CP2-7dfcbe2a8be44767a54d541a4d953837](https://www.notion.so/CP2-7dfcbe2a8be44767a54d541a4d953837)
            
    2. **프로젝트 결과를 사회 혹은 비즈니스에 어떠한 방식으로 활용해 볼 수 있는지 ( ※ 긍정적인 측면으로)**
        1. 해당 기업에 대한 액션 플랜 제공으로 기업의 수익 증대 기대
        2. 추천 알고리즘을 통한 유저 니즈에 맞는 추천을 함으로써 수익 증대 기대
    3. **연구 및 개발을 진행하며 수행하지 못했던 부분 및 아쉬웠던 부분 ( ※ 이유를 포함하여 작성)**
        1. 빅데이터를 다룬 경험이 전무해서 자주 colab세션이 끝났다. SQL를 활용하여 원하는 데이터만 가져와 사용함으로써 RAM 사용량을 줄이는 것을 해야겠다. SQL 공부를 좀 더 하고 진행해야 하는데 그러지 못한 것이 아쉽다.
        2. 더욱 다양한 분석을 하지 못한 것이 아쉽다. 도메인에 대한 지식의 부족으로 좀 더 크리티컬한 분석을 진행하지 못한 것이 아쉽다. 또한 분석에 대한 공부를 좀 더 진행해서 이 아쉬운 부분을 채워야한다.
        3. 추천 알고리즘을 할 때 어떠한 방식으로 하는지 이해는 했지만 데이터가 너무 커서 좀 더 좋은 추천을 못한 것이 아쉽다. 카테고리 별로 나눠서 진행했는데 코사인 유사도 데이터를 카테고리 별로 하다보니 다른 카테고리에서 유사한 아이템을 추천을 못한 것이 아쉽다.
    4. **향후 자신의 프로젝트 주제를 이어서 진행할 연구자 혹은 개발자를 위한 방향성 및 기술적 측면 제언** 
        1. SQL을 활용하여 데이터 경량화를 해서 좀 더 빠르고 안전한 분석을 하는 것이 좋다고 생각된다. 
        2. 도메인 지식을 좀 더 딥하게 공부하여 좀 더 새로운 관점에서의 접근과 기존에 통용되던 접근을 둘 다 진행해서 기존과 새로움의 조화를 시키는 것이 좋다고 생각된다.

# 5. **참고 자료**

  

- CF알고리즘
    
    [https://western-sky.tistory.com/58](https://western-sky.tistory.com/58) CF알고리즘 구현
    
    [https://lsjsj92.tistory.com/568](https://lsjsj92.tistory.com/568) CF알고리즘 구현
    
- CB알고리즘

      [https://data-matzip.tistory.com/8](https://data-matzip.tistory.com/8) CB알고리즘



### 분석  
분석 시 oct.csv 사용

### 알고리즘  
  
추천 알고리즘은 algorithm.zip 데이터를 사용하여 진행
().item → 카테고리 별 아이템 코사인 유사도 데이터  
user_pur → 유저의 구매한 목록, 카테고리 등  
product → 판매된 아이템 목록










## error
08-04 15:42
카테고리 최빈값이 2개 이상일 경우 에러
→ 최근 카테고리로 진행(예정)


