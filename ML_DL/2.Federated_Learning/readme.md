## Federated Learning이란?
- 모델 학습을 여러 대의 edge device에 나뉘서 하는 방법
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Federated_learning_process_central_case.png/880px-Federated_learning_process_central_case.png" width="600">
- 데이터가 edge device를 나갈 필요 없음 -> 학습된 파라미터만 공유함
- edge device에 있는 데이터는 학습할 때만 사용되고 서버에 보낼 필요가 없어서 보안이 좋음
- 보안을 위해 암호화랑 학습된 파라미터에서 특정 데이터 뽑을 수 없게 처리
- secure aggregation: 암호화된 정보들이 있을 때 각각은 복호화 불가능하지만 전체는 복호화 가능한 기법
- 일반적인 학습이랑 성능 차이 별로 없음
- 개인 정보 보호 필요한 의료쪽, 산업 기밀 보호 필요한 스마트공장, 실제 운전자 특성을 활용하는 자율자동차 에서 쓰임

설명 만화: https://federated.withgoogle.com/   
성능 분석글: https://sooyongshin.wordpress.com/2020/11/22/federated-learning/
