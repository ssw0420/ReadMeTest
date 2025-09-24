## 프로젝트 개요
### 프로젝트 명: NeoSteel Rift
##### VR 슈팅 로그라이크 게임

여기에 이미지 넣기

### 프로젝트 진행 타임라인
##### Notion : https://www.notion.so/NeoSteel-Rift-1ba37781ff7380e08b7cd05d1300bc0b

### 데모 플레이 및 기능 설명 영상
##### Youtube :

### 프로젝트 진행 기간
1. PC-VR 연결 버전 : 2025.03.09 ~ 2025.06.12
2. Standalone VR 버전 : 2025.08.27 ~ 2025.09.17

### 개발 인원
신승우
- 게임 디자인 및 시스템 설계
- 프로젝트 에셋 조사 및 관리
- 프로젝트 관리 및 PC-VR 연동 개발 환경 구축
- FMOD 설정 및 Audio System 구현
- 일반 몬스터 AI, 보스 몬스터 AI 구현
- 플레이어와 몬스터간 상호작용 구현
- 게임 플레이 진행 로직 구현
- 게임 데이터 관리 시스템 구현
- VFX, Particle System 최적화
- 씬 구성, 라이팅 설정 및 최적화
- 플레이어 UI 구현

한유민

## 목차
1. 프로젝트 기획 배경
2. 개발 환경
3. 사용 에셋
4. 프로젝트 구조
5. 기능 구현 및 최적화
6. 참고 자료
7. 프로젝트 리뷰


## 1. 프로젝트 기획 배경
여기에 이미지 넣기 (Center로 2장)
## 2. 개발 환경
##### Unity
- Unity 2022.3.60f1
- Unity XR Interaction Toolkit 3.0.3
- Oculus Integration SDK
  
##### FMOD
- FMOD 2.03.07

##### XR
- Meta Quest 3

## 3. 사용 에셋
**Unlimited Music Bundle: Vol. 1**,     **Universal Audio Bundle**,     **Stylized Shoot & Hit Vol.1**,     **Stylized Shoot & Hit Vol.2**,     **UNI VFX: Ulimate pack for Visual Effect Graph**,     **Hybrid Action Music Pack Vol.3**,     **Universal Sound FX**,     **Ultimate Clean GUI Pack**,      **Epic Toon FX**,     **Sci-Fi Battle Weapons**,     **All Sky Free - 10 Sky / SkyBox Set**,     **Droll Robots Pack1**,     **Factory Interior + Warehouse Props Vo1 - Bundle**,     **UNI VFX: Realistic Explosions, Fire & Smoke for Visual Effect Graph**


## 6. 참고 자료
Unity Documentation

글로벌ICT포털 | VR/AR/MR 시장동향 보고서 2024 | “https://www.globalict.kr/product/product_view.do?menuCode=040200&artclCode=DP0200&catNo=325&p_cateNo=&viewMode=view&knwldNo=144041”

GGIT | [기술] 돌아온 VR 게임, 대중화 시대 열리나 | “https://www.kocca.kr/global/2023_7+8/sub02_04.html”

Steam | Steam 하드웨어 및 소프트웨어 설문조사: February 2025 | “https://store.steampowered.com/hwsurvey/Steam-Hardware-Software-Survey-Welcome-to-Steam?l=koreana”

유니티 TIPS 핵심만 쏙쏙! Baked Lighting 이해하기 | "https://www.youtube.com/watch?v=J4iVXAYaJfQ&t=91s"

유니티 TIPS 새로워진 길찾기 AI Navigation 2.0 공략 | "https://www.youtube.com/watch?v=A0nsAjsJqHg&t=40s"

Knockback NavMeshAgents using Physics | "https://www.youtube.com/watch?v=0NH5obeOb7I"

2월 알쓸유잡 : 메모리 최적화를 위한 에셋 관리 | "https://www.youtube.com/watch?v=52ehLUfk3DQ&t=3328s"

Visual Design Methods for Virtual Reality, Mike Alger

VR 컨텐츠 제작 시 주의해야 하는 사항들 | "https://www.youtube.com/watch?v=rxC4FasB46M"

