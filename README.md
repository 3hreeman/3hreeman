# 장세명 Threeman
대한민국, 서울 | santapemagic@gmail.com | [LinkedIn](https://www.linkedin.com/in/3hreeman)

**Client**      : Unity  
**Server**      : Java, Apache Tomcat, MyBatis  
**Database**    : MySQL, Redis  
**Environment** : AWS(EC2, S3), Linux

---
## Company Works
<details>
<summary>더 보기</summary>

### [Hardcore Leveling Warrior](https://play.google.com/store/apps/details?id=com.superplanet.lucid3.global&hl=en) <sub>2024</sub>

개발팀 프로그래밍 파트 / 리드 프로그래머
1. 프로토타이핑 및 최적화
2. 전투 씬 구성, 전투 시스템
3. 스킬 및 특성 시스템

### [부메랑 RPG:던져라! 듀드](https://play.google.com/store/apps/details?id=com.superplanet.boomerang&hl=ko) <sub>2024</sub>
개발팀 프로그래밍 파트 / 리드 프로그래머
1. 프로젝트 리팩토링 및 최적화
2. 사내 프레임워크 적용
   
### [비공정기사단](https://play.google.com/store/apps/details?id=com.superplanet.airship) <sub>2022</sub>

개발팀 프로그래밍 파트 / 프로그래머
1. 프로토타이핑 및 최적화
2. 전투 로직 및 스킬 시스템
3. 캐릭터 커스터마이징, 이벤트 컷씬 시스템

### 마법스크롤 상인 지오 <sub>2021</sub>
개발팀 프로그래밍 파트 / 프로그래머
1. 전투 프로토타이핑 및 기본 시스템 설계
2. 빌드 최적화
   
### [전자오락수호대](https://play.google.com/store/apps/details?id=com.superplanet.videogameguardians&hl=ko) <sub>2020</sub>
개발팀 프로그래밍 파트 / 프로그래머
1. 프로젝트 리메이크 및 빌드 최적화
2. 사내 프레임워크 적용

</details>





## Personal Works

<details>
<summary>더 보기</summary>

### [Boids_with_ECS](https://github.com/3hreeman/Unity_Boids)

### 프로젝트 개요
Unity의 [Unity ECS(Entity Component System)](https://unity.com/kr/blog/engine-platform/on-dots-entity-component-system) 퍼포먼스 테스트를 위한 프로젝트.

<details>
<summary>ECS 개요</summary>

**ECS의 특징**
  
ECS는 Entity(엔티티), Component(컴포넌트), System(시스템)으로 구성된 아키텍처.  
기존의 객체 지향 프로그래밍(OOP) 방식보다 성능과 유지보수 측면에서 많은 이점을 제공함.  
  
① 성능 최적화 (Performance)  
캐시 효율성 향상: 데이터가 연속된 메모리 블록(SoA, Structure of Arrays)으로 저장되므로 CPU 캐시 효율이 극대화됨.  
병렬 처리(Parallel Processing) 최적화: 시스템이 독립적으로 실행될 수 있어 멀티스레딩 환경에서도 쉽게 확장 가능.  

② 유연성 (Modularity & Reusability)  
데이터 기반 아키텍처: 엔티티는 컴포넌트의 집합으로 이루어져 있어 객체 간의 상속 관계가 필요 없음.  
확장성과 유지보수 용이: 특정 기능을 수정하거나 추가할 때 기존 코드에 영향을 주지 않고 독립적으로 구현 가능.  

③ 디커플링 (Decoupling)  
엔티티는 데이터를 포함하지 않으며, 시스템이 해당 데이터를 처리하는 방식으로 동작하여 코드가 모듈화되고 재사용성이 높아짐.  
특정 기능을 다른 프로젝트에서도 쉽게 재사용 가능.  

  
**ECS의 방향성**
   
 ① 차세대 성능 최적화 아키텍처  
 DOTS(Data-Oriented Technology Stack)의 핵심 구성 요소로 활용되며, Unity의 향후 엔진 최적화 방향에서도 중요한 역할을 담당.  
 기존의 객체 지향 방식보다 하드웨어 성능을 극대화할 수 있도록 설계됨.  

 ② 대규모 시뮬레이션 및 게임 개발에 적합  
 수천 개에서 수백만 개의 오브젝트(엔티티)를 효율적으로 관리 가능.  
 AI, 물리 시뮬레이션, 대규모 오픈월드 게임 등에서 ECS의 성능 이점을 극대화할 수 있음.  

 ③ 점진적 도입 가능  
 기존 Unity의 GameObject 및 MonoBehaviour 시스템과 함께 사용할 수 있도록 설계되어 있으며, 점진적인 전환이 가능.  
 기존 프로젝트에서도 ECS의 성능 이점을 부분적으로 활용 가능.  
</details>

### 레퍼런스 및 테스트 후 비교

[[YUNNONG-Boids](https://github.com/BongYunnong/CodingExpress)] 의 Boids 프로젝트를 바탕으로 하여 ECS로 컨버팅.

![Image](https://github.com/user-attachments/assets/d576d961-cf5d-4444-a894-4fd7750096dc)

1-1) 기존 레퍼런스 프로젝트에서 구현된 Boids 시스템  
각각의 Boid가 개별의 MonoBehaviour형태로 구현되어, 각각의 Update문에서 움직임을 연산.  
오브젝트의 개수가 늘어날 수록 프레임 드랍이 눈에 띄게 발생.  
1000개 이상부터는 원활한 실행이 어려움.  

![Image](https://github.com/user-attachments/assets/359a0262-64e8-40e2-80d3-d9c32f83d9de)

2-1) ECS로 컨버팅하여 재구성한 Boids 시스템  
기존 레퍼런스 프로젝트의 Boid 움직임을 ECS 구조로 컨버팅.  
각 모듈당 10000개씩, 총 2만개의 오브젝트가 평균 CPU 10ms 이하로 쾌적하게 작동하는 것을 확인.  

### 결론 및 감상
컨버팅 중에 Boids 이동 보정 로직이 일부 수정되어 원본과 완벽히 동일한 형태의 Boids 시스템을 구현하지 못한 것은 아쉬움.  
그럼에도 압도적인 퍼포먼스의 차이를 확인하여 ECS의 데이터 지향적 설계가 추구하는 효율적인 대규모 시스템 구현이라는 방향성을 확인할 수 있었음.  
ECS의 데이터 지향적 구조가 생소하게 느껴졌고, 기존에 익숙한 MonoBahaviour 기반의 시스템과는 구조적으로 많이 다름을 알 수 있었음.  

압도적인 퍼포먼스라는 분명한 장점이 존재하지만, 이미 익숙하여 빠른 테스트와 Iteration이 가능한 기존 Component 시스템의 장점들에 비해 사용하기에 조금 더 까다롭다고 느낌. 하지만 신생 시스템인 만큼 앞으로도 더욱 발전할 수 있기에 추후가 더 기대됨.

---

### [PF_Zone](https://github.com/3hreeman/pf_zone)

### 프로젝트 개요
이 프로젝트는 단순하지만 검증된 게임성을 가진 레퍼런스를 참고하여, 여러가지 떠오르는 로직이나 새로운 기능들을 빠르게 검증하고 테스트해보기 위한 프로젝트입니다.  
**뱀파이어 서바이버** 방식으로 등장하는 적들을  
**록맨**처럼 일반 공격과 차징 공격으로 처치하는  
**2D 탑다운 뷰 형태의 슈팅 게임**이며,  
모든 공격에는 소소한 물리효과가 적용되어, 썩 나쁘지않은 타격감을 느낄 수 있습니다.  

기본적인 플레이 모습은 아래와 같습니다.

![Image](https://github.com/user-attachments/assets/7c47f84a-c874-455d-a4f5-783fb3e59dad)  
1. 기본 시작시 모습

![Image](https://github.com/user-attachments/assets/1f83c08a-3a09-473e-be29-f7bb4b901f95)  
2. 게임이 일정 이상 진행되면 다음처럼 다수의 적이 쫓아옵니다.

현재 테스트중인 기능은 Unity의 [JOB시스템](https://unity.com/kr/blog/engine-platform/improving-job-system-performance-2022-2-part-1)입니다.

다수의 적이 등장하여 동시에 움직일 때, 두 시스템에 대한 퍼포먼스를 중점적으로 비교했습니다.

- MonoBehaviour의 Update
- Unity JOB시스템

가장 큰 차이점은 실행되는 **Thread**가 다르다는 점입니다. 
- MonoBehaviour의 Update는 **Main Thread**에서,
- JobSystem은 **JobThread**에서 별도로 실행된다는 점이 큰 차이입니다.  

두 Thread의 차이점은 아래에 간략하게 정리해두었습니다.
<details>
<summary>Unity의 MainThread와 JobThread</summary>

**1. Main Thread (메인 스레드)**  

① 역할  
Unity의 기본 실행 흐름을 담당하는 스레드.  
Update(), FixedUpdate(), LateUpdate() 등 일반적인 MonoBehaviour 기반 게임 로직이 실행됨.  
Unity API(예: Transform, GameObject, Instantiate() 등)와 직접적으로 연관됨.  
UI 처리, 입력 감지, 렌더링 호출 등 필수적인 작업을 수행.  

② 주요 특징  
싱글 스레드로 동작 → 대부분의 Unity API는 메인 스레드에서만 실행 가능.  
성능 병목이 발생할 가능성이 높음 (예: 많은 연산을 포함한 물리 연산, AI 계산, 대규모 데이터 처리).  
멀티스레딩 지원 부족으로 인해 복잡한 연산을 처리하는 데 한계가 있음.  

**2. Job Thread (잡 스레드)**  

① 역할  
Unity의 C# Job System을 통해 생성되는 워크로드 처리용 스레드.  
메인 스레드가 직접 처리하기 어려운 병렬 연산을 백그라운드에서 수행.  

대표적인 예시:  
물리 연산 (예: Havok Physics, Unity Physics)  
AI 연산 (예: 경로 탐색, 상태 업데이트)  
대규모 데이터 연산 (예: 군집 AI, 파티클 시스템, 애니메이션 처리)  

② 주요 특징  
멀티스레딩 가능 → 여러 개의 CPU 코어를 활용하여 성능을 극대화.  
Unity의 C# Job System과 Burst Compiler를 함께 활용하면 최적화된 네이티브 코드로 변환됨.  
메인 스레드와 독립적이지만, Unity API에는 접근할 수 없음 (렌더링 관련 API 사용 불가).  
Job System을 활용하면 Unity가 자동으로 스레드 풀을 관리하여 최적의 스레드 개수를 결정.  

</details>

각 케이스에 대해서 오브젝트 개수를 점차로 늘려가며 테스트하며, 오브젝트 1000개가 동시에 움직이는 상황을 기준으로 다음과 같은 결과를 얻었습니다.
테스트 환경에서 구성한 뷰의 모습은 아래와 같습니다.

![Image](https://github.com/user-attachments/assets/63cf45e4-acb6-4140-9e4b-88ac119d9527)


#### 1. MonoBehaviour의 Update형태로 작동할 경우

![Image](https://github.com/user-attachments/assets/62b569b4-0569-43cf-8c37-323dcdf9ea75)

1-1) Profiler의 Main Thread 내 Update문의 CPU사용량

![Image](https://github.com/user-attachments/assets/ba68ab31-48f6-4816-bbac-e548c8eb090b)
1-2) Main Thread만 열일하고 Job Thread는 놀고 있다.

#### 2. Job System으로 작동할 경우

![Image](https://github.com/user-attachments/assets/02e52149-76d8-4ab4-bb40-f8999a59d873)

2-1) 1-1에 비해 Main Thread의 사용량이 현저히 줄어든 것이 보인다.

![Image](https://github.com/user-attachments/assets/f779846e-a472-44d9-8730-5b03aa7f00b2)
2-2) Main Thread에서 사용하던 연산량이 JOB Thread에서 병렬로 처리되고 있음을 확인할 수 있다.


### 결론 및 감상
Unity는 명시적으로 멀티스레드를 지원하지 않아서 아쉬운 부분이 많습니다.  
**C#의 Thread나 Task**을 통해 멀티스레드를 활용할 수 있지만, MonoBehaviour 기반의 Update는 Main Thread에서만 실행된다는 점과 더불어 Task나 Thread는 엔진과 독립적으로 작동하면서 GameObject나 Transform과 같은 Unity API를 사용할 수 없기에 활용도가 제한적입니다.  
그런 측면에서 **Unity의 Job System**은 좋은 대안이 될 수 있습니다.  
1. 엔진 내부에서 자동으로 관리하는 Thread pool을 활용하기에 관리가 쉽고 효율적으로 활용 가능  
2. 연속적인 메모리 구조로 데이터를 관리하기에 CPU 캐시 효율성이 높음  

물론 Job System에도 아쉬운 점은 있습니다.  
Thread나 Task와 마찬가지로 Unity API를 직접 호출할 수 없기에 NativeArray등의 구조체를 거쳐야한다는 점, 기존의 MonoBehaviour 구조와 달라서 적응하기 위한 러닝 커브가 존재한다는 점은 분명히 아쉬운 부분이기도 합니다.  
그럼에도 분명한 장점을 가지고 있고, Unity가 새롭게 지원하는 [ECS(Entity Component System)](https://unity.com/ecs)와 같은 [DOTS(Data Oriented Technology Stack)](https://unity.com/dots) 기반 시스템과 밀접하게 연관되어 있기 때문에, 향후에 더욱 요긴하게 사용될 가능성이 높은 기술 스택이므로, Unity개발자라면 필히 익혀둬야 할 기술이라고 생각됩니다.
