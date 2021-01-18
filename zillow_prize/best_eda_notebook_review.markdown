## Zillow EDA best notebook review
Notebook link: <https://www.kaggle.com/philippsp/exploratory-analysis-zillow>

<br>

Kaggle Zillow [Zillow Prize: Zillow’s Home Value Prediction (Zestimate)](https://www.kaggle.com/c/zillow-prize-1/overview) 의 best EDA notebook이 어떤 특징을 갖고 있고, 내 노트북과 비교했을 때 어떤 점이 더 나은지를 분석한다.




### 1. Target value에 대한 이해
내 노트북에서는 target 값인 logerror에 대해 정확히 이해하지 않고 EDA를 진행했다. 하지만 best notebook에서는 logerror에 대한 간략한 해석을 포함하여 target 값에 대한 이해를 도왔다.
 + logerror > 0 : overestimation of price
 + logerror < 0 : underestimation of price
 + absolue logerror: how well estimated price
 <br>
 등으로 경우를 나누어서 target을 분석했다. 이에 따라 뒤에서 진행되는 EDA도 absolute logerror과의 관계 등을 포함하여 분석의 일관성과 질을 높였다.
 
 
### 2. 분명하고 이해하기 쉬운 시각화
내 노트북도 시각화에 최대한 공을 들였기 때문에 시각화는 나름 잘 됐다고 생각하지만, best notebook에서의 시각화는 정말 이해하기 쉬웠다. 예를 들면 다음과 같다. 
+ missing value 시각화: 데이터의 결측값을 파악할 때, 나는 표로 missing 비율을 나타내고 끝냈다. 하지만 best notebook에서는 missing value에 대한 시각화를 진행하여 missing 비율이 높을수록
barplot이 길어지게 표현했는데, 한눈에 어떤 변수가 missing이 많은지를 파악할 수 있었다.
+ 지도시각화: latitude, longitude를 이용해 couty를 시각화할 때, folium을 이용해 어떤 지역에서 transaction이 이루어지는지를 더 자세히 표현했다. 그리고 이에 더하여 지역별로 logerror 분포가
 어떤지 heatmap으로 표현했는제 정말 좋은 아이디어라고 생각했다. 
 
### 3. Target value를 이용한 overfit, underfit 분석
Target인 logerror을 이용하여 absolute logerror(예측이 정확도)를 정의하고, 어떤 변수의 어떤 구간에서 overfit 혹은 underfit이 되는지를 plot했다! 기준은 absolute error < 0.01이면 best fit
이런식으로 정했다. 굉장히 좋은 아이디어라고 생각하는데, 이렇게 특정 변수에서 underfit이 되는 구간을 찾으면 모델링 후 post processing을 진행하거나, feature engineering을 할 때 이부분을
보완하면 모델의 성능을 더 높일 수 있을 것 같았다.