The Art of Game Design - Jesse Schell


## 7. 프로젝트 리뷰
- **의존성 최소화를 통한 시스템 통제**
  
게임 엔진에서 제공하는 NavMesh Agent, Rigidbody, Root Motion Animation 등 오브젝트의 물리적 동작에 직접적으로 영향을 주는 시스템은 가능한 한 하나의 시스템으로 통합하고 최소화해야 합니다. 이를 통해 서로 다른 시스템 간 충돌이나 예기치 못한 부작용을 줄이고, 개발 및 디버깅 효율을 높일 수 있습니다.

- **플레이어 스킬 추가**

현재 플레이 방향성이 슈팅에 치우쳐 있어, 초기 기획에 맞는 뱀서라이크 스타일로 변경하기 위해 기존 시스템을 활용한 스킬 추가 및 개선이 필요합니다.

- **보스 스킬 및 페이즈 추가**

보스 시스템은 구축되어 있으나 패턴이 단조롭고 페이즈 구분이 부족하여, 플레이어가 위협감을 느끼기 어려우므로, 페이즈별 스킬과 패턴 추가가 필요합니다.

- **이벤트 드리븐 구조의 에디터 시각화**

현재 이벤트 구조를 ScriptableObject 기반으로 변경하여 에디터 상에서 이벤트 호출 여부를 명시적으로 확인이 가능하도록 구현해야 합니다.

- **애니메이션 파라미터 해시화 적용**

Animator 파라미터를 문자열이 아닌 해시 값으로 변경하여 오타 및 이름 변경에 따른 오류를 방지하고 성능을 개선해야 합니다.

- **SO 데이터 구분 및 구글 시트 연동**

현재 테스트용과 플레이용 데이터가 구분되어 있지 않고, 외부에서 데이터를 관리하는 체계가 미비하므로 테스트용 / 플레이용 SO를 명확히 구분하고, 구글 시트 연동을 통해 외부에서 데이터 편집 후 SO로 자동 반영되도록 구현해야 합니다.

- **시각 효과 추가**
  
Fracturing & Destruction, Bullet Decal 등과 같은 게임 플레이 경험에 직접적으로 영향을 주는 이펙트 추가가 필요합니다.




회고: Standalone VR 버전으로 빌드까지 진행하며, 한정된 자원으로 게임을 개발하기 위한 최적화 방식에 대해 많이 알 수 있는 기회가 되었습니다. 이를 바탕으로 앞으로 컴퓨터 그래픽스, 메모리 관리, 프로그래밍 언어와 시스템 설계에 대해 더 깊이 학습할 필요가 있다고 느꼈습니다.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
한유민

플레이어 이동 및 회전
- XR Interaction Toolkit 3.0.3을 사용하여 플레이어 이동, 회전 설정
- Controller Input Action Manager을 통해 Input Action을 관리
- 왼손 컨트롤러 조이스틱을 통해 이동
- 오른손 컨트롤러 조이스틱을 통해 회전
- 회전 시 Snap Turn Provider을 사용하여 45도로 회전하여 VR 멀미 최소화
- VR 멀미는 주로 시각 정보와 신체의 평형 감각 사이의 불일치 때문에 발생하는데 부드러운 회전 과정에서 발생하는 지속적인 시각적 움직임 정보를 제거하여 시각 정보와 평형 감각의 불일치를 최소화 하기 위해 Snap Turn을 사용
- 평균적으로 많이 사용하는 각도인 45도로 설정
- 텔레포트 기능은 게임 플레이에 큰 영향을 끼치며 게임 진행 방향성과 맞지 않아 제외 시킴
- 로그라이크 장르 특성상 360도 방향을 주시해야 하므로, 오른손 컨트롤러 조이스틱을 아래 방향으로 내릴 시 180도 회전하여 바라보는 방향의 반대편을 바로 확인할 수 있도록 설정


씬 이동 시 Fade-In, Fade-Out을 하기 위한 FadeScreen 스크립트 사용
- 부드러운 페이드 효과를 위한 코루틴 사용
- Mathf.SmoothStep() 사용하여 선형 보간(Lerp)보다 더 부드러운 가속/감속 효과를 통해 자연스러운 Fade-In, Fade-Out 사용


