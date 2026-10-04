# 학습 계획

각 항목을 끝내면 `[ ]`를 `[x]`로 바꾸고, [worklog.md](worklog.md)에 기록한다.

항목 앞 기호는 AI 활용 방법이다. 자세한 기준: [ai_usage_guide.md](ai_usage_guide.md)

| 🖐 직접 | 🤝 먼저 직접, 막히면 AI | 🤖 AI에게 맡김 |
|---|---|---|

---

## 1단계: 딥러닝 도구 익히기 (2~4주)

폴더: [01_pytorch_basics](../01_pytorch_basics/)

목표: numpy로 직접 짜던 신경망을 PyTorch로 옮기고, AlphaStar에 쓰인 신경망 구조(CNN, LSTM, Transformer)를 이해한다.

- [ ] 🤖 가상환경 생성, PyTorch(CUDA) 설치, GPU 인식 확인
- [ ] 🤝 Tensor, autograd 기본 사용법 (공식 튜토리얼 따라 하기)
- [ ] 🖐 예전에 numpy로 만든 MLP를 PyTorch로 다시 구현
- [ ] 🖐 CNN으로 MNIST 분류 (정확도 98% 이상)
  - 🤖 데이터 다운로드, DataLoader, 정확도 그래프 코드는 맡겨도 됨
- [ ] 🤝 CNN으로 CIFAR-10 분류
- [ ] 🖐 LSTM으로 간단한 시계열 예측 (예: sin 파형)
- [ ] 🖐 Attention / Transformer 개념 정리 (`notes.md`)
- [ ] 🤝 (선택) 작은 Transformer 직접 구현

참고 자료
- PyTorch 공식 튜토리얼: https://pytorch.org/tutorials/
- Andrej Karpathy, *Neural Networks: Zero to Hero* (YouTube)
- *The Illustrated Transformer* (Jay Alammar 블로그)

---

## 2단계: 강화학습 기초 (1~2개월) ★ 가장 중요

폴더: [02_reinforcement_learning](../02_reinforcement_learning/)

목표: 정답 라벨 없이 "보상"만으로 학습하는 방법을 직접 구현해서 이해한다.
**이 단계의 알고리즘 구현은 전부 🖐 직접 한다.** 이 저장소에서 가장 중요한 부분이다.

개념
- [ ] 🖐 강화학습 기본 용어 정리: 상태, 행동, 보상, 정책, 가치함수, 할인율 (`notes.md`)
- [ ] 🤝 MDP(마르코프 결정 과정) 이해
- [ ] 🤝 탐험(exploration)과 활용(exploitation)

구현 (Gymnasium `CartPole-v1` 기준, 평균 보상 475 이상 달성이 목표)
- [ ] 🤖 Gymnasium 설치 및 랜덤 에이전트 실행
- [ ] 🤖 학습 곡선 그래프, 학습된 에이전트 영상 저장 유틸리티
- [ ] 🖐 **REINFORCE** (정책 경사): AlphaStar 학습의 뿌리
- [ ] 🖐 REINFORCE + baseline
- [ ] 🖐 **DQN** (경험 재생, 타깃 네트워크)
- [ ] 🖐 **Actor-Critic (A2C)**
- [ ] 🖐 **PPO**: 실무에서 가장 많이 쓰는 알고리즘
- [ ] 🤝 PPO로 `LunarLander` 학습 (하이퍼파라미터 튜닝은 직접)
- [ ] 🤝 (선택) DQN으로 Atari 게임 하나 학습
  - 🤖 Atari 환경 설치와 화면 전처리 래퍼는 맡겨도 됨

참고 자료
- Hugging Face Deep RL Course (무료, 실습 위주, 1순위 추천): https://huggingface.co/learn/deep-rl-course
- OpenAI Spinning Up: https://spinningup.openai.com/
- David Silver 강화학습 강의 (YouTube)
- Sutton & Barto, *Reinforcement Learning: An Introduction* (무료 PDF)
- CleanRL (알고리즘별 단일 파일 구현): https://github.com/vwxyzjn/cleanrl
  - ⚠ 내 구현을 **끝낸 뒤** 비교용으로만 본다

