# statistics

생존분석 목표
1. 생존 시간 분포 요약
2. 약물 간에 생존 시간 분포 비교
3. 생존 시간과 예측 인자 간에 분석


생존분석에서의 outcome 정의
y = event가 발생할때까지 걸리는 시간 (time till event occurs; non-negative) 
생존분석에서 y는 두가지 요소로 구성되어진다 -> T = time, e = event 발생 여부 (indicator의 역할을 한다) (0 = No, 1 = Yes)
y = surv(t, e)

censoring 
censoring은 probability에 영향을 주지 않는 것을 가정으로 한다. 
start와 end 지점 정의 
각 샘플마다 start 지점과 event끝날때 까지 걸리는 시간이 T.
만약 end 지점까지 event가 발생하지 않거나 중간에 follow-up loss가 있다면 T는 정해지지만 e = 0이 되는 right censoring
만약 start와 end 사이에 event는 발생하지만 시작 지점이 명확하지 않은 경우 left censoring -> left censoring은 분석에 사용하지 않는다.

Survival Function
S(t) = P(T>t) : t시간 이후에도 살아남을 확률을 나타내는 것이 survival function이다.

Hazard & Hazard ratio
Hazard: P(T<t+a|T>t): t 이후에도 살아남았을 때 t에 죽을 확률
Hazard Ratio(HR): Hazard X = 1 / Hazard X = 0 : X를 어떤 변수에 expose되거나 안되거나에 따른 Hazard 비율

Kaplan-Meier plot, Negative Exponential Survival function, Cox Proportional Hazard Model
이 세가지 모델은 각각 nonparametric, parametric, semiparametric model이다. (이 세가지 모델 모두 t = 0일 때 S(t) = 1이지만,갈수록 0으로 감소하는 형태의 그래프가 된다는 것을 생각하자.)
1. Kaplan-Meier plot
  plot에 X축을 t, Y축을 S(t)로 plotting 하면 K-M plot; 해석하기가 매우 용이한 장점이 있고, S(t)를 estimation할 수 있다는 장점은 있지만, function으로 수식으로 정의하기 어렵다는 것과, HR를 estimate할 수 없다는 단점이 있다. 일반적으로 K-M plot은 계단식으로 감소하는 모양의 그래프가 되는데 이때 S(t) 변하는 t 시점에선 Hazard가 발생하지만, 그 이외에 평평한 구간에선 Hazard가 존재하지 않는다. 또한 X(independent var)이 category일 때 X에 따른 각각의 K-M plot을 그리고 비교할 수 있지만, numerical var이었을 때는 할 수 없다는 단점이 있다.
2. Exponential 
  S(t) = exp(-Hazard(t))
  S(t)와 HR를 estimate할 수 있다. 하지만 exponential survival function은 위의 식에서 알 수 있듯 Hazard가 고정이 된다. (consistent Hazard) 그런데 이러한 Hazard의 고정은 사실 현실적인 가정이 아니다. 왜나하면 예를 들어 우리가 나이에 따른 Survival function은 당연히 감소할 수 밖에 없다. 그래서 이를 보정한 Weibull model이 있긴 하다. 이 모델은 시간에 따라 비율을 증가하거나 감소하는 가정을 함으로서 보정한다. 
3. Cox proportional Hazard model
  시간에 따라 유동적으로 Hazard 변동이 가능하다는 장점이 있다. 그리고 HR또한 estimate할 수 있다. 하지만 S(t)는 estimation할 수 없다는 단점이 있다. 
