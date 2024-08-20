# venv 사용법

<https://blog.deeplink.kr/?p=942>

### venv의 장점

* **격리된 환경**: 다양한 프로젝트에서 서로 다른 패키지나 Python 버전의 충돌 없이 작업할 수 있다.
* **버전 관리**: 프로젝트별로 필요한 패키지와 그 버전을 쉽게 관리할 수 있다.
* **의존성 문제 해결**: 각 프로젝트의 의존성을 명확하게 알 수 있으므로 배포나 협업 시 문제를 최소화 할 수 있다.

### venv의 단점

* **추가적인 공간**: 각 가상 환경마다 패키지를 복제하기 때문에 디스크 공간이 추가로 필요하다.
* **관리**: 여러 가상 환경을 사용하면 관리가 복잡해질 수 있다.

<br>

### venv 사용방법

* **가상 환경 생성**<br>
**Windows**: python -m venv [가상환경명]<br>
**Linux/Mac**: python3 -m venv [가상환경명]

* **가상 환경 활성화**<br>
**Windows**: [가상환경명]\Scripts\activate<br>
**Linux/Mac**: source [가상환경명]/bin/activate

* **가상 환경 비활성화**<br>
모든 운영체제에서: deactivate

* **패키지 설치**<br>
활성화된 가상 환경에서, pip install [패키지명] 명령어를 사용하여 패키지를 설치한다.

* **requirements.txt를 활용한 패키지 설치**<br>
requirements.txt 파일 내의 패키지를 한번에 모두 설치할 때는,<br>
pip install -r requirements.txt 명령어를 사용하여 패키지를 설치한다.

* **가상 환경 내 패키지 리스트 확인 및 requirements.txt 만들기**<br>
가상환경 내 패키지 리스트 확인: pip freeze

* **가상환경 내 패키지를 requirements.txt 만들기**<br>
pip freeze > requirements.txt

* **가상환경 삭제하기**<br>
가상 환경은 결국 폴더 형태로 저장되기 때문에, 해당 폴더를 삭제하면 가상 환경도 함께 삭제된다.


</br>
특정버전으로 하고 싶으면 아래와 같이 하면 된다.

```bash
py -[버전] -m venv [venv명]
```
</br>
3.6버전으로 하고 싶으면 이렇게
```bash
py -3.6 -m venv venv36
```

</br>

하고싶은 버전이 없다면 컴퓨터에 해당 버전이 먼저 설치되어 있어야한다.

