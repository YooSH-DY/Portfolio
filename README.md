# SeHyeok Yoo

**Research & Software Engineer**  
`Computer Vision` · `Sensor Fusion` · `Real-time Interaction` · `Applied AI`

비전과 웨어러블 센서 데이터를 안정적인 제스처 인식 결과로 변환하고,  
이를 실제로 동작하는 실시간 인터랙션 시스템까지 연결합니다.

[GitHub](https://github.com/YooSH-DY) · Email: `imasp@naver.com` ·

---

## About

컴퓨터소프트웨어공학을 전공하고, 중앙대학교 첨단영상대학원에서 XR/HCI와 실시간 제스처 인식 시스템을 연구했습니다.

주요 관심 분야는 **비전 기반 손 추적**, **IMU·웨어러블 센서 융합**, **강건한 제스처 인식**, **실시간 아바타 인터랙션**입니다. MediaPipe 3D landmark와 IMU quaternion·acceleration 데이터를 처리하고, 규칙 기반 방법과 딥러닝 모델을 비교하며, Python 백엔드와 Unity 클라이언트를 연결하는 end-to-end 시스템을 구현해왔습니다.

---

## Core Competencies

- **Real-time AI application**  
  센서 입력 수집, 전처리, 인식·분류, 네트워크 통신, Unity 반영까지 이어지는 실시간 파이프라인 구현

- **Robust gesture recognition**  
  3D landmark의 각도·거리·관계 특징 설계, 3단계 상태 분류, One Euro Filter·EMA·temporal validation 적용

- **Model comparison and evaluation**  
  Rule-based method와 YOLOv10n, DeiT, MLP, SGCN 기반 모델의 정확도·처리 속도·자원 사용량 비교

- **Multimodal interaction**  
  Webcam, Apple Watch, Movella DOT IMU 등 이질적인 입력을 결합한 아바타 제어 시스템 개발

- **Research engineering**  
  실험용 프로토타입, CSV logging, resource profiling, 사용자 평가용 시스템 및 연구 코드 정리

---

## Featured Projects

### 1. 가상현실 환경의 손·손가락 제스처 인식을 위한 구조화된 3단계 분류 모델

**Journal of KIISE, 2026 · First Author · Repository Available**

카메라 기반 손 추적에서 발생하는 경계 구간의 흔들림을 줄이기 위해 손가락 상태를 `extension / in-between / flexion`의 3단계로 구조화한 실시간 제스처 인식 시스템입니다.

**My Contribution**

- 손가락 상태 및 손가락 간 관계를 이용한 규칙 기반 인식 방법 설계
- MediaPipe Hands 기반 landmark 처리와 EMA 기반 입력 안정화
- Python 인식 백엔드와 WebSocket 기반 Unity 인터랙션 연동
- 무기 조작, 객체 선택, 조명 제어 등 실시간 가상환경 기능 구현
- 사용자 평가에 활용할 수 있는 실행 시스템 구성

**Tech Stack**

`Python` · `OpenCV` · `MediaPipe Hands` · `WebSocket` · `Unity` · `C#`

[View Repository](https://github.com/YooSH-DY/JOK26-3) · [Publication](https://jok.kiise.or.kr/digital-library/manuscript/file/106055/07.pdf)


---

### 2. Multi-view Hand Gesture Recognition Pipeline

**Ongoing Research · Repository Available**

Top/Bottom 카메라 기반 데이터 수집부터 RuleBase와 딥러닝 모델 학습, 실시간 비교, 자원 측정, Unity 연동까지 하나의 환경에서 수행할 수 있도록 구성한 연구 파이프라인입니다.

**My Contribution**

- 사용자·세션 단위 듀얼 카메라 제스처 데이터 수집 및 로그 구조 설계
- MediaPipe 3D landmark 기반 state/relation vector RuleBase 구현
- YOLOv10n, DeiT, MLP, SGCN 기반 비교 모델 학습 및 실행
- FPS, CPU, RAM, GPU, prediction, confidence를 저장하는 측정 파이프라인 구현
- 정적·동적 제스처 안정화와 UDP 기반 Unity command bridge 구성

**Tech Stack**

`Python` · `PyTorch` · `YOLOv10n` · `DeiT` · `SGCN` · `MediaPipe` · `UDP` · `Unity`

[View Repository](https://github.com/YooSH-DY/multi-view-hand-gesture-recognition)

> 논문 심사와 연구 데이터 보호를 위해 원본 참가자 영상, 전체 실험 로그, 모델 가중치와 심사 자료는 공개 저장소에서 제외했습니다.

---

### 3. Hand/Finger Gesture Standardization for FCI in XR

**IEEE ISMAR-Adjunct 2025 · Repository in Preparation**

손 형태와 손가락 간 거리를 아바타의 동작 모드 및 연속 모션 파라미터로 변환하는 실시간 인터랙션 시스템입니다. 사용자별 캘리브레이션, temporal stabilization, 실험 로그 기록을 포함합니다.

**Implementation Contribution**

- MediaPipe 기반 hand gesture mode detection
- 사용자별 손가락 거리 캘리브레이션 및 정규화
- EMA와 연속 프레임 확인을 이용한 입력 안정화
- WebSocket 기반 Python–Unity 실시간 통신
- Animator, Humanoid IK, 실험용 CSV logging 연동

**Tech Stack**

`Python` · `MediaPipe Hands` · `WebSocket` · `Unity` · `Humanoid IK` · `CSV Logging`

[View Paper](https://doi.org/10.1109/ISMAR-Adjunct68609.2025.00097)  
`Repository: In preparation`

---

## Additional Research Projects

> 아래 프로젝트 저장소는 취업 포트폴리오 형태로 정리 중입니다. 논문 링크는 먼저 공개하고, 코드 저장소는 준비되는 순서대로 연결할 예정입니다.

### Minimal Input to Maximal Movement: Real-Time Avatar Control with Dual-sensor

**ACM VRST 2025 · First Author**

웹캠과 손등 IMU의 최소 입력으로 복잡한 아바타 댄스 동작과 모션 파라미터를 실시간 제어한 시스템입니다.

- Webcam + Movella DOT 기반 dual-sensor interaction
- 손가락 상태를 이용한 dance variation 제어
- 손목 움직임을 이용한 속도·다리 높이 등 연속 제어
- Python, WebSocket, Unity 기반 실시간 시스템 구현

[View Paper](https://doi.org/10.1145/3756884.3768392) · `Repository: In preparation`

---

### Wrist-Based Spatial Gestures for Multi-Parameter Avatar Dance Control

**ACM SUI 2025 · Co-Author**

손등의 단일 IMU 센서로 손목 roll/pitch를 분석하고 방향, 상체 회전, 골반 기울기, 애니메이션 속도를 동시에 제어한 인터랙션입니다.

- IMU quaternion 기반 spatial gesture processing
- 복수 아바타 파라미터의 실시간 매핑
- 음악 템포에 따른 표현적 움직임 분석
- Unity 기반 인터랙션 프로토타입 구현

[View Paper](https://doi.org/10.1145/3694907.3765952) · `Repository: In preparation`

---

### Controlling Avatar Locomotion with Minimal Wrist and Finger Gestures

**ACM UIST Adjunct 2025 · Co-Author**

Apple Watch, 손가락 IMU, 웹캠을 결합해 제한된 공간에서도 걷기, 후진, 점프와 같은 아바타 로코모션을 제어하는 멀티센서 FCI 시스템입니다.

- Apple Watch + Movella DOT + MediaPipe 입력 통합
- 센서 데이터 처리 및 실시간 Unity 연동
- 제한된 공간을 위한 minimal-input locomotion 구현
- 사용자 평가용 프로토타입 구성

[View Paper](https://doi.org/10.1145/3746058.3758438) · `Repository: In preparation`

---

## Publications

### Journal

- **SeHyeok Yoo**, et al.  
  *가상현실 환경의 손·손가락 제스처 인식을 위한 구조화된 3단계 분류 모델.*  
  Journal of KIISE, 2026.  
  [Repository](https://github.com/YooSH-DY/JOK26-3)

### International Conferences

- **SeHyeok Yoo**, Kyung Min Kim, Youngho Chai.  
  *Minimal Input to Maximal Movement: Real-Time Avatar Control with Dual-sensor.*  
  ACM VRST 2025.  
  [Paper](https://doi.org/10.1145/3756884.3768392)

- Kyung Min Kim, **SeHyeok Yoo**, Youngho Chai.  
  *Wrist-Based Spatial Gestures for Multi-Parameter Avatar Dance Control.*  
  ACM SUI 2025.  
  [Paper](https://doi.org/10.1145/3694907.3765952)

- Kyung Min Kim, **Se Hyeok Yoo**, Young Ho Chai.  
  *Controlling Avatar Locomotion with Minimal Wrist and Finger Gestures.*  
  ACM UIST Adjunct 2025.  
  [Paper](https://doi.org/10.1145/3746058.3758438)

- Kyung Min Kim, **Se Hyeok Yoo**, Youngho Chai.  
  *Hand/Finger Gesture Standardization for FCI (Finger-Computer-Interface) in XR.*  
  IEEE ISMAR-Adjunct 2025.  
  [Paper](https://doi.org/10.1109/ISMAR-Adjunct68609.2025.00097)

---

## Technical Skills

| Category | Skills |
|---|---|
| Languages | Python, C# |
| Vision & AI | OpenCV, MediaPipe Hands, PyTorch, YOLOv10n, DeiT, MLP, SGCN |
| Sensor Processing | IMU quaternion/acceleration, 3D landmarks, One Euro Filter, EMA |
| Real-time Communication | WebSocket, UDP, JSON command protocol |
| XR & Application | Unity, Animator, Humanoid IK, real-time avatar control |
| Experimentation | CSV logging, resource profiling, threshold analysis, user-study prototype |

---

## Education

**M.S. in Metaverse Convergence**  
Chung-Ang University, Graduate School of Advanced Imaging Science  
Expected Aug. 2026

**B.S. in Computer Software Engineering**  
Wonkwang University, 2023

---

## Contact

- GitHub: [YooSH-DY](https://github.com/YooSH-DY)
- Email: `imasp@naver.com`
<!--
- Resume: `YOUR_RESUME_LINK`
-->
---

<sub>
This repository is a recruitment-oriented portfolio hub.  
Each linked project repository contains a source-only implementation bundle; participant data, commercial assets, large model files, and unpublished research materials are excluded.
</sub>
