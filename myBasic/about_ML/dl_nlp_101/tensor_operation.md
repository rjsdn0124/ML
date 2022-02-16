# Tensor Operation
- 텐서 다루는 법.

## Tensor?
- Tensor는 배열의 집합이다. 모든 차원의 배열을 Tensor라 부를 수 있다.


### Shape
- 데이터 받아서 사용하려면 데이터의 모양을 알아야지(shape) 우리가 사용할 데이터의 형태에 맞출 수(reshape) 있다.
- torch.~~ 형태로 초기화된 변수 x에 x.shape하면 고차원부터 저차원 순서로 안의 원소 수가 나온다. ','를 통해 각 차원별 원소 수를 각 변수에 저장 가능
- ex) nth,(n-1)th,~~ = x.shape 하면 각각 들어감. 
- @@ reshape와 view는 거의 동일하지만 메모리 사용 방식이 다르다! 
    - reshape는 메모리 자체의 구조를 바꿔서 영구적으로 변수에 저장시키지만
    - view는 해당 tensor가 들어있는 메모리를 그냥 어떻게 바라볼지를 저장해놓음.
        - reference 같은 느낌. 따라서 기존 tensor가 저장된 내용이 바뀌면 같이 바뀐다!

### GPU
- gpu에 사용 가능!(cpu to gpu)
    - torch.tensor 호출 시에 device = 'cuda'를 넣어주면 gpu에 tensor를 놔두는겨!
    -호출 한 tensor를 gpu에서 다시 놔두고 싶다면 to('cuda')로도 사용 가능! 
        - gpu 갯수만큼 cuda:0~(갯수-1) 할당해서 어떤 gpu에 할당할지 정할 수 있음!
- gpu to cpu
    - .cpu()하면 끝!
- cpu인 상태에선?
    - tolist()함수와 numpy()함수 등 torch.tensor 상태의 tensor를 각각의 object로 바꿀 수 있다. %얘네는 cpu만 참조하기 때문!
    - scalar 상태의 데이터는 item()함수로 python 기본 형태로 바로 불러올 수 있다.

### Tensor Decomposition    
