# 공공임대주택 정보 안내 도우미 – 찾아줘 홈즈 🏠
<img src="/홈즈.png" width="800" height="500">

## 📌 프로젝트 개요
본 프로젝트는 공공임대주택 신청 공고문을 활용해 사용자가 손쉽게 원하는 조건의 주택 정보를 찾을 수 있도록 하는 AI 기반의 정보 안내 시스템입니다.<br/>
Azure Document Intelligence를 활용한 데이터 전처리와, LLM 기반 RAG(Retrieval-Augmented Generation) 시스템, 카카오톡 챗봇 인터페이스가 결합된 구조로 구성되어 있습니다.<br/>
또한, 본 시스템은 Python Flask 기반 서버를 Azure Virtual Machine 상에 구축하여 상시 운영되며, 외부 접근을 위해 Ngrok 터널링을 활용해 카카오톡 챗봇과 안정적으로 연동되도록 구성되어 있습니다.<br/>
이를 통해 최종적으로 선택된 공고문 내 세부 정보를 사용자의 질의에 따라 탐색하여 지엽적인 내용까지도 정확하게 응답할 수 있습니다.<br/>

## 🛠️ 기술 스택
<img src="https://img.shields.io/badge/Azure OpenAI-3050FF?style=flat-square&logo=OpenAI&logoColor=white"/> <img src="https://img.shields.io/badge/Azure Document Intelligence-3050FF?style=flat-square&logo=&logoColor=white"/> <img src="https://img.shields.io/badge/Azure AI Search-3050FF?style=flat-square&logo=&logoColor=white"/> <img src="https://img.shields.io/badge/Azure Virtual Machine-3050FF?style=flat-square&logo=&logoColor=white"/><br/>
<img src="https://img.shields.io/badge/flask-000000?style=flat-square&logo=flask&logoColor=white"/> <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white"/> <img src="https://img.shields.io/badge/ngrok-1F1E37?style=flat-square&logo=ngrok&logoColor=white"/> <img src="https://img.shields.io/badge/Kakaotalk-FFCD00?style=flat-square&logo=kakaotalk&logoColor=white"/>

- Azure OpenAI: embedding 모델을 통한 벡터화 및 GPT-4 기반 언어 모델을 사용해 자연어 응답 생성
- Azure Document Intelligence Layout : PDF을 Markdown 파일로 변환
- Azure AI Search: 벡터 기반 유사도 검색으로 관련 공고문 청크를 반환
- Azure VM : Python 기반 Flask 서버를 가상머신에서 상시 운영
- Flask : 로컬 서버 생성
- Ngrok : 로컬/VM 서버를 카카오톡 챗봇에서 접근 가능하도록 터널링
- LangChain: 텍스트 분할, 임베딩 및 RAG 파이프라인 구성
- Python: 전체 백엔드 및 데이터 전처리 로직 작성
- Kakao i 오픈빌더: 사용자 인터페이스 챗봇 구성
<br/>

## 🗂️ 프로젝트 구조
### 활용 데이터셋 : LH, GH, SH 공공주택 모집공고 데이터(.pdf)
- data_preprocessing/main.py/ : PDF -> .md 변환 및 데이터 전처리
- 클라우드.ipynb/ : 청크변환, 임베딩 및 AI search 업로드
- QR.py/ : query rewrite
- RAG.py/ : LLM 기반 RAG를 통한 지정된 공고문의 정보 추출
- personal.py/ : LLM 기반 RAG(none filter)를 통한 사용자 기반 공고문 추천
- app.py/: 시스템의 메인 실행(Flask)

## 🎯 주요 기능

공고문 기반 질의응답:
카카오톡 버튼 상호작용을 통한 공고문 선택 → 해당 공고문에 대한 질문 → RAG기반 응답 생성

사용자 맞춤형 응답:
카카오톡 챗봇에서 사용자의 조건 및 상황을 단계별로 받아서 조건에 맞는 공고문 자동 탐색

PDF 자동 처리 및 AI 벡터 인덱싱:
공고문 PDF파일 전처리, 청크분할, 임베딩, 업로드까지의 과정을 자동화

### 🎥 시연영상 
[시연영상.mp4](https://github.com/hongwon1031/MS_AI_project_2/blob/main/%EC%8B%9C%EC%97%B0%EC%98%81%EC%83%81.mp4)
### 자세한 내용은 [[복덕방7]발표.PDF](https://github.com/hongwon1031/MS_AI_project_2/blob/main/%5B%EB%B3%B5%EB%8D%95%EB%B0%A97%5D%EB%B0%9C%ED%91%9C.pdf) 참고
