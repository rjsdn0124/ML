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