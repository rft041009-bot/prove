# PROVE / 프루브

PROVE(프루브)는 `화장품의 진짜 가격을 증명하다`를 컨셉으로 한 링크 기반 가격 검증 서비스입니다.

사용자는 올리브영, 쿠팡, 네이버쇼핑, 공식몰 등에서 본 화장품 상품 링크를 입력하고, PROVE는 `실구매가`, `용량당 가격`, `쿠폰`, `배송비`, `기획세트`, `직전 세일가`를 같은 기준으로 비교합니다.

결과는 단순 최저가가 아니라 지금 가격이 `진짜 세일`인지, 더 안전하고 합리적인 `구매 추천처`가 어디인지 근거와 함께 보여줍니다.

## MVP Flow

1. Paste product link
2. Extract product info
3. Match same product across stores
4. Normalize price conditions
5. Compare current sale and previous sale
6. Calculate real discount
7. Recommend purchase option
8. Save item / track price

## Core Features

- `LINK_INPUT`: 상품 링크 하나로 검증 시작
- `PRODUCT_EXTRACT`: 상품명, 브랜드, 용량, 옵션, 구성품 자동 추출
- `PRICE_COMPARE`: 판매처별 표시가와 실구매가 비교
- `UNIT_PRICE`: 1ml 또는 1g 기준 용량당 가격 계산
- `COUPON_SHIPPING`: 쿠폰과 배송비를 반영한 실제 결제 금액 계산
- `SALE_HISTORY`: 현재 세일가와 직전 세일가 비교
- `REAL_DISCOUNT`: 표시 할인율이 아닌 실질 할인 정도 계산
- `BUY_RECOMMEND`: 최저가와 구매 추천처를 분리해 제시
- `PRICE_ALERT`: 관심 상품 저장 및 가격 변동 알림

## Verdict Types

- `REAL_SALE`: 평소 가격과 직전 세일 대비 의미 있게 저렴한 경우
- `NORMAL_PRICE`: 세일처럼 보이지만 실제로는 평소와 비슷한 경우
- `LOWEST_CAUTION`: 최저가는 낮지만 판매처나 상품 조건 확인이 필요한 경우
- `BUY_ELSEWHERE`: 다른 플랫폼의 구매 조건이 더 좋은 경우
- `SET_VALUE`: 기획세트나 증정품까지 보면 구매 가치가 있는 경우
- `LOW_REAL_BENEFIT`: 표시 할인율은 높지만 실질 이득은 낮은 경우
- `WAIT_OK`: 지금 급하게 사지 않아도 되는 경우

## Branch Flow

```txt
backend      \
frontend/a    -> main
frontend/b   /
```

