# Unreal C++
## 이득우의 언리얼 c++ 게임 개발의 정석
### 액터의 설계
- 월드: 현실 세계를 모방한 컴퓨터 안의 가상 세계. 뷰포트 윈도우에 보이는 작업 공간이다.
  1. 공간: 가상 세계를 구성하는 3차원의 영역. 트랜스폼이라는 구조체를 제공하며, 기본 단위는 cm.
  2. 시간: 가상 공간에서 흐르는 시간. 시간은 초 단위로 현실 세계와 동일하게 흘러가지만, 사용자가 시간의 스케일을 조절 가능.
  3. 물리: 월드 공간에 배치된 물체에 작용하는 물리적인 환경. 공간에 배치된 물체가 월드로부터 물리적인 영향을 받으려면 콜리전 정보 필요.
  4. 렌더링: 엔진이 제공하는 시각적 기능. 빛과 이에 반응하는 머티리얼로 구성되며, 언리얼 엔진은 현실 세계와 유사하게 작동하도록 물리 기반 렌더링 시스템을 제공.

- 엑터: 콘텐츠를 구성하는 최소 단위의 물체. 특정 공간에서 자신에게 주어진 역할을 수행하는 물체를 의미.
  1. 이름: 작업을 위한 명칭이며, 여러 액터가 같은 이름을 가질 수 있음.
  2. 유형: 게임플레이에서 수행할 액터의 역할이며, 액터의 클레스 이름.
  3. 트랜스폼: 액터는 반드시 월드에 존재해야 하므로 항상 트렌스폼이 부여됨.
  4. 프로퍼티: 액터에 설정된 속성 값이며, 액터의 유형에 따라 서로 다른 속성을 제공.
  5. 게임 로직: 액터에 특정 상황이 발생할 때 이에 대응할 구체적인 행동 명령을 위한 프로그래밍 코드.

- 레벨: 플레이어에게 주어지는 스테이지. 월드에 배치된 액터들의 집합.

- 컴포넌트: 시각적, 물리적, 움직임을 규격화한 기능.
  1. 스태틱메시 컴포넌트: 애니메이션이 없는 모델링 에셋인 스태틱메시를 사용해 시각적인 기능과 물리적인 기능을 제공하는 모듈. 주로 배경 물체에 사용.
  2. 스켈레탈메시 컴포넌트: 애니메이션 정보가 있는 모델링 애셋인 스켈레탈 메시를 사용해 시각적인 기능, 애니메이션, 캐릭터의 물리 기능 제공. 캐릭터에 사용.
  3. 콜리전 컴포넌트: 구/박스/캡슐로 지정한 영역에 물리적인 기능을 설정하기 위한 모듈. 시각적인 기능은 없음.
  4. 카메라 컴포넌트: 가상 세계에서 보여지는 현재 상황을 플레이어의 모니터 화면에 출력해주는 기능.
  5. 오디오 컴포넌트: 가상 세계에서 소리를 발생시키는 데 사용하는 기능.
  6. 파티클 시스템 컴포넌트: 파티클 시스템으로 설계된 이펙트를 화면에 보여주기 위한 기능.
  7. 라이트 컴포넌트: 물체에 광원 표과를 부여하는 기능.
  8. 무브먼트 컴포넌트: 물체에 특정 움직임을 부여하는 기능.
- 루트 컴포넌트: 액터를 대표하는 하나의 컴포넌트.
