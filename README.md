⚔️ Knight_Shift: Boss AI & Game Systems Core
이 레포지토리는 3인 팀 프로젝트(졸업 작품) **'Knight_Shift'**에서 제가 전담하여 설계하고 구현한 보스 AI 시스템 및 게임 핵심 로직을 엄선하여 정리한 저장소입니다.

🎮 AI 시스템 및 보스 패턴 작동 데모 (Youtube)
주요 성과: 유동적인 페이즈 전환 시스템과 Behavior Tree 기반의 의사결정 로직을 통해 긴장감 있는 보스전을 구현했습니다.

🎯 핵심 구현 사항 (Key Contributions)
1. 하이브리드 AI 및 의사결정 시스템
단순한 상태 머신(FSM)을 넘어, 복잡한 패턴을 유기적으로 제어하기 위해 Behavior Tree를 도입했습니다.

의사결정 로직: 거리, 체력, 쿨다운 정보를 EnemyBlackboard로 관리하며 실시간으로 최적의 패턴을 선택합니다.

구현 파일: HoundBehaviorTree.cs, GolemBehaviorTree.cs, BTNode.cs

2. 정교한 보스 페이즈(Phase) 전환 및 패턴
보스의 체력 상태에 따라 완전히 다른 전투 경험을 제공하는 페이즈 시스템을 구축했습니다.

Hound AI: 2페이즈 진입 시 무적 상태와 함께 '영혼 화살비' 및 '장판 공격' 연출을 결합한 특수 패턴 구현.

Golem AI: 중량감을 살린 '콤보 공격'과 지형지물을 생성하는 '바위 송곳' 패턴 구현.

구현 파일: HoundAI.cs, GolemAI.cs

3. 게임 흐름 및 전투 관리 시스템
보스전의 시작부터 끝까지, 게임의 전체적인 흐름을 제어하는 매니저 클래스들을 설계했습니다.

전투 시스템: 인터페이스(IDamageable)를 활용한 데미지 전달 체계와 광역 판정 로직 구현.

스테이지 관리: 몬스터 스폰 시스템 및 보스전 트리거 로직 설계.

구현 파일: BossStageManager.cs, StageManager.cs, JumpAttackAreaDamage.cs

📂 프로젝트 구조 (Scripts)
Plaintext
├── AI_Brain
│   ├── HoundAI.cs / GolemAI.cs (보스 핵심 로직)
│   └── HoundBehaviorTree.cs / GolemBehaviorTree.cs (의사결정)
├── BT_Engine
│   ├── BTNode.cs (자체 구축 BT 엔진 코어)
│   └── EnemyBlackboard.cs (데이터 관리 블랙보드)
├── Combat_Systems
│   ├── IDamageable.cs (피격 인터페이스)
│   ├── AttackCollider.cs (공격 판정)
│   ├── ParticleProjectile.cs (투사체 로직)
│   └── RockSpike.cs (오브젝트 생성 공격)
└── Managers
    ├── StageManager.cs / BossStageManager.cs (게임 흐름 제어)
    └── HoundSoundManager.cs (이벤트 기반 사운드 관리)
💡 Technical Challenge & Solution
Challenge: 애니메이션 루트 모션(Root Motion)과 NavMeshAgent 이동 간의 충돌로 인한 미끄러짐 현상 발생.

Solution: SafeStopAgent 및 SafeResumeAgent 메서드를 설계하여, 특정 패턴 실행 시 에이전트를 안전하게 정지시키고 애니메이션 이벤트를 통해 정밀하게 복구함으로써 부드러운 동작을 구현했습니다.
