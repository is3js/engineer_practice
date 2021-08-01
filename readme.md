## Guide

![image-20210801203005753](https://raw.githubusercontent.com/is3js/screenshots/main/image-20210801203005753.png)

- 분석을 위해 제공된 DB 중 분석에 사용된 칼럼 위주로 diagram을 그리면서 분석을 시도했습니다. 주 분석도구는 Anaconda환경의 jupyter notebook입니다.

  - 번호가 매겨진 ipynb마다 sql 일부 및 python으로 구현된 코드및 주석으로 코드 설명이 구현되어있습니다.
  - 구현된 코드 및 결과물 확인만 원하는 경우 가장 마지막 ipynb인 `03_Total_Code_and_Results.ipynb`의 하나씩 Run하면 됩니다.

- 분석 과정

  1. postgresql remote server에 접속.
     - jupyter notebook의 `ipython-sql extension`을 사용하여 해당 server에서 `table_name`을 받아와 저장합니다.
  2. 8개의 Table -> pandas DataFrame으로 변환.
     - `psycopg2` package를 이용하여 1.에서 얻은 `table_name`으로 sql쿼리를 작성하여 `DataFrame으로 변환`합니다.
  3. 각 DataFrame을 Local에 pickle형식 저장.

     - git clone한 프로젝트 폴더내 data폴더(`./data/`)에 pickle로 저장합니다.

  4. 저장된 pickle을 불러와 로컬에서 분석을 시작합니다.
     - 4번 연습문제의 경우, SQL WITH문을 활용한 hint가 주어졌으나, jupyter내 sql활용의 어려움 및 숙련도의 부족으로 WITH문을 pandas DataFrame으로 받아와 칼럼으로 분리하여 일부 테이블을 생성하였습니다.

  ```
  git clone https://github.com/is3js/engineer_practice.git

  pip install psycopg2 ipython-sql==0.3.9
  jupyter notebook
  ```
