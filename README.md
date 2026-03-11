# 📊 FP 자동산정 도구

RFP(제안요청서) 파일을 업로드하면 AI가 자동으로 기능점수(FP)를 산정하고, 보정계수 적용 후 개발원가까지 계산해주는 웹 도구입니다.

## ✨ 주요 기능

- **RFP 파일 업로드**: DOCX, XLSX, PDF, TXT 파일 지원
- **AI 자동 분석**: Claude API로 요구사항 → 단위프로세스 자동 추출
- **FP 유형 자동 분류**: ILF, EIF, EI, EO, EQ 자동 판별
- **보정계수 5종**: 규모(자동), 연계, 성능, 운영환경, 보안
- **원가 자동 계산**: 개발원가 + 이윤 + 직접경비 + HW = 총 사업비
- **Excel 다운로드**: 4개 시트 결과 보고서

## 🚀 배포 방법 (왕초보용 가이드)

### 준비물
1. **GitHub 계정** (무료): https://github.com 에서 회원가입
2. **Streamlit Cloud 계정** (무료): https://streamlit.io/cloud 에서 GitHub로 로그인
3. **Claude API Key**: https://console.anthropic.com 에서 발급 (사용한 만큼만 과금)

### Step 1: GitHub에 코드 올리기

1. https://github.com 로그인
2. 오른쪽 위 **"+"** 버튼 → **"New repository"** 클릭
3. Repository name: `fp-estimator` 입력
4. **"Public"** 선택 (Streamlit Cloud 무료 버전은 Public만 가능)
5. **"Create repository"** 클릭
6. **"uploading an existing file"** 링크 클릭
7. 아래 파일들을 드래그&드롭으로 업로드:
   - `app.py`
   - `requirements.txt`
   - `.streamlit/config.toml` (폴더째로)
8. **"Commit changes"** 클릭

### Step 2: Streamlit Cloud에 배포

1. https://share.streamlit.io 접속
2. **"New app"** 클릭
3. Repository: `내GitHub아이디/fp-estimator` 선택
4. Branch: `main`
5. Main file path: `app.py`
6. **"Deploy!"** 클릭
7. 2~3분 기다리면 배포 완료!

### Step 3: 사용하기

1. 배포 완료되면 URL이 생성됩니다 (예: `https://fp-estimator.streamlit.app`)
2. 이 URL을 **누구에게나 공유**하면 됩니다
3. 사용자가 접속 → 왼쪽 사이드바에 Claude API Key 입력 → RFP 파일 업로드 → 분석!

## 📋 사용법

1. 왼쪽 사이드바에서 **Claude API Key** 입력
2. **"RFP 입력"** 탭에서 파일 업로드 또는 텍스트 붙여넣기
3. **"AI로 자동 분석"** 버튼 클릭 (30초~1분 소요)
4. **"FP 산정 결과"** 탭에서 결과 검토·수정
5. **왼쪽 사이드바**에서 보정계수 설정
6. **"원가 계산"** 탭에서 사업비 확인
7. **"다운로드"** 탭에서 Excel 저장

## 💡 참고사항

- FP 간이법 기준: SW사업 대가산정 기준 (과기정통부 고시)
- FP당 단가: 2026년 추정 639,102원 (2025년 605,784원 × 1.055)
- 이윤율: 9.755% (KRC 사업 기준)
- 보정계수: SW진흥법 시행령 기준 5종
- Claude API 비용: 1회 분석당 약 $0.01~0.05 (매우 저렴)

## 📁 파일 구성

```
fp-estimator/
├── app.py                 # 메인 앱 코드
├── requirements.txt       # 필요한 라이브러리 목록
├── .streamlit/
│   └── config.toml       # 테마 설정
└── README.md             # 이 파일
```
