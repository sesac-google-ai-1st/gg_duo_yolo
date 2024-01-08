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

- 데이터를 GCP 버킷에 업로드, GCP JUPYTER NOTEBOOK에서 버킷 데이터 다운로드(gsutil 이용)
- 압축 해제(unzip 시 lock 하고 multiprocessing 사용하면 빠르게 가능)

![h7](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/78138e27-3d33-4b2d-a3ae-b21ad450b5a7)

- 데이터 정리
- COCO data 포맷을 YOLO data 포맷으로 변경

![h8](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/56dd94aa-bcab-4033-8c25-d1f0bdd5d09f)

- xml 파일을 txt로 변경

<br>

# 3. 학습

- git clone ultralytics
- yaml 파일 생성

![h9](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/46ca2536-70b7-490f-8e22-18b7fc622da0)

![h10](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/c0ce5fef-5310-4eea-8e66-6475dcbc163f)

- train, val 폴더 정리(데이터 개수 확인)
- 학습

![h12](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/2bc871dc-438e-4205-aeb8-46bc8979ac36)


<br>

# 4. 학습 결과
- confusion matrix

![output](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/5376efea-24c7-49ea-bfd6-cd8d520694c5)

- graph, train의 loss 값이 계속 떨어지는 것으로 보아 더 많은 데이터를 학습시킬 필요가 있다고 보임

![output1](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/743e764b-23c3-4212-9e28-e79c54f2cbf2)

- image

![output2](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/5db6d884-3607-4d2a-8b9a-6e69ce602c16)


<br>

# 5. 검증 및 테스트

### 검증

- 다른 팀들에 비해 다른 작업을 안했는데도 결과값이 좋음
- 데이터 유실 및 파괴가 없는 방식(시간이 오래 걸리는 방식)으로 진행하여 그런 것으로 추정

![b1](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/f9e9c663-e94d-4769-a13d-a03718137a20)

### 테스트

![h13](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/cbf31cd1-ce3a-417c-9dd2-c04d5fdf5e87)
![h1](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/6af710cb-9b7e-4ed3-b91c-32645193bd99)

![h5](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/352ad4f3-d9bf-486c-b5c8-c305a45dbee2)
![h31](https://github.com/sesac-google-ai-1st/gg_duo_yolo/assets/145187337/907f6eee-3e2e-475a-89ac-14087aab7a2d)


<br>

# 6. 한계 및 적용점

### 한계

- 대용량 데이터를 다루다 보니 유실 및 파괴가 있는데 확인 후 정리 필요
- 멀티 GPU 사용하려는데 오류가 생김
- pip install ultralytics, git clone https://github.com/ultralytics/ultralytics 둘 다 하면 사용 가능해짐
- 멀티 GPU 관련하여 정확한 원인 찾을 필요성 있음
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
