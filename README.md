# 따밥따밥
### 선한영향력가게와 무료급식소 데이터들을 받아와 SQL에 연동시키고, 접속해 SQL 구문을 사용해 특정 데이터만 가져와 활용했던 과정들
csv 파일은 3개
1) 선한영향력 가게
2) 무료급식소
3) 무료급식소 운영시간 정보

sql_gupsik.py, sql_stores.py, sql_hours.py 는 csv 파일들을 sql의 table에 저장해주는 코드

<선한영향력 가게>
category.py 코드는 SQL에서 가게들을 제공대상으로 분류해 해당하는 가게들만 리턴시켜준다
create_map.py 코드는 folium module을 사용해서 지도를 만들어준다
- selenium 모듈을 이용해서 웹사이트에 접속해 현재 위치의 위도와 경도를 가져와 지도에도 표시해준다
- 각 가게의 위도와 경도에 팝업을 표시해준다
  - 이 팝업은 html_store.py의 popup_html 함수를 가져와 format한다
- category.py에서 분류했던 데이터로 세개의 지도를 생성한다
<img width="1439" alt="Screen Shot 2022-05-20 at 4 08 27 PM" src="https://user-images.githubusercontent.com/99851347/169473006-8eeb2276-0256-48bf-afde-a0a2252a8c0c.png">


<무료급식소>
sql_open_close.py는 sql구문을 실행하는 코드
- 무료급식소의 운영시간이 현재 시간과 요일 사이에 있으면 현재 열려있는 급식소로 판단해 열려있는 급식소들만 리턴해준다
practice.py 코드는 무료급식소 지도를 생성해준다
- sql_open_close.py 파일 내에 open_close() 함수를 실행시켜 리턴된 가게들은 open 그룹 안에, 그렇지 않은 가게들은 closed 그룹 안에 넣어준다
- 지도 우측 상단에는 라디오 버튼 두개가 생겨 open/closed 된 가게들을 편리하게 볼 수 있다
