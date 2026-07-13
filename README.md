# 유세혁

**연구·소프트웨어 엔지니어**  
`컴퓨터 비전` · `센서 융합` · `실시간 인터랙션` · `응용 AI`

비전과 웨어러블 센서 데이터를 안정적인 제스처 인식 결과로 변환하고,  
이를 실제로 동작하는 실시간 인터랙션 시스템까지 연결합니다.

[이메일](imasp@naver.com)

---

## 소개

컴퓨터소프트웨어공학을 전공하고, 중앙대학교 첨단영상대학원에서 XR/HCI와 실시간 제스처 인식 시스템을 연구했습니다.

주요 관심 분야는 **비전 기반 손 추적**, **IMU·웨어러블 센서 융합**, **강건한 제스처 인식**, **실시간 아바타 인터랙션**입니다. MediaPipe 3D landmark와 IMU quaternion·acceleration 데이터를 처리하고, 규칙 기반 방법과 딥러닝 모델을 비교하며, Python 백엔드와 Unity 클라이언트를 연결하는 end-to-end 시스템을 구현해왔습니다.

---

## 핵심 역량

- **실시간 AI 애플리케이션 구현**  
  센서 입력 수집, 전처리, 인식·분류, 네트워크 통신, Unity 반영까지 이어지는 실시간 파이프라인 구현

- **강건한 제스처 인식**  
  3D landmark의 각도·거리·관계 특징 설계, 3단계 상태 분류, One Euro Filter·EMA·temporal validation 적용

- **모델 비교 및 평가**  
  규칙 기반 방법과 YOLOv10n, DeiT, MLP, SGCN의 정확도·처리 속도·자원 사용량 비교

- **멀티모달 인터랙션**  
  Webcam, Apple Watch, Movella DOT IMU 등 서로 다른 입력을 결합한 아바타 제어 시스템 개발

- **연구 시스템 구현**  
  실험용 프로토타입, CSV logging, resource profiling, 사용자 평가용 시스템 및 연구 코드 정리

---

## 연구 프로젝트

### 1. 가상현실 환경의 손·손가락 제스처 인식을 위한 구조화된 3단계 분류 모델

**정보과학회논문지 · 2026 · 제1저자**

카메라 기반 손 추적에서 발생하는 경계 구간의 흔들림을 줄이기 위해 손가락 상태를 `펴짐 / 중간 / 굽힘`의 3단계로 구조화한 실시간 제스처 인식 시스템입니다.

**주요 구현**

- 손가락 상태와 손가락 간 관계를 이용한 규칙 기반 인식 방법 설계
- MediaPipe Hands 기반 landmark 처리와 EMA 기반 입력 안정화
- Python 인식 백엔드와 WebSocket 기반 Unity 인터랙션 연동
- 무기 조작, 객체 선택, 조명 제어 등 실시간 가상환경 기능 구현
- 사용자 평가에 활용할 수 있는 실행 시스템 구성

**기술 스택**

`Python` · `OpenCV` · `MediaPipe Hands` · `WebSocket` · `Unity` · `C#`

[저장소 보기](https://github.com/YooSH-DY/JOK26-3) · [게재 정보](https://jok.kiise.or.kr/digital-library/manuscript/file/106055/07.pdf)

---

### 2. Multi-view Hand Gesture Recognition Pipeline

**진행 중인 연구 · 저장소 공개**

Top/Bottom 카메라 기반 데이터 수집부터 규칙 기반 방법과 딥러닝 모델 학습, 실시간 비교, 자원 측정, Unity 연동까지 하나의 환경에서 수행할 수 있도록 구성한 연구 파이프라인입니다.

**주요 구현**

- 사용자·세션 단위 듀얼 카메라 제스처 데이터 수집 및 로그 구조 설계
- MediaPipe 3D landmark 기반 state/relation vector RuleBase 구현
- YOLOv10n, DeiT, MLP, SGCN 기반 비교 모델 학습 및 실행
- FPS, CPU, RAM, GPU, prediction, confidence 측정 파이프라인 구현
- 정적·동적 제스처 안정화와 UDP 기반 Unity command bridge 구성

**기술 스택**

`Python` · `PyTorch` · `YOLOv10n` · `DeiT` · `SGCN` · `MediaPipe` · `UDP` · `Unity`

[저장소 보기](https://github.com/YooSH-DY/multi-view-hand-gesture-recognition)

> 논문 심사와 연구 데이터 보호를 위해 원본 참가자 영상, 전체 실험 로그, 모델 가중치와 심사 자료는 공개 저장소에서 제외했습니다.

---

### 3. Hand/Finger Gesture Standardization for FCI (Finger-Computer-Interface) in XR

**IEEE ISMAR-Adjunct 2025 · 포스터 · 제2저자**

손 형태와 손가락 간 거리를 아바타의 동작 모드 및 연속 모션 파라미터로 변환하는 실시간 인터랙션 시스템입니다.

**주요 구현**

- MediaPipe 기반 hand gesture mode detection
- 사용자별 손가락 거리 캘리브레이션 및 정규화
- EMA와 연속 프레임 확인을 이용한 입력 안정화
- WebSocket 기반 Python-Unity 실시간 통신
- Animator, Humanoid IK, 실험용 CSV logging 연동

**기술 스택**

`Python` · `MediaPipe Hands` · `WebSocket` · `Unity` · `Humanoid IK` · `CSV Logging`

[게재 정보](https://doi.org/10.1109/ISMAR-Adjunct68609.2025.00097)  
`저장소 정리 중`

---

## 학회 프로젝트

### Minimal Input to Maximal Movement: Real-Time Avatar Control with Dual-sensor

**ACM VRST 2025 · 포스터 · 제1저자**

웹캠과 손등 IMU를 결합해 아바타 댄스 동작과 모션 파라미터를 실시간으로 제어한 시스템입니다.

[게재 정보](https://doi.org/10.1145/3756884.3768392) · `저장소 정리 중`

---

### Wrist-Based Spatial Gestures for Multi-Parameter Avatar Dance Control

**ACM SUI 2025 · 포스터 · 제2저자**

손등의 단일 IMU 센서로 손목 움직임을 분석하고 복수의 아바타 동작 파라미터를 제어한 인터랙션입니다.

[게재 정보](https://doi.org/10.1145/3694907.3765952) · `저장소 정리 중`

---

### Controlling Avatar Locomotion with Minimal Wrist and Finger Gestures

**ACM UIST Adjunct 2025 · 포스터 · 제2저자**

Apple Watch, 손가락 IMU, 웹캠을 결합해 제한된 공간에서 아바타 로코모션을 제어한 멀티센서 인터랙션 시스템입니다.

[게재 정보](https://doi.org/10.1145/3746058.3758438) · `저장소 정리 중`

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

## 연락처

- 이메일: [imasp@naver.com](mailto:imasp@naver.com)

---

<sub>
본 저장소는 취업용 연구 포트폴리오 허브입니다.  
각 프로젝트 저장소에는 공개 가능한 소스 코드와 구현 설명만 포함하며, 참가자 데이터, 상용 에셋, 대용량 모델 파일 및 미공개 연구 자료는 제외합니다.
</sub>
