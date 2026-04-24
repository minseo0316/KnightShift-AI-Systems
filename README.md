⚔️ Knight_Shift: Boss AI & Game Systems Core
3인 팀 프로젝트(졸업 작품) 'Knight_Shift'의 핵심 로직 저장소

몬스터의 의사결정 시스템부터 타격 판정, 게임의 흐름을 제어하는 매니저 시스템까지 전담하여 설계 및 구현했습니다.

🎥 AI 시스템 및 보스 패턴 작동 데모
핵심 성과: 유동적인 페이즈 전환 시스템과 Behavior Tree 기반 의사결정 로직 구현.

시연 하이라이트: 01:20 (보스 페이즈 전환), 02:45 (광역 패턴 판정).

🎯 핵심 구현 사항 (Key Contributions)
1️⃣ 하이브리드 AI 및 의사결정 시스템
단순한 상태 머신(FSM)을 넘어, 복잡한 패턴을 유기적으로 제어하기 위해 Behavior Tree를 자체 구축하여 도입했습니다.

의사결정 로직: 거리, 체력 정보를 EnemyBlackboard로 관리하며 실시간 최적 패턴 선택.

관련 파일: HoundBehaviorTree.cs, GolemBehaviorTree.cs, BTNode.cs

2️⃣ 정교한 보스 페이즈(Phase) 전환 시스템
보스의 체력에 따라 전투 흐름이 바뀌는 페이즈 시스템을 구축하여 긴장감을 높였습니다.

Hound: 2페이즈 진입 시 무적 상태와 함께 '영혼 화살비' 등 연출 결합 패턴 구현.

Golem: 중량감을 살린 '콤보 공격'과 지형지물을 생성하는 '바위 송곳' 패턴 구현.

관련 파일: HoundAI.cs, GolemAI.cs

3️⃣ 전투 판정 및 게임 흐름 제어
전투의 기초가 되는 인터페이스와 스테이지 전체를 아우르는 매니저를 설계했습니다.

전투: IDamageable 인터페이스 기반의 데미지 전달 및 광역 판정 로직.

관리: 몬스터 스폰 및 보스전 트리거 로직 설계.

관련 파일: BossStageManager.cs, StageManager.cs

📂 프로젝트 구조 (Scripts)
Plaintext
Scripts
├── 01_AI_Brain ............. 보스 핵심 로직 및 Behavior Tree
├── 02_BT_Engine ............ 자체 구축 BT 엔진 코어 및 블랙보드
├── 03_Combat_Systems ....... 피격 인터페이스, 투사체, 판정 로직
└── 04_Managers_Utility ..... 게임 흐름 제어 및 사운드/환경 관리
💡 Technical Challenge & Solution
Issue: 애니메이션 루트 모션(Root Motion)과 NavMeshAgent의 충돌

패턴 실행 중 에이전트의 이동과 애니메이션 좌표 이동이 충돌하여 위치가 미끄러지는 현상이 발생했습니다.

Solution:
SafeStopAgent 및 SafeResumeAgent 메서드를 설계하여, 특정 패턴 실행 시 에이전트를 안전하게 정지시키고 애니메이션 이벤트를 통해 정밀하게 복구함으로써 부드러운 동작을 구현했습니다.
