# star2_ai_study
start2 AI를 사용하기 위해서 학습 및 수행한 내용을 저장하는 저장소입니다.

MLP를 직접 구현해 본 수준에서 출발해, AlphaStar(DeepMind, 2019)가 어떻게 동작하는지
**직접 손으로 구현하며 이해하는 것**을 목표로 합니다.

## 목표

- 최종 목표: PySC2 미니게임을 강화학습(PPO)으로 학습시키고, python-sc2로 컴퓨터(Hard)를 이기는 봇 만들기
- 이해 목표: AlphaStar 논문을 읽고 구조(입력 인코더 → LSTM → 단계별 행동 출력)와 학습 방식(모방학습 → 셀프플레이 강화학습)을 설명할 수 있기

## 로드맵

| 단계 | 주제 | 예상 기간 | 폴더 | 상태 |
|---|---|---|---|---|
| 0 | AlphaStar 개요 이해 | - | [docs/alphastar_overview.md](docs/alphastar_overview.md) | ✅ 완료 |
| 1 | PyTorch, CNN, LSTM, Transformer | 2~4주 | [01_pytorch_basics](01_pytorch_basics/) | ⬜ 예정 |
| 2 | 강화학습 기초 (REINFORCE, DQN, PPO) | 1~2개월 | [02_reinforcement_learning](02_reinforcement_learning/) | ⬜ 예정 |
| 3 | 셀프플레이 (틱택토, 오목) | 2~4주 | [03_self_play](03_self_play/) | ⬜ 예정 |
| 4 | 스타크래프트 II (python-sc2, PySC2, SMAC) | 2개월 이상 | [04_sc2](04_sc2/) | ⬜ 예정 |
| 5 | 논문 읽기 (AlphaStar 등) | 병행 | [05_papers](05_papers/) | ⬜ 예정 |

상세 항목과 체크리스트: [docs/learning_plan.md](docs/learning_plan.md)
작업 기록: [docs/worklog.md](docs/worklog.md)

## 저장소 구조

```
star2_ai_study/
├── README.md                    # 이 파일 (전체 개요, 진행 상태)
├── docs/
│   ├── alphastar_overview.md    # AlphaStar 동작 원리 정리
│   ├── learning_plan.md         # 단계별 학습 항목, 체크리스트, 참고 자료
│   └── worklog.md               # 날짜별 작업 기록
├── 01_pytorch_basics/           # 1단계 실습 코드
├── 02_reinforcement_learning/   # 2단계 실습 코드
├── 03_self_play/                # 3단계 실습 코드
├── 04_sc2/                      # 4단계 실습 코드
└── 05_papers/                   # 논문 요약
```

## 환경

- OS: Windows 11
- Python 3.11
