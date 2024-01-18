# TIL
매일 배운 것을 기록합니다
## 2024
<details>
  <summary>1월</summary>
  -  <summary>0118</summary>
  - SELECT  C.CAR_ID AS CAR_ID
      , C.CAR_TYPE AS CAR_TYPE
      , ROUND(C.DAILY_FEE * 30 * (1 - P.DISCOUNT_RATE/100),-1) AS FEE
FROM CAR_RENTAL_COMPANY_CAR C
     INNER JOIN CAR_RENTAL_COMPANY_DISCOUNT_PLAN P ON C.CAR_TYPE = P.CAR_TYPE
                AND P.DURATION_TYPE LIKE '30%'
                AND c.car_type IN ('세단','SUV')# 세단,suv 중 30일 이상인 차만
     LEFT JOIN CAR_RENTAL_COMPANY_RENTAL_HISTORY H ON C.CAR_ID = H.CAR_ID 
               AND ('2022-11-01' BETWEEN H.START_DATE AND H.END_DATE 
                    OR '2022-11-30' BETWEEN H.START_DATE AND H.END_DATE)
                    #11월 1일-30일 내에 대여 기간이 겹치는 차
WHERE H.CAR_ID IS NULL #대여기간이 안겹치는 차 (즉, 대여가능한 차)
      AND ROUND(C.DAILY_FEE * 30 * (1 - P.DISCOUNT_RATE/100),-1) 
          BETWEEN 500000 AND 1999999 #금액조건
ORDER BY FEE DESC, CAR_TYPE ASC, CAR_ID DESC

#그런데 left join 방식으로 하면 같은 차를 여러번 대여할 수 있으므로 기준 테이블의 행에 조인 되는 행이 2개 이상이 되면 중복값이 생긴다는 것을 주의해야할 것 같다.
# 물론 여기에서는 일부러 NULL값만을 추출하는 것이라 해당 없지만! 혹시 저 조건에 맞는 행을 추출하고 싶었다면 distinct 혹은 group by를 통해 중복값을 제거해야한다.
  -  <summary>0117</summary>
  -  우피 디벨롭, 그로스해킹 일독
  - <summary>0114</summary>
  - 포트폴리오 PDF 작성
  - <summary>0113</summary>
  - 현장에서 바로 써먹는 데이터 분석 with 파이썬 도서 다중회귀분석
  - <summary>0112</summary>
  - 집중력과 수면, 휴대폰 사용시간 상관관계 및 다중회귀분석 디벨롭
  - <summary>0108</summary>
  - 추천시스템의 성능개선 (rank_aware)검색모델 평가지표 MRR, MaP, nDCG 일독 
  - <summary>0107</summary>
  - A/B TEST 도서 (~40p)
  - <summary>0106</summary>
  - 추천시스템에서 피어슨, 코사인 유사도 구현하는 글 업로드
  - https://blog.naver.com/malcha0808/223314589405
  - <summary>0105</summary>
  - RMSE
  <summary>0103</summary>
  - 피어슨 상관관계
  <summary>0102</summary>
  - 인프런 : 웹사이트 퍼포먼스 분석 - 02
  <summary>0101</summary>
  - 데이터 로그 지표 설계 - 03. 로그 설계 질문 및 보완(고정 파라미터 vs 가변파라미터)
</details>


## 2023

  <details>
  <summary>12월</summary>
   <summary>1228</summary>
  - A/B 테스트 1/4 읽고 요약하기
  - SQL ga관련 코드 2개 풀기
    <summary>1227</summary>
  - Tracking Plan 작성하기
   <summary>1226</summary>
  - 다양한 사례로 익히는 SQL 데이터분석 5개 강의 듣고 복습 (페이지별 이탈율/종료율)
   <summary>1211</summary>
  - 모각공 스터디 시작, 데이터로그지표 설계하기 강의 듣고 문제풀이, 블로그 글 업로드
  <summary>1207</summary>
  - [CF기반 추천시스템 디벨롭] 유사도 계산 방식 비교 (코사인 VS 피어슨) 블로그 글 정리 (https://blog.naver.com/malcha0808/postwrite?categoryNo=18)
  <summary>1201</summary>
  - 와인 추천시스템 구현
  </details>

  <details>
  <summary>11월</summary>
  <summary>1129</summary>
  - 다양한 사례로 익히는 SQL 데이터분석 5개 강의 듣고 복습
  <img src="https://github.com/malchalog/TIL/assets/141055063/8e190268-62a9-49e9-b0ba-bcd398ced6ce"  width="700" height="370">
  </details>





