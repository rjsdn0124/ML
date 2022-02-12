# Pytorch

## Tensor
- Tensor는 배열이나 행렬과 매우 유사한 특수한 자료구조이다. 
- Tensor는 GPU나 다른 하드웨어 가속기에서 실행할 수 있다는 점만 제외하면 NumPy 의 * ndarray와 유사함. 
<br/>* ndarray란?

        NumPy를 통해 만들어진 배열로써, 일반 파이썬의 list와는 다르게 c를 이용한 라이브러리이므로 메모리에 연속적으로 배치된다. 이로 인해 다수의 선형대수 연산의 속도를 향상시킬 수 있다.
- PyTorch에서는 텐서를 사용하여 모델의 입력(input)과 출력(output), 그리고 모델의 매개변수들을 부호화(encode)함.
- torch 생성하기
```py
    # data를 직접 선언해서 torch로 변환하기
    data = [[1, 2],[3, 4]]
    x_data = torch.tensor(data)

    # data를 ndarray형태로 만들어서 torch로 변환하기. torch -> ndarray도 가능
    np_array = np.array(data)
    x_np = torch.from_numpy(np_array)

    # tensor 속성 입히기
    x_ones = torch.ones_like(x_data) # 속성만(자료형, 모양) 유지
    x_rand = torch.rand_like(x_data, dtype=torch.float) # x_data의 속성에 dtype으로 float형을 쓰겠다 선언해서 해당 속성으로 덮어쓰기

```

[Pytorch Tutorial](https://pytorch-lightning.readthedocs.io/en/latest/)


[Pytorch Tutorial(한국에 뭐시기)](https://tutorials.pytorch.kr/)


