# 공공임대주택 정보 안내 도우미 – 찾아줘 홈즈 🏠
## 📌 프로젝트 개요
본 프로젝트는 공공임대주택 신청 공고문을 활용해 사용자가 손쉽게 원하는 조건의 주택 정보를 찾을 수 있도록 하는 AI 기반의 정보 안내 시스템입니다.
주요 기술로는 Azure의 DI를 통한 데이터 전처리 과정 및 LLM 기반 RAG(Retrieval-Augmented Generation) 시스템과 카카오톡 챗봇 인터페이스가 결합되어 있으며,
사용자의 지역, 조건, 상황에 맞는 주택 공고문 정보를 자연어로 응답합니다.
공공 데이터를 활용한 챗봇 서비스로, 주거 정보 접근성 향상을 목표로 합니다.

## 🛠️ 기술 스택
<img src="https://img.shields.io/badge/Azure OpenAI-3050FF?style=flat-square&logo=OpenAI&logoColor=white"/> <img src="https://img.shields.io/badge/Azure Document Intelligence-3050FF?style=flat-square&logo=&logoColor=white"/> <img src="https://img.shields.io/badge/Azure Virtual Machine-3050FF?style=flat-square&logo=&logoColor=white"/><br/>
<img src="https://img.shields.io/badge/flask-000000?style=flat-square&logo=flask&logoColor=white"/> <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white"/> <img src="https://img.shields.io/badge/ngrok-1F1E37?style=flat-square&logo=ngrok&logoColor=white"/> <img src="https://img.shields.io/badge/Kakaotalk-FFCD00?style=flat-square&logo=kakaotalk&logoColor=white"/>

- Azure OpenAI: embedding 모델을 통한 벡터화 및 GPT-4 기반 언어 모델을 사용해 자연어 응답 생성 
- Azure AI Search: 벡터 기반 유사도 검색으로 관련 공고문 청크를 반환
- Azure VM : Python 기반 Flask 서버를 가상머신에서 상시 운영
- Flask : 로컬 서버 생성
- Ngrok : 로컬/VM 서버를 카카오톡 챗봇에서 접근 가능하도록 터널링
- LangChain: 텍스트 분할, 임베딩 및 RAG 파이프라인 구성
- Python: 전체 백엔드 및 데이터 전처리 로직 작성
- Kakao i 오픈빌더: 사용자 인터페이스 챗봇 구성
<br/>

## 🗂️ 프로젝트 구조
- 활용 데이터셋 : LH, GH, SH 공공주택 모집공고 데이터(.pdf)
- data_preprocessing/main.py/ : PDF -> .md 변환 및 데이터 전처리
- 클라우드.ipynb/ : 청크변환, 임베딩 및 AI search 업로드
- QR.py/ : query rewrite
- RAG.py/ : LLM 기반 RAG를 통한 지정된 공고문의 정보 추출
- personal.py/ : LLM 기반 RAG(none filter)를 통한 사용자 기반 공고문 추천
- app.py/: 시스템의 메인 실행(Flask)

## 🎯 주요 기능
공고문 기반 질의응답:
사용자가 원하는 주택 조건을 입력하면 관련 공고의 세부 내용을 추출해 자연어로 답변.

지역 기반 검색:
“서울 강남 지역의 청년 전세임대 있나요?” → 해당 공고가 있을 경우 연결

사용자 맞춤형 응답:
카카오톡 챗봇에서 사용자 응답을 단계별로 받아서 조건에 맞는 공고문 자동 탐색

PDF 자동 처리 및 AI 벡터 인덱싱:
공공데이터 포털의 PDF 파일을 자동 수집, 텍스트 변환, 분할 및 벡터화하여 질의 가능하게 함


### 자세한 내용은 [6팀_취합_최종.PDF](https://github.com/hongwon1031/MS_AI_Project_1/blob/main/6%ED%8C%80_%EC%B7%A8%ED%95%A9_%EC%B5%9C%EC%A2%85.pdf) 참고
