ItsNED 

* 그러면 나중에 도커 업뎃할때 짜증나실거 같은데 제가 생각만하고 아직 하진 않았는데 위에 패키지들만 설치한 base 이미지를 하나 만들고 django관련은 그 이미지를 이용해서 도커라이징을 하면

raha vabadus

* Ubuntu + Python3 + 패키지 + 댕고 + nginx만해서 1개 묶고 DB만 1개 묶으면.. (용량차이는 의미없습니다 이미) 그런데 NLP용 패키지들 업데이트 한번하면 0.X 기가 단위로 용량 변하는데.. 
* Docker Pack IO cost vs Deploy cost해서 결정하시면 되지 않을까요? 아니면 어딘가의 G모사 처럼 (장고+nginx) + Process Docker + DB Docker 3 Tier 로 많이 나눕니..다..
* 마이크로서비스 개념 이럴때 쓰시면.. 그걸 다 관리하기 귀찮아서 웹인터페이스(장고+nginx) <=> NLP / AI / BigData / Search Engine <=> DB 이렇게 묶는 곳도 있더라구요

Papercraft

- 도커허브 쓰세요! 이미지 자동으로 빌드 해줘요
- 도커 풀하면 도커 이미지를 받을 수 있습니다
- 로컬에서 빌드 하지 않아도 되어요
- 깃허브랑 도커 허브 그냥 연동하면 dockerfile인가 있으면 알아서 만들어 줘서 
- 머신러닝 하는 부분만 Restful로 다른 서버로 따로 때. 저거 서버 하나위에서 돌리면 잘못하면 훅 갈것 같... 들어오는 요청별로 머신러닝 모델이 존재하는 서버로 요청 포워딩 해줘. nginx같은거 써서 하면 편할거야
- 너 어차피 장고부분은 html css js 다 스테틱 파일에 넣어놓고 작업하는거잖아. 뷰랑 연결된 메인 로직들은 너가 restful 하게 안짰을 테니 수정하는데 귀찮을거니까 놔두고 머신러닝만 api식으로 따로 때서 다른 서버에 올려