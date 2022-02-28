# torch,nn

### nn.Flatten
- 계층을 초기화하여 각 28x28의 2D 이미지를 784 픽셀 값을 갖는 연속된 배열로 변환합니다.

### nn.conv2d ????
- convolution2d, (input 채널수, 출력되는 채널 수, ...)로 받는다.

### nn.Sequential()
- nn.Module 층을 차례로 쌓을 수 있또록 함. 여러 함수들을 연결해주는 역할. 이를 통해 인공 신경망을 구현할 수 있다.



# torch

### torch 연산
- 연산 후 나온 tensor에 인자로 함께 grad_fn이 들어간다. 이는 역전파 하기 위해 어떤 연산을 통해 나온 결과인지 저장하는 역할이다.