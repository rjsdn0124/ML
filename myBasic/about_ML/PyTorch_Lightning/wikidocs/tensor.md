# Tensor

### Tensor shape
- 텐서는 보통 2D형태로 표현을 한다. But 자연어 처리에서는 3D형태로 사용한다.
- 2D: ( *Batch Size* (전체 데이터를 사용하기엔 많으니 나누는 과정인 Batch를 통해 나눠진 size), *dim* (해당 데이터가 표현된 Tensor의 차원))
- 3D: (Batch Size, length(단어의 갯수), dim(해당 단어가 표현된 Tensor의 차원))


## PyTorch & Numpy

### Numpy basic
- how to use
```py
import numpy as np

t = np.array([0,1,2,3,4])
print(t.ndim) # 1 - print dimension
print(t.shape) # (7,) - print shape(1x7)
```
- 배열과 같음. 
- '-1' 인덱스를 통해 뒤에서부터 참조하는 방식도 가능.
- Slicing: [시작번호 : 끝번호]로도 가능. 끝 번호는 출력에 포함이 안 됨. 시작 번호가 생략된 경우는 처음부터 시작하고 끝 번호가 생략된 경우에는 마지막 원소까지 참조.

### PyTorch
- how to use
```py
t = torch.IntTensor([0,1,2,3,4,5])
print(t) # tensor([0,1,2,3,4,5])
print(t.dim()) # 1
print(t.shape) # torch.Size([7]) - shape
print(t.size()) # torch.Size([7]) - shape
```
- Numpy와 비슷함. but better
- slicing이랑 원소 참조 방법은 똑같음.
- 2차원 행렬에서 
```py
t = torch.FloatTensor([[1., 2., 3.],
                       [4., 5., 6.],
                       [7., 8., 9.],
                       [10., 11., 12.]
                      ])
#첫번째 차원 전체 선택한다는 의미. 비워놓는게 아님! 그러고 2번째 차원에서 첫 번째 원소를 참조.
print(t[:,1]) #tensor([ 2.,  5.,  8., 11.])

#첫 번째 차원 전체 선택해서 해당 차원 내부 원소들 중 마지막 전까지 모든 원소를 참조하겠다는 의미. 각 차원 모두 해당.
print(t[:,:-1]) 
#tensor([[ 1.,  2.],
#        [ 4.,  5.],
#        [ 7.,  8.],
#        [10., 11.]])
```
- broadcast: 자동으로 Tensor에 대해서 사칙 연산을 수행함.
<br/> ex) (1x2), (2x1) Tensor에 대한 연산에서 두 Tensor size를 (2x2)로 바꿔서 연산을 진행한다.
- 행렬 곱셈(t1.matmul(t2)과 그냥 일반 원소끼리의 곱셈(t1.mul(t2) | t1 * t2) 둘 다 가능하다.
- 평균: .mean()함수로 평균을 구할 수 있다. 인자로 dim = ? 을 받아 ? 자리에 넣는 차원을 빼고 나머지 차원에서의 평균을 구해서 표현한다. -1은 항상 마지막을 의미. -1을 ?에 넣으면 마지막 차원 제외
- 덧셈: .sum()함수로 평균과 같은 느낌으로 진행. 평균이 더한 값을 전체로 나눈 값이기 때문. 인자로 받는 dim도 똑같은 원리.
- 최대: .max() 함수로 데이터 중 가장 최댓값을 반환한다. argmax() 함수로 최댓값이 존재하는 인덱스를 반환한다. max함수에 dim을 인자로 주면 해당 차원을 제거한 나머지 차원에서의 최댓값을 반환하고 각 인덱스의 위치를 알려준다. argmax와 같음.

### 알짜 배열 상식
- (3,2,2): 3x2x2 배열. 첫번째 차원은 3, 두번째 차원은 2, 세번째 차원은 2. 순서는 shape이 바뀌면 계속 바뀜

### Tensor Manipulation
- View: Numpy에서의 Reshape와 같은 역할을 함. Tensor의 크기(Shape)를 변경해주는 역할을 함.
``` py
t.view([-1,3]) # (?,3)크기의 tensor로 변경
```
- Squeeze: 1인 차원 제거. 한 라인으로 이루어진 차원을 모두 제거한다.
- Unsqueeze: 인자로 넣어준 차원에 1인 차원을 추가한다. view(1,-1)로 하면 같은 효과.

### Tensor Type Cast
- 자료형Tensor()형식으로 해주면 됨. 자료형 바꾸려면 .자료형()만 붙여주면 된다.

### concatenate
- .cat([t1,t2(합칠 배열)], dim = 0(길이를 늘릴 차원))

### stacking
- stack([x,y,z (쌓을 배열)],dim=1(쌓아서 길이를 키울 차원))

### one/zero _like
- .ones_like()/.zeros_like(): 기존 텐서를 0이나 1로 바꾸는 함수. 

### In-place Operation
- 덮어쓰기 연산: 연산 뒤에 '_'를 붙이면 기존 값이 있던 변수의 데이터를 연산한 결과로 덮는다.