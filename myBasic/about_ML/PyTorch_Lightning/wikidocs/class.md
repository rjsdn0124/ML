# Class

## Function & Class

- 파이썬은 전역 변수와 같은 이름으로 지역 변수를 생성할 수 있다. 그래서 전역 변수를 사용할 땐 global 키워드를 이용해서 선언해주어야한다.

- 클래스 사용법
``` py
class Calculator:
    # 클래스에서 지역으로 공유하며 사용하는 변수.
    def __init__(self):
        # 생성자 함수 선언
        self.result = 0 # 객체 할당 변수
        
    def add(self, num):
        self.result += num
        return self.result
```

### super
- 자식 클래스애서 부모 클래스의 내용을 사용하고 싶을 경우
- super().__init__()으로 생성자에서 사용하여 매개변수로 부모 클래스의 변수에 저장. 앞 뒤 상관 x
- self는 이 함수를 쓸 인스턴스 자신을 호출하는 단어.