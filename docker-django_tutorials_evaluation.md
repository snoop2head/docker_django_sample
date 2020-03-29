# Docker & Django tutorials evaluation



https://www.youtube.com/watch?v=KaSJMDo-aPs

- 완전 기초 튜토리얼: django sample page를 docker에 올리는 거에 의의를 두면 됨.



https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/single-container-docker.html

- docker로 elastic beanstalk으로 올리는 법. 
- 다만 완전 기초 튜토리얼 컨테이너는 1.12GB이므로 eb에 올라갈 수 있음
- Fitcuration으로 docker build한 것은 무려 4GB이므로, 아마 eb에 올릴 수 없을 것임.



https://realpython.com/django-development-with-docker-compose-and-machine/

- docker machine을 써야하는 것 때문에 탈락. 
- pipenv 같은 virtual environment가 아니라 쌩으로 로컬에서 돌리라는 듯



https://docs.docker.com/compose/django/

- official docs임에도 불구하고 버그가 득실득실: downvotes가 400개로써 upvote만큼이나 많음
- 기존 프로젝트를 dockerizing하는 것이 아니라 새로 프로젝트를 파야 함.
- 심지어 database 등록하는 것도 코드를 빼먹음. 



https://www.youtube.com/watch?v=KN8wuFi2RXM

- 참고할 만하나, 새로운 프로젝트를 파서 다시 시작하는 것임. 기존 프로젝트를 docker에 올리는 법은 나와있지 않음.
- 다만 yaml file, Dockerfile의 역할에 대해서 배우는 거에는 도움이 됨. 



https://www.youtube.com/watch?v=90LCcim-wHQ

- 진행 중



https://www.youtube.com/watch?v=90LCcim-wHQ

- Django version 1.10인게 걸리긴하지만, 진행은 해봐야 할 듯.





