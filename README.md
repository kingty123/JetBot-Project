# JetBot-Project

## 개요
- 본 프로젝트는 NVIDIA JetBot 키트를 활용하여 영상 처리 기술과 자율 주행 기능을 구현하는 것을 목표로 합니다.
- AI 기술(물체 인식, 장애물 회피) 및 자율 주행을 로봇에 적용해보고 싶을 때 초보자도 쉽게 이해하고 접근할 수 있도록 구성되었습니다. 😊
- Jetson Nano는 프로그래밍하기 쉬운 환경을 제공하며, 카메라가 내장된 휴대용 배터리 구동 AI 컴퓨터로서 프로젝트 진행에 용이합니다.
<br>
  
<p align = "center"><img src = "https://github.com/user-attachments/assets/b30ec8e1-13a9-4a29-bc5b-375667c3246a" width="70%" height="70%"></p>
<br>

## 목표
- 내장 카메라(800만 화소)를 활용한 이미지 인식
- 충돌 방지 기능 구현
- 도로를 따라가는 자율 주행 기능 구현
- 특정 객체 추적 기능 구현
<br>

## Process
1) Jetbot 전용 SW 구축: Jetbot을 제어하고 필요한 기능을 수행하기 위한 소프트웨어를 개발
2) Jetbot과 통신 가능한 웹 서버 구축: 웹 인터페이스를 통해 Jetbot을 원격으로 제어하고 상태를 확인
3) 요청에 따른 이미지와 텍스트 처리: 웹 서버를 통해 받은 요청에 따라 Jetbot이 촬영한 이미지를 처리하고 텍스트 정보를 추출 (OCR 등).
4) TTS (Text-To-Speech) 기능: 텍스트 정보를 음성으로 변환하여 사용자에게 제공
5) 사용자 명령을 해석 및 JetBot 동작으로 변환: 웹 인터페이스를 통해 사용자가 내린 명령을 해석하여 Jetbot의 동작을 제어
6) 웹 인터페이스 제공: 사용자가 Jetbot의 기능을 쉽게 사용하고 확인할 수 있는 웹 기반 인터페이스를 개발
<br>

## Detail
1) 이미지 인식: 내장 카메라를 활용하여 이미지를 얻고, 이를 분석하여 특정 물체를 인식하거나 상황 판단
2) 충돌 방지: Jetbot 센서 데이터를 수집하고, Jetson Nano에서 학습된 모델을 활용하여 장애물을 감지하고 회피합니다. Jetbot에서 실시간으로 충돌 방지 데모를 실행
3) 도로 따라가기: FastAPI 및 granite3.2-vision와 같은 프레임워크를 활용하여 객체 인식 및 자율 주행 알고리즘을 개발 <br>
👉 FastAPI 프레임워크를 사용하여 Ollama 모델과 JetBot을 연동하는 API 서버를 구축 <br>
👉 사용자의 프롬프트를 받아 Ollama에 전달하고, Ollama의 응답에 따라 JetBot을 제어하고, 결과를 사용자에게 반환 <br>
👉 TTS 엔진을 사용하여 텍스트를 음성으로 변환하고, 대화 내용을 메모리에 저장하는 기능도 제공 <br>
4) 객체 추적: 미리 학습된 객체 감지 모델을 다운로드하여 Jetbot에 적용

<br>

## 결과
✔️ 약 200여장의 사진을 직접 수집하고, Jetbot 링크에서 얻은 이미지로 훈련시켰다.
<br>

### 사물인식 및 객체추적
<p align="center"><img src = "https://github.com/user-attachments/assets/c98a0cea-c545-43a1-a861-4f6983b341b8" width="20%" height="20%"></p> 
<br>

### 도로주행
<p align="center"><img src = "https://github.com/user-attachments/assets/ca29bc3f-ebef-41cb-be21-729dae1fb07a" width="40%" height="40%"></p>