플레이 씬에서 왼손 컨트롤러 트리거 버튼을 사용하여 UI 버튼 클릭 사용
- 플레이 씬에서 오른손 컨트롤러 트리거를 통해 UI 선택 시 총 그랩을 놓은 후 UI 선택하고 다시 총을 그랩해야 하는 번거로움이 있어 왼손 컨트롤러 트리거를 통해 UI 선택 가능


무기(총) 양손 파지 시스템
- 실제 Controller Hand와 Visual Hand를 구분하여 설계 및 구현
- 구분하지 않고 왼손 컨트롤러 그랩에 총 그랩 애니메이션 삽입 시 양손 파지 모션이 부자연스러움 존재
- 이를 해결하기 위해 양손 파지 시 실제 Controller Hand의 Mesh를 비활성화 한 후 총기에 미리 배치해 둔 Visual Hand를 활성화 하여 시각적으로 양손 파지를 성공적으로 됐다는 정보를 제공


무기(총) 반동 시스템
- Configurable Joint의 스프링 특성을 이용해 총이 움직인 후에 원래 위치로 복귀하는 특성을 사용하여 반동 효과를 연출
- 총기에 반동을 줄 경우 그랩중인 오른손, 왼손은 위치 이동을 안 하므로 총기 그랩 시 오른손 컨트롤러 자식으로 들어간 후 발사 시 오른손 컨트롤러 반동 효과를 적용하여 반동 효과를 적용
- 원리는 총 발사 시 오른손 컨트롤러에 Rigidbody의 직선 방향과 회전 방향을 이동 시킨 후 Configurable Joint의 특성을 사용하여 회전 복원력, 위치 복원력을 통해 반동 효과를 적용
- 한손으로 총을 그랩, 양손으로 총을 그랩을 할 때 반동 제어의 차이를 주기 위해 반동 최소값, 누적 최대 한계 값, 반동 증가량, 목표값으로 변화하는 속도 등의 수치를 나눠 반동 효과 차별화


무기(총) 강화 스킬 시스템
- 몬스터 50회 처치 시 자동으로 스킬 시스템 활성화
- 몬스터 50회 처치 시 SkillStatus를 변경하여 총기 발사 횟수를 카운트 후 충족 시 스킬 활성화
- 총기 발사 횟수에 따른 차징 시스템
- Pistol은 61회 발사 시 스킬 활성화
- Rifle은 151회 발사 시 스킬 활성화
- 각각의 총에 약 5탄창 사용 시 스킬 활성화
- 스킬 활성화 시 총알 무제한, 넉백 효과
- 일반 총알과 스킬 총알을 각각의 Perfab으로 분리하여 일반 발사, 스킬 발사의 시각적 정보 제공
- 총 발사 시 스킬 차징의 정도에 따라 총기 앞부분에 스킬 Muzzle의 알파값을 0과 1을 구분하여 시각적 정보 제공
- 스킬 활성화 시 총기 앞부분에 스킬 Muzzle이 회전하며 활성화 상태임을 알려줌


총기 UI
- '|'를 기준으로 왼쪽 숫자는 남은 총알 횟수, 오른쪽 숫자는 최대 총알 횟수를 제공하여 사용자에게 정보 제공
- 숫자 아랫 부분에 프로그래스바 효과를 사용하여 스킬 차징에 정도를 표시
- Gradient 효과를 사용해 차징 정도가 낮을 시 노란색에 가깝고, 차징 정도가 높을 경우 빨간색에 가깝게 구분하여 정보 제공


총기 변경
- 플레이어 6레벨 달성 시 추가 보상으로 총기 변경(Pistol -> Rifle)


보스 출현 시나리오
- 보스 출현 10초전 몬스터 스포너를 비활성화 하여 보스 출현 전 몬스터 수를 줄임
- 보스 출현 시 Fade-In, Fade-Out을 하여 보스 등장을 시각적으로 제공
- 보스 출현과 동시 맵에 Light 텍스쳐를 변경하여 보스 출현에 대한 추가적인 시각적 정보 제공




