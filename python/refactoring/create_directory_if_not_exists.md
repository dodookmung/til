# 📁 디렉토리 생성 코드 단순화

- [공식 문서: os.makedirs](https://docs.python.org/3/library/os.html#os.makedirs)

---

## 👎 리팩토링 전

```python
import os

if not os.path.exists(result_path):
    os.makedirs(result_path)
```

## 👍 리팩토링 후

아래와 같이 한 줄로 리팩토링할 수 있습니다:

```python
os.makedirs(result_path, exist_ok=True)
```

## ✅ 리팩토링 포인트
`exist_ok=True`를 사용하면, `result_path`가 이미 존재하는 경우에도 예외가 발생하지 않습니다.
따라서 `os.path.exists()`로 사전 검사를 하는 코드는 중복이며 제거 가능합니다.

또한, 이 방식은 **race condition**을 방지합니다.
예를 들어, 멀티스레드 환경에서 `exists()` 검사 후 다른 스레드가 디렉토리를 만들면 `makedirs()`가 예외를 던질 수 있습니다.
`exist_ok=True`는 이러한 상황에서도 안전하게 동작합니다.