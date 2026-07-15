# 유세혁 포트폴리오

**연구·소프트웨어 엔지니어**  
`컴퓨터 비전` · `센서 융합` · `실시간 인터랙션` · `응용 AI`

비전과 웨어러블 센서 데이터를 활용해 제스처 인식 방법과 시스템 요구사항을 설계하고,  
센서 입력부터 Unity 동작까지 이어지는 실시간 인터랙션 파이프라인을 설계하고, 핵심 로직을 구현·수정하며 시스템을 통합·검증해왔습니다.
<!--
**Email:** `imasp@naver.com`
-->
---

## 소개

컴퓨터소프트웨어공학을 전공하고, 중앙대학교 첨단영상대학원에서 XR/HCI와 실시간 제스처 인식 시스템을 연구했습니다.

주요 관심 분야는 **비전 기반 손 추적**, **IMU·웨어러블 센서 융합**, **강건한 제스처 인식**, **실시간 아바타 인터랙션**입니다. MediaPipe 3D landmark와 IMU quaternion·acceleration 데이터를 처리하고, 규칙 기반 방법과 딥러닝 모델을 비교하며, Python 백엔드와 Unity 클라이언트를 하나의 실시간 시스템으로 통합하고 검증해왔습니다.

---

## 핵심 역량

- **실시간 인터랙션 시스템 개발**  
  센서 입력 수집, 전처리, 인식·분류, 네트워크 통신, Unity 반영까지 이어지는 시스템 구조 설계, 핵심 로직 구현·수정 및 통합

- **강건한 제스처 인식 방법 설계**  
  3D landmark의 각도·거리·관계 특징 정의, 3단계 상태 분류, One Euro Filter·EMA·temporal validation 적용

- **모델 비교 및 실험 검증**  
  규칙 기반 방법과 YOLOv10n, DeiT, MLP, SGCN의 정확도·처리 속도·자원 사용량 비교

- **멀티모달 입력 통합**  
  Webcam, Apple Watch, Movella DOT IMU 등 서로 다른 입력을 하나의 아바타 제어 파이프라인으로 연결

- **연구 프로토타입 개발**  
  사용자 평가용 시스템과 CSV logging, resource profiling, 반복 실험 및 오류 검증 환경 구현·구성

---

## 연구 프로젝트

### 1. 가상현실 환경의 손·손가락 제스처 인식을 위한 구조화된 3단계 분류 모델

**정보과학회논문지 · 2026 · 제1저자**

카메라 기반 손 추적에서 발생하는 경계 구간의 흔들림을 줄이기 위해 손가락 상태를 `펴짐 / 중간 / 굽힘`의 3단계로 구조화한 실시간 제스처 인식 시스템입니다.

**담당:** 제스처 상태·관계 정의, 임계값과 안정화 방법 설계, 핵심 인식 로직 구현·수정, Python–Unity 시스템 통합 및 실험 검증

**주요 수행 내용**

- 손가락 상태와 손가락 간 관계를 이용한 규칙 기반 인식 방법 설계
- MediaPipe Hands landmark 처리와 EMA 기반 안정화 로직 구현·수정
- Python 인식 백엔드와 WebSocket 기반 Unity 인터랙션 기능 구현·연결
- 무기 조작, 객체 선택, 조명 제어 등 가상환경 동작 매핑 로직 구현
- 사용자 평가를 위한 실행 환경과 실험 절차 구성

**기술 스택**

`Python` · `OpenCV` · `MediaPipe Hands` · `WebSocket` · `Unity` · `C#`

