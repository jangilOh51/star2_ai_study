# 작업 기록

최신 기록이 위로 오도록 작성한다.

---

## 2026-10-05

### 한 일
- AlphaStar가 어떻게 동작하는지 정리 → [alphastar_overview.md](alphastar_overview.md)
  - 구조: 입력 인코더(Transformer, CNN, MLP) → LSTM → 단계별 행동 출력
  - 학습: 사람 리플레이 모방학습 → 셀프플레이 강화학습(리그)
- 전체 학습 로드맵(1~5단계)과 단계별 체크리스트 작성 → [learning_plan.md](learning_plan.md)
- 저장소 폴더 구조 생성 (`01_pytorch_basics` ~ `05_papers`)
- AI 활용 기준 정리 → [ai_usage_guide.md](ai_usage_guide.md)
  - 학습 계획의 모든 항목에 🖐 직접 / 🤝 먼저 직접, 막히면 AI / 🤖 AI에게 맡김 표시

### 배운 점
- "다양한 기능"은 기능별로 코딩한 것이 아니라, 출력을 `무슨 행동 → 어떤 유닛 → 어디에` 단계로 나눈 하나의 신경망이다.
- 각 단계는 MLP의 softmax 분류와 같은 원리다.
- 핵심 차이는 학습 방식: 정답 라벨 대신 승패 보상으로 학습한다(강화학습).

### 다음 할 일
- [ ] PyTorch 설치
- [ ] 예전 numpy MLP를 PyTorch로 다시 구현
- [ ] Gymnasium `CartPole`을 REINFORCE로 학습해 보기
