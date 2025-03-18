## E-Commerce 데이터 분석 프로젝트
스파르타 코딩클럽에서 실시한 재직자 부트캠프 과정에서 진행한 프로젝트입니다.
- - -
## 프로젝트 개요
고객 만족도 점수(Customer satisfaction score, CSAT)란?

기업이 제공하는 제품이나 서비스에 대한 고객 만족도를 평가하는 중요한 지표입니다.

만족도 조사 응답을 통해 성장의 기회와 회사가 뒤쳐지고 있는 분야를 파악할 수 있습니다.

매니저는 이러한 피드백에 따라 조치를 취하고 취약점을 해결함으로써 더 나은 고객 경험을 제공하여 고객 확보 및 유지율을 높일 수 있습니다.

고객 만족도 데이터를 분석하여, 고객의 요구를 충족하지 못하는 부분을 파악하고, 이를 개선하기 위한 전략적 인사이트를 도출해보겠습니다.
- - -
## 문제 정의
- **날짜별, 카테고리별 평균 CSAT**
 
![날짜별 고객 만족도 점수 평균](https://github.com/ganghyo/E-Commerce/blob/master/CSAT_date_avg.png)
Others 카테고리의 CSAT
 
![카테고리별 고객 만족도 점수 평균](https://github.com/ganghyo/E-Commerce/blob/master/CSAT_category_avg.png)

날짜별로 고객 만족도 점수(CSAT)를 봤을 때, Others 항목에서 최소값이 가장 많이 나타나는 것이 확인되었습니다.

Others 항목의 세부 항목을 살펴 보면, Call disconnected가 평균 3.23점, Call back request가 평균 3.52점 으로 낮은 수치를 기록했습니다.

이 수치들을 보면, 고객들이 전화 연결 부분에서 불편함을 느끼고 있다고 판단됩니다.

- **고객응대 유형**

당 사의 고객응대 유형은 크게 세 가지로 분류 되는데,

![고객응대 유형](https://github.com/ganghyo/E-Commerce/blob/master/Channel_cnt.png)

Inbound: 79.3% / Outcall: 17.2% / Email: 3.5% 로 전화응대(Inbound) 유형이 가장 많은 부분을 차지합니다.

그런데, Call disconnected 와 Call back request 부분에서 만족도 평균 점수가 가장 낮다는 것은 큰 문제가 있다고 판단됩니다.

## EDA(탐색적 데이터 분석)
1. **팀 별 고객 응대 횟수 및 Call back 까지 걸린 시간**

![팀별 고객 응대 횟수](https://github.com/ganghyo/E-Commerce/blob/master/call_manager_cnt.png)
![팀별 Call back까지 걸린 평균 시간](https://github.com/ganghyo/E-Commerce/blob/master/call_manager_time_avg.png)

특히, Olivia Tan 매니저의 팀이 응대 횟수는 적으나 Call back 까지 오래 걸리는 것이 확인됩니다.

![팀별 고객 만족도 점수 평균](https://github.com/ganghyo/E-Commerce/blob/master/CSAT_manager.png)

그에 따라 고객 만족도 점수도 2.50점으로 현저히 낮은 것을 확인할 수 있습니다.

2. **근무 시간대 별 상담원 수와 Call back 까지 걸린 시간**

![근무 시간대별 상담원 수 및 Call back까지 걸린 평균 시간](https://github.com/ganghyo/E-Commerce/blob/master/inbound_time_avg_slot.png)

근무 시간대 별로 확인했을 때, Afternoon(12~14시) 과 Night(20~06) 시간대에 Call back까지 걸린 시간이 길다는 것을 확인할 수 있습니다.

해당 시간대에는 상담원 수가 다른 시간대에 비해 매우 적습니다.
반면에, Morning(06~12) 에는 상담원 수가 가장 많고, Call back까지 걸린 시간이 매우 짧습니다.

상담원 수에 따라 Call back 시간이 짧다는 것을 확인할 수 있습니다.

3. **상담원 별 응대 횟수**

![상담원 별 응대 횟수1](https://github.com/ganghyo/E-Commerce/blob/master/inbound_cnt_employee_morning.png)
![상담원 별 응대 횟수2](https://github.com/ganghyo/E-Commerce/blob/master/inbound_cnt_employee_afternoon.png)

상담원 별로 응답 횟수 차이가 많이 나는 것을 알 수 있습니다.

4. **근무 시간대 별 상담원 평균 응답 횟수**

![근무 시간대 별 응대 횟수](https://github.com/ganghyo/E-Commerce/blob/master/inbound_cnt_slot.png)
근무 시간대에 따라 평균 응대 횟수가 다르다는 것을 알 수 있습니다.
Night 시간대의 근무자들이 다른 시간대 근무자들보다 평균 10회가 더 많습니다.

## 해결 방안
