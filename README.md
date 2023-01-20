# docker-monitoring-module

## 설계
* Docker SDK for Python
  * [Docs](https://docker-py.readthedocs.io/en/stable/index.html)
  * 해당 SDK가 제공하는 API를 이용하여 도커 컨테이너의 메트릭을 가져옴
* Psutil
  * 호스트 시스템의 자원 정보를 불러옴
  
## 모듈
* 폴더 내부에 docker_inspection.json과 docker_stats.json이 있다. 이는 파이썬 SDK에서 docker stats 명령어와 docker inspection 명령어의 역할을 하는 메서드의 결과물을 저장한 것이다. 이 json 구조를 참고하여 코딩하였다.

* 필요한 메트릭은 Docker Doc를 참고하여 주어진 공식대로 원하는 메트릭을 계산하여 사용하였다 ([출처](https://docs.docker.com/engine/api/v1.41/#tag/Container/operation/ContainerStats))
![image](https://user-images.githubusercontent.com/57928967/213635488-9f3ffb13-bf51-42f9-a68e-3fc3ba414aca.png)

## 폴더 구조 설명
* Data : json 출력물을 저장하는 폴더
* Docker_inspection.json : client.container.atts의 결과물
* Docker_stats.json : client.container.stats의 결과물
* Requirements.txt : 해당 프로그램을 돌리는데 필요한 종속성을 기록한 txt 파일

## 데모
![image](https://user-images.githubusercontent.com/57928967/213634888-9f65bebf-fa9e-4046-9f42-c5b35e3f0de8.png)