---

## 3단계: 셀프플레이 (2~4주)

폴더: [03_self_play](../03_self_play/)

목표: AI가 자기 자신과 싸우며 강해지는 과정을 직접 확인한다. (AlphaGo, AlphaStar의 핵심 아이디어)

- [ ] 🤝 틱택토 게임 환경 직접 구현 (규칙 판정 부분은 막히면 AI 도움 가능)
- [ ] 🖐 틱택토 셀프플레이 학습 (랜덤 상대에게 패배 0 달성)
- [ ] 🖐 과거 버전의 자신들과 대결하는 "상대 풀(opponent pool)" 적용
- [ ] 🤝 (선택) 작은 판 오목 / Connect Four
- [ ] 🤖 (선택) PettingZoo 설치 및 예제 실행

---

## 4단계: 스타크래프트 II (2개월 이상)

폴더: [04_sc2](../04_sc2/)

이 단계는 설치와 API가 복잡하다. **설치와 API 조사는 🤖 맡기고, 전략과 학습은 🖐 직접** 한다.

사전 준비
- [ ] 🤖 StarCraft II 설치 (무료 Starter Edition 가능)
- [ ] 🤖 맵 파일 다운로드 및 배치 (Ladder 맵, 미니게임 맵)

4-1. python-sc2 (BurnySc2): 게임 API와 친해지기
- [ ] 🤖 설치 및 예제 봇 실행
- [ ] 🤝 일꾼 생산 + 미네랄 채취 봇 (API 사용법은 물어봐도 됨)
- [ ] 🖐 프로토스 기본 빌드 (파일런 → 게이트웨이 → 질럿) 후 공격
- [ ] 🖐 컴퓨터 Easy → Medium → Hard 순서로 승리 (전략은 직접 고민)

4-2. PySC2 (DeepMind 공식, AlphaStar도 사용): 미니게임 강화학습
- [ ] 🤖 설치 및 랜덤 에이전트 실행
- [ ] 🖐 관측(observation)과 행동(action) 구조 정리 (`notes.md`)
- [ ] 🖐 `MoveToBeacon` 규칙 기반 에이전트
- [ ] 🤝 관측을 신경망 입력으로 바꾸는 전처리 코드
- [ ] 🖐 `MoveToBeacon` PPO 학습 (2단계에서 만든 내 PPO 사용)
- [ ] 🖐 `CollectMineralShards` PPO 학습
- [ ] 🖐 `DefeatRoaches` PPO 학습

4-3. SMAC: 전투 컨트롤(마이크로) 멀티에이전트
- [ ] 🤖 설치 및 `3m` 시나리오 실행
- [ ] 🤝 독립 학습(IPPO) 또는 QMIX로 `3m` 승률 90% 이상

4-4. (도전) 모방학습
- [ ] 🤖 리플레이 파일 파싱
- [ ] 🖐 리플레이로 "다음 행동/빌드 예측" 지도학습 모델

---

## 5단계: 논문 읽기 (병행)

폴더: [05_papers](../05_papers/)

2단계를 마친 뒤 시작하는 것을 권장한다. 논문마다 요약을 `05_papers/`에 남긴다.

- **🖐 요약은 반드시 직접 쓴다.** AI 요약을 받으면 읽은 것이 아니다.
- 🤝 읽다가 이해 안 되는 수식이나 문단만 질문한다.

- [ ] Mnih et al., 2015, *Human-level control through deep reinforcement learning* (DQN)
- [ ] Schulman et al., 2017, *Proximal Policy Optimization Algorithms* (PPO)
- [ ] Vinyals et al., 2017, *StarCraft II: A New Challenge for Reinforcement Learning* (PySC2)
- [ ] Silver et al., 2017, *Mastering the game of Go without human knowledge* (AlphaGo Zero)
- [ ] Vinyals et al., 2019, *Grandmaster level in StarCraft II using multi-agent reinforcement learning* (AlphaStar)
- [ ] Samvelyan et al., 2019, *The StarCraft Multi-Agent Challenge* (SMAC)
