# Inverse_problem in SIR model

## 1. SIR model
<img src="https://github.com/dontempty/Inverse_problem/assets/155451345/48fb09bc-691c-4171-abf7-4e6938985a8a.png" width="600" height="500"/>

### $\frac{dS}{dt} = -\frac{\beta IS}{N}$  
### $\frac{dI}{dt} = \frac{\beta IS}{N}-\gamma I$  
### $\frac{dR}{dt} = \gamma I$
### $\frac{dS}{dt}+\frac{dI}{dt}+\frac{dR}{dt} = 0$

## 2. Parameter estimation (without noise)
![4](https://github.com/dontempty/Inverse_problem/assets/155451345/fbb865cc-57e3-441d-bed6-62d39fdce041)
|    |beta|gamma|
|---|---|---|
|real|0.25|0.1|
|first-order forward differences|0.37429|0.22289|
|first-order backward differences|0.25153|0.09894|
|second-order centered differences|0.25043|0.09928|
|PINN|0.25119|0.09994|

## 3. Parameter estimation (with noise)
![5](https://github.com/dontempty/Inverse_problem/assets/155451345/191e6e90-1273-4265-b26e-1413c010cfc3)
|    |beta|gamma|
|---|---|---|
|real|0.25|0.1|
|first-order forward differences|0.45016|0.25932|
|first-order backward differences|0.27620|0.08942|
|second-order centered differences|0.27644|0.09408|
|PINN|0.27391|0.09346|

## 4. Conculsion
explicit euler 보다는 implicit euler 의 성능이 더 좋은것을 관찰할 수 있다.  
loss 함수가 convex임을 증명했고 parameter들의 explicit한 표현에서 분모는 항상 0이상임을 증명했다.

## 5. Reference
https://onlinelibrary.wiley.com/share/5XERPV9MFIVGNHBSBFYT?target=10.1002/mma.6985

## 잡답
oreder가 올라갈수록 조금씩 더 좋아지는 경향이 보인다.
나중에는 다른 모델에도 적용하면 좋을것 같다.
