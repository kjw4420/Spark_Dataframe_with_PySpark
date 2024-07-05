# Spark_Dataframe_with_PySpark
# 실습파일 목록
### 1. PySpark_DataFrame_1: 헤더 없는 CSV 파일 처리하기(워밍업)
- 입력 데이터: 헤더 없는 CSV 파일
- 데이터 스키마 지정
- SparkConf 사용
- measure_type값이 TMIN인 레코드 대상으로 stationId별 최소 온도 찾기
  * 판다스 데이터프레임으로 처리
  * Spark로 처리
---
### 2. PySpark_DataFrame_2: 헤더 없는 CSV 파일 처리하기
- 입력 데이터: 헤더 없는 CSV 파일
- 데이터 스키마 지정하기
  * ust_id, item_id, amount_spent 데이터 컬럼으로 추가
- cust_id를 기준으로 amount_spent의 합 계산
  * MAX와 AVG 구하기
- Spark SQL로 처리
---
### 3. PySpark_DataFrame_3: 텍스트 파싱해서 구조화된 데이터로 변환(비정형 -> 반정형 데이터(JSON))
- 입력 데이터: 텍스트 파일
- Regex 활용
  * 텍스트에서 필요한 데이터만 파싱
  * \S+: 하나 이상의 비공백 문자 ex) 2021-01-04, $28.32 (비공백 문자)
  * \d: 하나 이상의 숫자 ex) 85001
  * .*: 아무 문자나 0개 이상 ex) ABC Hauling(공백있어도 됨)
- 반정형 데이터(JSON) CSV 파일 저장
---
### 4. PySpark_DataFrame_4: Stackoverflow Survey 기반 인기 언어 찾기
- stackoverflowCSV 파일에서 다음 두 필드는 ';' 구분자로 프로그래밍 언어 종류 구분
  * LanguageHaveWorkedWith: 가장 많이 사용되는 언어
  * LanguageWantToWorkWith: 가장 많이 사용하고 싶은 언어
- 이를 별개 레코드로 분리하여 가장 많이 사용되는 언어 top50과 가장 많이 쓰고 싶은 언어 top50 계산
---
### 5. PySpark_DataFrame_5: Redshift 연결 및 MAU(Monthly Active User) 계산
- 두 개의 테이블을 Redshift에서 Spark로 로드
  * JDBC 연결 실습
- DataFrame과 SparkSQL 사용해 조인
- DataFrame JOIN
  * left_DF.join(right_DF, join condition, join type)
---   
### 6. PySpark 설치 및 테스트 
- PySpark + Py4J 설치
  * 구글 Colab 가상서버 위에 로컬 모드 Spark을 실행
  * Py4J: 파이썬에서 JVM내에 있는 자바 객체를 사용가능하게 해줌
  * Local Standalone Spark 사용
- 테스트
  * Python 객체(리스트) -> RDD 변환
  * Python 객체(리스트) -> Dataframe 변환
  * Spark Dataframe으로 로드
