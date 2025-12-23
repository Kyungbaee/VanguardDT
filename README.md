# VanguardDT

### 1) 자율 주행

### 2) SLAM + 맵 구성

### 3) GUI 구성




### 4) 3D Gaussian Splatting Pipeline

| Meeting Room | Ogu |
| :---: | :---: |
| [![MeetingRoom](./gif/MeetingRoom.gif)](https://sikk806.github.io/VanguardDT/?url=https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/resolve/main/models/test2.splat) | [![Ogu](./gif/ogu.gif)](https://sikk806.github.io/VanguardDT/?url=https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/resolve/main/ogu.splat) |
| [🔗 Interactive Viewer](https://sikk806.github.io/VanguardDT/?url=https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/resolve/main/models/test2.splat) | [🔗 Interactive Viewer](https://sikk806.github.io/VanguardDT/?url=https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/resolve/main/ogu.splat) |

> 💡 **Tip:** 움직이는 이미지를 클릭하면 실시간 3D 뷰어로 연결됩니다.

</br>

프로젝트에서 실시간 3D 자산 생성을 위한 **가우시안 스플래팅(Gaussian Splatting) 학습 및 배포 파이프라인** 구축 </br>
저사양 환경(VRAM 4GB)에서의 최적화와 영상 입력부터 웹 배포까지의 **전과정 자동화**

#### 1. 기술 스택 및 환경 설정
* **Core:** Python, PyTorch (CUDA 11.8), COLMAP, FFmpeg
* **Rendering:** 3D Gaussian Splatting (SIGGRAPH 2023)
* **Visualization:** Unreal Engine 5.4 (XVerse Plugin), WebGL (Splat Viewer)
* **Storage & Hosting:** Hugging Face (Model Storage), GitHub Pages (Web Hosting)
</br>

#### 2. 전과정 자동화 파이프라인
데이터 전처리부터 모델 업로드, URL 배포까지 한 번의 명령어로 수행하는 **pipeline.py**를 구축

**실행 명령어 :**
```bash
python pipeline.py <video_data_path>
```

**자동화 단계**
1. **Preprocessing:** 이미지 리사이징 (640p -> 320p)
2. **SfM:** COLMAP을 통한 카메라 위치 추정
3. **Training:** 3D Gaussian Splatting 모델 학습 (7,000 iter)
4. **Convert:** .ply 파일을 웹 친화적인 .splat 확장자로 자동 변환
5. **Auto Upload:** Hugging Face API를 통해 학습 모델을 원격 저장소에 업로드 및 최종 결과 URL 반환
</br>

#### 3. 결과물
* **Dataset:** [Hugging Face Repository](https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/tree/main)
* **Live Demo:** [VanguardDT Online Viewer](https://sikk806.github.io/VanguardDT/?url=https://huggingface.co/datasets/kyungbae/ssafy-3d-splat/resolve/main/ogu.splat)
</br>