[저장소 보기](https://github.com/YooSH-DY/JOK26-3) · [게재 정보](https://jok.kiise.or.kr/digital-library/manuscript/file/106055/07.pdf)

---

### 2. Multi-view Hand Gesture Recognition Pipeline

**논문 심사 중 · 저장소 공개**

Top/Bottom 카메라 기반 데이터 수집부터 규칙 기반 방법과 딥러닝 모델 비교, 실시간 측정, Unity 연동까지 하나의 환경에서 검증할 수 있도록 구성한 연구 파이프라인입니다.

**담당:** 데이터 수집·평가 구조 설계, 규칙 기반 로직과 비교 모델 구현·수정, 실시간 측정·로깅 환경 통합 및 검증

**주요 수행 내용**

- 사용자·세션 단위 듀얼 카메라 제스처 데이터 수집 구조 설계
- MediaPipe 3D landmark 기반 state/relation vector 규칙 정의 및 인식 로직 구현
- YOLOv10n, DeiT, SGCN 비교 모델 구현·수정 및 실험 환경 구성
- FPS, CPU, RAM, GPU, prediction, confidence 측정·로깅 기능 구현
- 정적·동적 제스처 안정화 로직과 UDP 기반 Unity command bridge 구현·통합

**기술 스택**

`Python` · `PyTorch` · `YOLOv10n` · `DeiT` · `SGCN` · `MediaPipe` · `UDP` · `Unity`

[저장소 보기](https://github.com/YooSH-DY/multi-view-hand-gesture-recognition)

> 논문 심사와 연구 데이터 보호를 위해 원본 참가자 영상, 전체 실험 로그, 모델 가중치와 심사 자료는 공개 저장소에서 제외했습니다.

---

### 3. Minimal Input to Maximal Movement: Real-Time Avatar Control with Dual-sensor

**ACM VRST 2025 · 제1저자**

웹캠과 손등 IMU를 결합해 최소한의 입력으로 아바타 댄스 동작과 연속 모션 파라미터를 실시간 제어한 시스템입니다.

**담당:** 연구 방법론과 센서 매핑 구조 설계, 핵심 처리·제어 로직 구현·수정, Python–Unity 실시간 시스템 통합 및 사용자 평가 환경 구성

**주요 수행 내용**

- Webcam 기반 손가락 상태와 Movella DOT IMU 입력을 결합하는 dual-sensor 구조 설계
- 손가락 상태를 dance variation으로 변환하는 제스처 매핑 로직 구현·수정
- IMU quaternion·acceleration을 이용한 속도, 방향, 다리 높이 등 연속 제어 파라미터 구성
- WebSocket 기반 Python–Unity 실시간 데이터 전송 및 아바타 제어 기능 통합
- 사용자 평가를 위한 실행 프로토타입과 실험 로그 환경 구성

**기술 스택**

`Python` · `MediaPipe Hands` · `Movella DOT IMU` · `Quaternion` · `WebSocket` · `Unity` · `C#`

[저장소 보기](https://github.com/YooSH-DY/Minimal-Input-to-Maximal-Movement) · [게재 정보](https://doi.org/10.1145/3756884.3768392) 

---

### 4. Wrist-Based Spatial Gestures for Multi-Parameter Avatar Dance Control

**ACM SUI 2025 · 제2저자**

손등의 단일 IMU 센서로 손목의 공간 움직임을 분석하고, 하나의 입력으로 여러 아바타 동작 파라미터를 동시에 제어한 인터랙션입니다.

**담당:** IMU 기반 방법론과 파라미터 매핑 구조 설계, 핵심 제어 로직 구현·수정, Unity 인터랙션 시스템 통합 및 동작 검증

**주요 수행 내용**

- 손등 IMU의 quaternion 데이터를 이용한 손목 roll·pitch 기반 공간 제스처 정의
- 손목 움직임을 이동 방향, 상체 회전, 골반 기울기, 애니메이션 속도로 변환하는 매핑 구조 설계
- 센서 입력의 범위 보정과 아바타 파라미터 정규화 로직 구현·수정
- 실시간 센서 데이터 수신과 Unity Animator 제어 기능 통합
- 동작 조건별 출력 확인과 사용자 평가용 프로토타입 검증

**기술 스택**

`Movella DOT IMU` · `Quaternion` · `Python` · `WebSocket` · `Unity` · `Animator` · `C#`

[저장소 보기](https://github.com/YooSH-DY/Wrist-Based-Spatial-Gestures-for-Multi-Parameter-Avatar-Dance-Control) · [게재 정보](https://doi.org/10.1145/3694907.3765952)

---

### 5. Hand/Finger Gesture Standardization for FCI (Finger-Computer-Interface) in XR

**IEEE ISMAR-Adjunct 2025 · 제2저자**

손 형태와 손가락 간 거리를 아바타의 동작 모드 및 연속 모션 파라미터로 변환하는 실시간 인터랙션 시스템입니다.

**담당:** 제스처 인식·캘리브레이션 방법론 설계, 핵심 입력 처리·안정화 로직 구현·수정, Python–Unity 연동 및 실험 환경 구성

**주요 수행 내용**

- MediaPipe 기반 hand gesture mode와 finger-distance parameter 정의
- 사용자별 손가락 거리 캘리브레이션 및 정규화 기능 구현
- EMA와 연속 프레임 확인을 이용한 입력 안정화 로직 구현·수정
- WebSocket 기반 Python–Unity 실시간 통신 기능 통합
- Animator, Humanoid IK, CSV logging을 포함한 평가 환경 구성

**기술 스택**

`Python` · `MediaPipe Hands` · `WebSocket` · `Unity` · `Humanoid IK` · `CSV Logging`

[저장소 보기](https://github.com/YooSH-DY/Hand-Finger-gesture-standardization-for-FCI-Finger-Computer-Interface-in-XR) · [게재 정보](https://doi.org/10.1109/ISMAR-Adjunct68609.2025.00097)

---

### 6. Controlling Avatar Locomotion with Minimal Wrist and Finger Gestures

**ACM UIST Adjunct 2025 · 제2저자**

Apple Watch, 손가락 IMU, 웹캠을 결합해 제한된 공간에서 걷기, 후진, 점프 등의 아바타 로코모션을 제어한 멀티센서 인터랙션 시스템입니다.

**담당:** 멀티센서 기반 방법론과 로코모션 매핑 구조 설계, 핵심 입력 처리·제어 로직 구현·수정, 실시간 시스템 통합 및 사용자 평가 환경 구성

**주요 수행 내용**

- Apple Watch, 손가락 IMU, MediaPipe Hands 입력을 결합하는 멀티센서 구조 설계
- 손목 움직임과 손가락 제스처를 걷기, 후진, 방향 전환, 점프 동작으로 변환하는 매핑 정의
- 센서별 입력 범위와 조건을 조정하는 전처리·판별 로직 구현·수정
- Python 기반 데이터 처리와 Unity 아바타 로코모션 제어 기능 통합
- 제한된 공간에서 사용할 수 있는 사용자 평가용 프로토타입과 실험 환경 구성

**기술 스택**

`Python` · `Apple Watch` · `Movella DOT IMU` · `MediaPipe Hands` · `WebSocket` · `Unity` · `C#`

[저장소 보기](https://github.com/YooSH-DY/Controlling-Avatar-Locomotion-with-Minimal-Wrist-and-Finger-Gestures) · [게재 정보](https://doi.org/10.1145/3746058.3758438)

---

## 기술 스택

| 구분 | 기술 |
|---|---|
| 프로그래밍 언어 | Python, C# |
| 비전·AI | OpenCV, MediaPipe Hands, PyTorch, YOLOv10n, DeiT, MLP, SGCN |
| 센서 처리 | IMU quaternion/acceleration, 3D landmarks, One Euro Filter, EMA |
| 실시간 통신 | WebSocket, UDP, JSON command protocol |
| XR·애플리케이션 | Unity, Animator, Humanoid IK, real-time avatar control |
| 실험·평가 | CSV logging, resource profiling, threshold analysis, user-study prototype |

---

## 학력

**중앙대학교 첨단영상대학원 메타버스융합전공 석사과정**  
2026년 8월 졸업예정

**원광대학교 컴퓨터소프트웨어공학 학사**  
2023년 졸업

---

<sub>
본 포트폴리오의 `구현`은 연구 방법과 시스템 요구사항을 바탕으로 코드를 작성·수정하고, 실제 실행 환경에서 통합·검증한 범위를 의미합니다.  
본 저장소는 취업용 연구 포트폴리오 허브입니다.  
각 프로젝트 저장소에는 공개 가능한 소스 코드와 구현 설명만 포함하며, 참가자 데이터, 상용 에셋, 대용량 모델 파일 및 미공개 연구 자료는 제외합니다.
</sub>
