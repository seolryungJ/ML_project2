![image](https://github.com/seolryungJ/ML_project2/assets/131641261/96b49d68-af5b-4e3e-8f25-fd32abda0e91)# ML_project2
Olist 이커머스 기업 리뷰를 통한 매출 예측 및 자동화 대시보드 구축


# Olist 이커머스 기업 리뷰를 통한 매출 예측 및 자동화 대시보드 구축
      - 파이 팀 프로젝트
      - 진행기간 : '23.08.10 ~ '23.09.07
      - 팀원명 : 김나영, 박성호, 이민수, 정설령, 정원근

## 목차

## 소개
- 주제 : Olist 이커머스 기업 리뷰를 통한 매출 예측 및 자동화 대시보드 구축
- 목표 : 매출 예측과 실시간 대시보드 모니터링을 통한 최적의 마케팅 전략도 

## 프로젝트 배경
- 배경
  - 이커머스 플랫폼이 성장하면서 활용 가능한 데이터가 많아졌고, 데이터 분석은 기업의 의사결정 단계에서 필수요소가 됨
  - 기업의 매출 증대와 향후 방향성 제고를 위해 전반적인 기존 매출 현황 분석이 필요하다고 판단
  - 따라서, 자동화 대시보드를 구축해 주/월/분기 별 매출을 실시간으로 확인하고, 매출 예측을 통해 개선사항을 도출함

## 데이터
- 데이터 소개
  - 데이터 출처 : [캐글]([https://dacon.io/competitions/official/236118/data](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce))
  - 9가지 데이터셋 ![image](https://github.com/seolryungJ/ML_project2/assets/131641261/caa7d42c-b1b7-4cdc-8e70-a130d3d89e42)
    - customer_dataset
    - orders_dataset
    - order_items_dataset
    - order_payments_dataset
    - products_dataset
    - order_reviews_dataset
    - sellers_dataset
    - geolocation_dataset
    - category_english

## EDA
1. 기간, 상품
    - 2017~2018년 월별 매출 증감 ![image](https://github.com/seolryungJ/ML_project2/assets/131641261/01dd8e3a-1995-443b-9327-211690cbb898)
    - 2017~2018년 분기별 매출 증감 ![image](https://github.com/seolryungJ/ML_project2/assets/131641261/33e18117-a72f-4fd3-8c02-e44eed4f383d)
    - 상품별 분석 <img width="563" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/eaf94496-d919-4c42-b269-e201b33e0c50">

2. 위치
    - 위치별 구매 분석 <img width="977" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/0cf931db-9118-4ee3-9bf1-ca3f8c290003">
    - 배송기간 분석 <img width="969" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/741ba729-0f56-4374-ae3b-b89e656c1675">
    - 운송비 분석 <img width="965" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/235901be-a111-4a4c-a2a8-a846eee6e800">
    - 배송기간에 대한 분석 <img width="500" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/b08b8cb7-7c61-46d4-99d7-745dfe41a0d6">

3. 구매자
    - 구매자의 구매 시간 분석 ![image](https://github.com/seolryungJ/ML_project2/assets/131641261/2c21c63c-c466-4b81-b437-5a04aab92122)
    - 결제 방법에 대한 분석 <img width="966" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/85d64893-fb09-4136-bd39-adfc0288da33">
    - 리뷰 키워드를 통한 분석 <img width="576" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/5c50c4e7-68e9-45b8-a6ca-a827a2edca0a">

## 매출 예측 모델링
1. 9가지 데이터셋 병합
2. 데이터 전처리 수행
    - 주문 날짜 변수로 년, 월, 일, 분기 파생변수 생성
    - 현재 일자를 ‘2018.05.12’ 라고 가정
      - 학습 데이터셋 : ~ 2018.03.31까지의 데이터
      - 테스트 데이터셋 : 2018.4.1 ~ 2018.6.30 사이의 데이터
    - 지역, 카테고리 변수 라벨인코딩
3. 예측 모델 생성 및 변수 선정
    - 모델 1(날짜) : 구매일자의 년, 월, 일, 매출액
    - 모델 2(날짜 + 카테고리) : 구매일자의 년, 월, 일, 분기, 카테고리, 매출액
    - 모델 3(날짜 + 지역) : 구매일자의 년, 월, 일, 지역, 매출액 
4. 테스트 및 평가
    - 모델 비교
      <img width="576" alt="image" src="https://github.com/seolryungJ/ML_project2/assets/131641261/b7fb9f19-763b-4273-b907-d065eea2b05c">
      ![image](https://github.com/seolryungJ/ML_project2/assets/131641261/afaae739-dcff-40bd-9257-2d30738cf10f)

## 대시보드 구현 
