# 팬 데이터를 이용한 팬 등급 세분화
* 기업 요청에 따라 데이터 및 코드 비공개

감정분석 data : https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=86

## DATA
- 전체 데이터 수 : 502,810개

- 스티커 수(후원 수) : 1279개

- 채팅 방 : 240개

- 인원 : 7,476명


## 1. RFM 분석을 통한 팬, 채널 등급 분류
#### USER
R : 현재 – 최근 메시지 날짜 

F :  1일 평균 메시지 수 

M : 메시지 수*30원 + 스티커 액수

L : 활동 기간 ( 최근  날짜– 최초 날짜)


<img width="636" alt="image" src="https://user-images.githubusercontent.com/99347825/204079580-628a8c56-b2c8-4e08-9ed9-4b417dd65a83.png">

- **K-Means Clusterring** 사용

- **Elbow-Method**를 근거로 K=5로 결정

- **MinMaxScaler**를 사용하여 정규화


#### CHATING ROOM
R : 채널 유저들의 R 평균

F :  채널 유저들의 F 평균

M : 채널 유저들의 M 평균

<img width="584" alt="image" src="https://user-images.githubusercontent.com/99347825/204079711-cb2c8e90-5978-4cb0-904a-aa062117e938.png">


## 보완할 점
1. 감정분석 모델의 성능 : 더 나은 모델을 찾고 채팅 데이터를 라벨링하여 fine-tuning
2. 셀럽 행동 분석 : 셀럽 행동을 더 세부적(시간별, 채팅 내용별)으로 분석
3. 클러스터링 : 클러스터링 알고리즘을 바꿔가며 비교
4. RFM 분석 : 클러스터링이 아닌 5분위로 나눠 팬 등급 나눈 뒤 비교

