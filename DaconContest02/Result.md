## 결과

2월 29일자로 월간 데이콘 2 천체 유형 분류 공모전이 끝났다.

처음 해보는 공모전이어서 열심히 준비해보았다. 딥러닝 모델만 이용해서 천체를 예측하였다. 다양한 시도가 있었는데 epoch에 따라 learning rate를 조절해보기도 하고 ResNet에서 사용하는 skip connection 방법이나 DenseNet 구조와 비슷하게 만들어서 실험해보았다. Sequential model보다 DenseNet에서 사용하는 구조를 유사하게 만들어 더 적은 epoch에서  수렴하는 것을 확인할 수 있었다. 하지만 주어진 데이터에서 데이터 가공을 적게 하면 어떠한 방법을 시도하더라도 log_loss 값이 특정 값 이하로는 내려가지 않았다. 

단일 모델을 사용할 경우 보다는 ensemble 모델을 사용할 경우에 점수가 더 좋았다. Sklearn에 있는 딥러닝 모델을 VotingClassifier를 사용했을 때 더 좋은 점수가 나왔다. StratifiedKFold를 사용한 모델은 시간이 부족해서 제출하지는 못했지만, 아마도 VotingClassifier와 유사했을 것이라 생각한다. 

해결하지는 못했지만 Type에 데이터가 굉장히 불균형했다. 어떤 type은 전체의 1%에 미치지 못하기도 했고 어떤 천체는 25%를 차지하기도 했는데 이러한 문제 역시 앞으로 마주칠말하기 때문에 적절히 해결할 방법을 찾는 것이 필요하다. 이상치 처리하는 몇가지 방법도 배웠다.

등수 안에 드는 몇몇 사람들의 결론을 보면 존재하는 열과 천문학적 지식을 이용해서 다양한 연산을 통해 새로운 열들을 만들어내어 모델을 만드는데 사용하였다. 지금까지 본 코드로는 LightGBM, XGBoost 와 같은 방법을 사용하여 모델링을 했다. 딥러닝 모델만이 해답은 아니고 다양한 머신러닝 모델이 뛰어난 결과를 내는 것도 보았다. 경우에 따라 머신러닝이나 딥러닝 모델을 사용하는 것을 선택하는 것도 중요한 요소가 될 것이라고 생각한다. 딥러닝 모델만이 최고가 아닐 수도 있다는 것을 알았고, 머신러닝이든 딥러닝이든 하이퍼파라미터 튜닝과 데이터를 적절히 가공하는 일 역시 중요하다는 것을 배웠다. 





