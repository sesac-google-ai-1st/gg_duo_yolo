# 👬 gg_duo_yolo

> 고속도로 CCTV 차량 탐지 프로젝트

![h6](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/345e4f70-8622-48a5-9a86-5aec976f0e85)


# 📺 Result

![h5](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/352ad4f3-d9bf-486c-b5c8-c305a45dbee2)
![h31](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/907f6eee-3e2e-475a-89ac-14087aab7a2d)

# 🥇 Validate Custom Model

![b1](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/f9e9c663-e94d-4769-a13d-a03718137a20)

---

<br>

# 1. 프로젝트 소개

### 목표

- "교통문제 해결을 위한 CCTV 교통 영상(고속도로)" 데이터 중 영동선 신갈분기점 데이터를 YOLOv8을 이용하여 객체 탐지(차, 버스, 트럭)를 목표로 함
- 데이터 출처 : https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=164

### 진행 순서

- 데이터 전처리, 학습을 위한 환경 구축, 학습 및 검증

<br>

# 2. 데이터 전처리

- 데이터를 GCP 버킷에 업로드, GCP JUPYTER NOTEBOOK에서 버킷 데이터 다운로드 및 압축 해제
- 데이터 정리 및 COCO data 포맷을 YOLO data 포맷으로 변경

<br>

# 3. 학습

- git clone ultralytics, yaml 파일 생성, train, val 폴더 정리
- 학습

<br>

# 4. 학습 결과
- confusion matrix
- graph
- image

<br>

# 5. 검증 및 테스트
- 검증
- 테스트

<br>

# 6. 한계 및 적용점

### 한계

- 테스트 이미지를 보면 왼쪽 아래쪽에 버스가 아닌데 버스로 인식함
- 좀 더 많은 버스 데이터로 학습 필요하다고 논의함

### 적용점

- 테스트 이미지를 보면 경부선 데이터에 버스전용차로가 있어 버스가 더 많다.
- 이미지 개선 및 부분 탐지로 버스 전용차로 위반 차량 탐지 가능할 것으로 논의함

<br>

## cf. 첨부파일 설명

- highway_yolov8_data_cleaning.ipynb : 고속도로 CCTV 이미지 및 라벨 파일 전처리
- highway_yolov8_model.ipynb : 고속도로 CCTV 차량 탐지 모델 생성 (yolov8 medium model)
- test_video.avi : 생성한 yolov8m 모델로 실시간 고속도로 CCTV 객체 탐지 실습 동영상 (약 1분 30초)
