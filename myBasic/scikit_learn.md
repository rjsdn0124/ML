# scikit-learn

## K-NeighborsClassfier
```py
    from sklearn.neighbors import KNeighborsClassfier
    kn = KNeighborsClassfier()
    kn.fit($input, $target)
    kn.score($input, $target)
```
- 새로운 데이터가 들어왔을 때 해당 데이터 주변 일정 범위 중 가장 많은 데이터의 값으로 학습.
- fit()함수는 사이킷 런 패키지 내부 메소드로써 input 값과 target 값을 parameter로 받아 target에 맞게 input값들의 값을 학습시키는 함수이다.
- score()함수는 input값을 넣어서 학습한 모델이 input값들을 추정하여 나온 값과 target값을 비교하여 0.~~ 로 점수 매겨주는 함수.
- input은 dataframe 배열, target은 해당 인덱스의 인간이 추정한 결과값.