# Azure Custom Vision을 사용한 운전자 졸음 감지 시스템
## 프로젝트 개요
본 프로젝트는 공공임대주택 신청 공고문을 활용해 사용자가 손쉽게 원하는 조건의 주택 정보를 찾을 수 있도록 하는 AI 기반의 정보 안내 시스템입니다.
주요 기술로는 Azure의 DI를 통한 데이터 전처리 과정 및 LLM 기반 RAG(Retrieval-Augmented Generation) 시스템과 카카오톡 챗봇 인터페이스가 결합되어 있으며,
사용자의 지역, 조건, 상황에 맞는 주택 공고문 정보를 자연어로 응답합니다.
공공 데이터를 활용한 챗봇 서비스로, 주거 정보 접근성 향상을 목표로 합니다.
## 기술 스택


<img src="https://img.shields.io/badge/Azure-3050FF?style=flat-square&logo=&logoColor=white"/> <img src="https://img.shields.io/badge/Custom Vision-3050FF?style=flat-square&logo=&logoColor=white"/> <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Gradio-F97316?style=flat-square&logo=Gradio&logoColor=white"/> <img src="https://img.shields.io/badge/Hugging Face-FFD21E?style=flat-square&logo=huggingface&logoColor=white"/>

- Azure Custom Vision: 이미지 분류와 객체 감지에 사용됩니다.
- Python: 후처리 및 모델 훈련에 사용됩니다.
- Gradio: 인터페이스 개발에 사용하여 사용자가 쉽게 상호 작용할 수 있도록 합니다.
<br/>

## 프로젝트 구조
- 활용 데이터셋 : [운전자 및 탑승자 상태 및 이상행동 모니터링](https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=651)
- data_preprocessing.ipynb/: 라벨링 데이터 정제
- 평균KSS값추출.ipynb/ : 파이썬 후처리
- 실시간디텍팅.ipynb/ : 디텍션 모델 테스트
- newUI.py/: 시스템의 메인 실행
## 주요 기능
- 실시간 졸음 감지: 카메라를 통해 운전자의 얼굴을 실시간으로 분석하고, 졸음 징후를 감지합니다.
- 경고 시스템: 졸음 징후가 감지되면 경고음을 발생시켜 운전자가 즉시 대응할 수 있도록 합니다.

### 자세한 내용은 [6팀_취합_최종.PDF](https://github.com/hongwon1031/MS_AI_Project_1/blob/main/6%ED%8C%80_%EC%B7%A8%ED%95%A9_%EC%B5%9C%EC%A2%85.pdf) 참고
