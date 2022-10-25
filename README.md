# MapleAvatarReccommendation
딥러닝(CNN)을 사용한 메이플 코디 추천
## 배경
- 메이플 스토리 게임에서는 아바타 코디 대회에 참여하는 등 코디를 공유하고 즐기는 문화가 구축되어 왔다.

- 이에 따라 개개인의 취향을 고려하여 헤어 스타일을 지정하고, 사용자로부터 이미지 파일을 받아
색상에 기반한 인기 있는 코디를 추천하고자 한다.

- 사용자에게 이상형 월드컵을 통해 가장 선호하는 헤어를 고른 뒤, 아이템 칸에 아이템과 캐릭터를 넣었을 경우, 그에 알맞는 코디를 추천하고자 한다.

이미지

## 전체적인 개발 과정

### (1) 크롤링

- 데이터는 Maple.gg넷과 maple.io 등등에서 크롤링을 통하여 이미지들을 모아보았다. 코디와 아이템을 각각 4,000개 정도 수집하였다.

/br

### (2) 모델링

- CNN 모델 사용, 아바타 색상끼리 ①검은색, ②초록색, ③네이비색, ④분홍색, ⑤보라색, ⑥빨간색, ⑦하늘색, 
⑧노란색으로 분류하여서 학습시키기로 하였다.

- activation function은 relu와 softmax를 사용하였다. epoch = 50, patience =10으로 학습하였다.

- 코디만으로 데이터 셋을 학습한 경우 정확도가 90%, 아이템을 10% 정도 섞여서, 학습한 경우 정확도는 86% 나왔다.

/br

### (3) GUI

- QT designer라는 프로그램 사용하였다. 헤어를 고를 때, 이상형 월드컵으로 진행하였다. 최종적으로 GUI를 exe 파일로 만듦.

/br


### (4) 데이터베이스
- Azure 클라우드 서버에 사용자들이 평가한 평점을 데이터베이스에 쌓아서, 
추천할 아이템들의 웨이트를 주어서 사람들이 좀 더 선호하는 아이템을 추천한다.
