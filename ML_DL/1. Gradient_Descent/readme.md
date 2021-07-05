### Gradient란?
- 기울기
- error에 대한 각각 모델 파라미터의 변화량

### Gradient Descent란?
- ML, DL에서 자주 사용하는 최적화 알고리즘
- 방법: 주어진 데이터로 loss를 구함 -> loss에서 gradient 구함 -> gradient 방향으로 조금 움직임
- learning rate가 중요한 역할을 함

    <img src="https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/gradient-descent-learning-rate.png" width="600">

### Gradient Descent 종류
- Batch Gradient Descent
    -  데이터 전체로 하는 gradient descent
    -  local minimum에 빠질 수 있음
    -  computationally expensive
- Stochastic Gradient Descent(SGD)
    - 사전의미로는 batch size 1로 하는 gradient descent
    - 실제 구현은 batch size 1 이상(batch size 2 이상인 gradient descent은 Mini-Batch Gradient Descent)
    - 데이터 일부만 사용하므로 gradient에 노이즈가 많음
    - 노이즈가 많아서 오히려 local minimum에서 빠져나옴
    - computationally inexpensive
