# ELS hege 5.19

KOSPI200 step-down ELS의 payoff, FDM delta, 정적/동적 hedge, grid search, margin/fee 재분석까지 단계별로 분리한 프로젝트입니다. `leaning materials`의 Monte Carlo, FDM, Black-Scholes, delta hedge 로직을 유지하고, `ELS_Optimal_Hedge`와 같은 섹션형 노트북 구조로 정리했습니다.

## 폴더 구조

| 경로 | 내용 |
|---|---|
| `data/` | KOSPI200 원자료 및 참고 데이터 |
| `ELS_Optimal_Hedge.ipynb` | Section 0~2: 세팅, 시장 데이터, Monte Carlo |
| `section_3_payoff.ipynb` | Section 3: ELS payoff 및 상환 유형 분석 |
| `section_4_fdm_delta.ipynb` | Section 4: FDM value grid와 delta grid |
| `section_5_static_hedge.ipynb` | Section 5: short vanilla put 정적 hedge |
| `section_6_dynamic_hedge.ipynb` | Section 6: FDM delta 기반 동적 hedge trading |
| `section_7_grid_search.ipynb` | Section 7: 원금북/정적/동적 hedge 조합 탐색 |
| `section_8_result_analysis.ipynb` | Section 8: 최종 결과 표와 그래프 |
| `section_9_margin_performance.ipynb` | Section 9: 발행마진, 수수료, 거래비용 민감도 |
| `section_10_disclosed_fair_value_margin.ipynb` | Section 10: 공시 공정가액, 발행마진, 0.5% 판매수수료, 30bp 동적헤지 비용 연결 |
| `section_10_bs_fair_value_margin.ipynb` | Appendix: BS benchmark fair value 민감도 확인 |

## 실행 순서

1. `ELS_Optimal_Hedge.ipynb`
2. `section_3_payoff.ipynb`
3. `section_4_fdm_delta.ipynb`
4. `section_5_static_hedge.ipynb`
5. `section_6_dynamic_hedge.ipynb`
6. `section_7_grid_search.ipynb`
7. `section_8_result_analysis.ipynb`
8. `section_9_margin_performance.ipynb`
9. `section_10_disclosed_fair_value_margin.ipynb`

각 노트북은 표와 그래프 출력이 포함된 상태로 저장되어 있으며, 다시 실행하면 결과는 이 폴더 안의 `output/`, `figures/`에 저장됩니다.

## 학습자료 로직 반영

| 학습자료 | 프로젝트 반영 위치 | 핵심 로직 |
|---|---|---|
| `1.Pricing, Interest Rate.ipynb` | Section 0, 7, 9 | 현재가치, 현금계좌 growth factor, 무위험 운용 |
| `2.Monte Carlo Simulation (1).ipynb` | Section 2, 3 | GBM 경로 생성, pathwise payoff 평가 |
| `3.Finite Difference Method.ipynb` | Section 4 | FDM value grid, KI/No-KI 상태 분리 |
| `4.Hedge Trading.ipynb` | Section 6 | delta lookup, weekly rebalancing, hedge PnL |
| `Volatility Surface.ipynb` | Section 1, 5 | historical volatility와 Black-Scholes option pricing |
