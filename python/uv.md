# uv 사용법 

<https://wikidocs.net/238310>

uv 설치 
```bash
# On macOS and Linux.
curl -LsSf https://astral.sh/uv/install.sh | sh

# On Windows.
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# With pip.
pip install uv

# With pipx.
pipx install uv

# With Homebrew.
brew install uv
```


## 가상 환경 만들기

python -m venv .venv에 해당하는 명령어이다.
```bash
uv venv .venv
```

### 파이썬 환경 설정 

-p <파이썬 버전> 인자를 추가해 파이썬 버전을 지정해 다운로드할 수 있다.
```bash
uv venv -p 3.13
```

### Installing packages

```bash
uv pip install flask                # Install Flask.
uv pip install -r requirements.txt  # Install from a requirements.txt file.
```

uv init은 복잡해서 나중에 배워야 할 듯