# Tensor Operation
- 텐서 다루는 법.

## Tensor?
- Tensor는 배열의 집합이다. 모든 차원의 배열을 Tensor라 부를 수 있다.

### use
- torch.~~ 형태로 초기화된 변수 x에 x.shape하면 고차원부터 저차원 순서로 안의 원소 수가 나온다. ','를 통해 각 차원별 원소 수를 각 변수에 저장 가능
- ex) nth,(n-1)th,~~ = x.shape 하면 각각 들어감.


### Shape
- 