# 김민석 포트폴리오 — Vercel 배포 가이드

## 📁 폴더 구조

```
portfolio-vercel/
├── public/
│   ├── index.html          ← 포트폴리오 사이트 본체
│   └── files/
│       ├── pdf/            ← PDF 파일 보관
│       ├── excel/          ← Excel 파일 보관
│       └── pptx/           ← PPT 파일 보관
├── vercel.json             ← Vercel 설정
├── package.json
├── .gitignore
└── README.md               ← 이 파일
```

---

## 🚀 배포 방법 (처음 1회)

### 1단계 — GitHub 저장소 만들기

1. https://github.com 로그인
2. 우측 상단 **+** → **New repository** 클릭
3. Repository name: `portfolio` (원하는 이름)
4. **Private** 선택 (포트폴리오는 비공개 저장소 권장)
5. **Create repository** 클릭

### 2단계 — 이 폴더를 GitHub에 올리기

GitHub Desktop 앱을 사용하면 코딩 없이 가능합니다.

1. [GitHub Desktop](https://desktop.github.com/) 설치 및 로그인
2. **File → Add Local Repository** → 이 `portfolio-vercel` 폴더 선택
3. **Publish repository** 클릭 → 위에서 만든 저장소 이름 입력
4. **Publish** 클릭

### 3단계 — Vercel 연결

1. https://vercel.com 에서 GitHub 계정으로 로그인
2. **Add New Project** 클릭
3. 방금 만든 GitHub 저장소 선택 → **Import**
4. 설정 화면에서 아무것도 바꾸지 않고 **Deploy** 클릭
5. 잠시 후 배포 완료 → `https://포트폴리오이름.vercel.app` 주소 생성

---

## 📎 파일 추가하는 방법 (배포 후)

### PDF/Excel 파일을 사이트에 연결하는 순서

**① 파일을 올바른 폴더에 복사**

| 파일 종류 | 폴더 경로 |
|---------|---------|
| PDF | `public/files/pdf/` |
| Excel | `public/files/excel/` |
| PPT | `public/files/pptx/` |

**② GitHub에 push (파일 업로드)**

GitHub Desktop에서:
1. 변경된 파일이 왼쪽 목록에 표시됨
2. 하단 **Summary** 칸에 메모 입력 (예: `포트폴리오 PDF 추가`)
3. **Commit to main** 클릭
4. **Push origin** 클릭
5. Vercel이 자동으로 재배포 (약 30초~1분)

**③ 사이트에서 경로 연결**

1. 배포된 사이트 열기
2. 우측 하단 **관리자** 버튼 → 로그인 (초기 비밀번호: `admin` / `1234`)
3. 해당 문서 항목의 **📎 파일 경로 추가** 버튼 클릭
4. 경로 입력:
   - PDF: `/files/pdf/파일명.pdf`
   - Excel: `/files/excel/파일명.xlsx`
   - PPT: `/files/pptx/파일명.pptx`
5. 💾 **저장** 버튼 클릭
6. **📥 HTML 저장** 버튼 → 다운로드된 HTML로 GitHub 안의 `public/index.html`을 교체
7. GitHub Desktop에서 **Commit → Push** → 자동 재배포

---

## 🔐 초기 비밀번호

- 아이디: `admin`
- 비밀번호: `1234`

**⚠️ 배포 후 반드시 변경하세요!**
관리자 로그인 → 우측 패널 → **보안** 탭 → 비밀번호 변경

---

## 💡 파일 경로 예시

```
/files/pdf/portfolio_RPG.pdf
/files/pdf/portfolio_shooting.pdf
/files/pdf/career_description.pdf
/files/excel/data_table_sample.xlsx
/files/excel/balance_design.xlsx
/files/pptx/portfolio_presentation.pptx
```

---

## ❓ 자주 묻는 질문

**Q. 파일을 올렸는데 사이트에서 링크가 안 열려요**
→ Vercel 재배포가 완료됐는지 확인하세요. Push 후 약 1분 대기

**Q. 관리자에서 저장했는데 새로고침하면 사라져요**
→ 💾 저장 버튼 클릭 후, 📥 HTML 저장으로 파일을 받아서 GitHub에 다시 push해야 합니다

**Q. 사이트 주소를 바꾸고 싶어요**
→ Vercel 대시보드 → 프로젝트 → Settings → Domains에서 변경 가능
