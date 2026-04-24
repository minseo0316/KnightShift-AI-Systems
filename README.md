# ⚔️ Knight_Shift: Boss AI & Phase System Core

본 레포지토리는 3인 팀 프로젝트(졸업 작품) 'Knight_Shift'에서 제가 직접 설계하고 구현한 **AI 시스템 및 게임 코어 로직**을 별도로 정리한 저장소입니다.

---

### 🎮 보스 AI 및 페이즈 전환 데모
> (여기에 최신화한 영상 링크나 GIF를 꼭 넣어주세요!)
> 예: ![Demo](영상_또는_움직이는이미지_링크)

---

### 🎯 핵심 구현 사항 (My Contributions)

1. **Behavior Tree 기반 몬스터 AI**
   - 단순 FSM 방식을 넘어, **정찰-추적-대기-공격** 노드를 세분화한 Behavior Tree 구축
   - 조건부 우선순위 설계를 통해 유기적이고 예측 불가능한 AI 패턴 구현

2. **Boss Phase 전환 시스템**
   - 보스의 체력 상태에 따라 공격 패턴이 강화되는 **2페이즈(Phase) 전환 로직** 설계
   - 페이즈 전환 시의 VFX 및 사운드 연동 제어

3. **시스템 최적화**
   - 다수의 적 캐릭터 스폰 시 발생할 수 있는 부하를 줄이기 위한 로직 최적화

### 🔍 주요 소스 코드
* [BossAI_Controller.cs](./Scripts/BossAI_Controller.cs): 보스 전체 상태 및 페이즈 제어
* [BT_Node_Base.cs](./Scripts/BT_Node_Base.cs): 직접 구현한 Behavior Tree 베이스 노드
