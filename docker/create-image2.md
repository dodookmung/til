# Docker 이미지 생성 응용

<https://velog.io/@tastestar/Docker-Cli>

### 도커파일 만들기

```docker
# 1. 우분투 설치
FROM ubuntu:18.04

# 2. 메타데이터 표시
LABEL "purpose"="practice"

# 3. 업데이트 및 아파치 설치
RUN apt-get update
RUN apt-get install apache2 -y

# 4. 호스트에 있는 파일을 추가
ADD test.html /var/www/html

# 5. 작업공간 이동(=cd)
WORKDIR /var/www/html

# 6. 거기서 test2.html 파일생성
RUN ["/bin/bash", "-c", "echo hello > test2.html"]

# 7. 포트 80번 노출 지정
EXPOSE 80

# 8. 컨테이너 생성시 시작명령어
CMD ["apachectl", "-D", "FOREGROUND"]
```
</br>

```
* FROM : 생성할 이미지의 베이스가 될 이미지를 뜻합니다.
* LABEL : 이미지에 메타데이터를 추가합니다.
* RUN : 이미지를 만들기 위해 컨테이너 내부에서 명령어를 실행합니다. -y 꼭넣어줘야합니다.
* ADD : 파일을 이미지에 추가합니다. 여기서는 Dockerfile이 위치한 폴더에 test.html 파일을 가져와서 이미지의 /var/www/html 디렉터리에 추가합니다.
* COPY : 파일을 이미지에 추가, 로컬 파일 이미지에 추가
* WORKDIR : 명령어를 실행할 디렉토리
* EXPOSE : 이미지에서 노출할 포트를 설정합니다.
* CMD : 컨테이너가 시작될 때마다 실행할 명령어
* ENTRYPOINT : 컨테이너가 시작될 때마다 실행할 명령어를 설정
* ENV : 환경변수 지정
* VOLUME : 호스트와 컨테이너 내부의 디렉토리를 설정하여 데이터를 공유합니다. 도커 실행시 -v 명령어로 지정해야 볼륨이 생성됩니다.
```
</br>

### 컨테이너 이미지를 빌드

```bash
docker build [OPTIONS] 도커파일경로
```

* -t : 플래그는 이미지에 태그를 지정해줍니다. 사람이 읽을 수 있는 최종 이미지의 이름으로 생각하면 되고, 이미지 이름을 지정했기 때문에 컨테이너를 실행할 때 해당 이미지를 참조할 수 있습니다.
* . : 현재 디렉터리에서 Dockerfile을 찾아야한다고 알려줍니다.
* --no-cache : 빌드 시, 캐시 기능을 사용하지 않습니다.
</br>
</br>

### 애플리케이션 실행

```bash
docker run -dp 3000:3000 getting-started
```

* -dp : 이 플래그는 새 컨테이너를 분리된 모드에서 실행하고 호스트의 포트 3000과 컨테이너 포트 3000간에 매핑을 생성하고 ㅣ있씁니다. 포트 매핑이 없으면 애플리케이션에 접근할 수 없습니다.