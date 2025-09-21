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


Standalone VR 버전으로 빌드까지 진행하며, 한정된 자원으로 게임을 개발하기 위한 최적화 방식에 대해 많이 알 수 있는 기회가 되었습니다. 이를 바탕으로 앞으로 컴퓨터 그래픽스, 메모리 관리, 프로그래밍 언어와 시스템 설계에 대해 더 깊이 학습할 필요가 있다고 느꼈습니다.

