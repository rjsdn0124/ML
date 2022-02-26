# Autograd

### 자동 미분
- requires_grad = True인 한 '스칼라' 텐서에 대한 수식이 있다면, 이 수식을 backward()함수를 통해 연산해서 해당 텐서에 기울기를 저장한다. w.grad 형태로 사용
- "reuqires_grad = True" param?
<br/> 해당 스칼라 텐서에 수식을 연산해서 나온 기울기를 저장하겠다는 선언