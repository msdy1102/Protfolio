# 김민석 포트폴리오 — Vercel 배포 가이드
# 파일 수정하지 말아주세요 ㅠㅠ

## 📁 폴더 구조

```
portfolio-vercel/
├── index.html              ← 포트폴리오 사이트 본체 (루트에 위치)
├── files/
│   ├── pdf/                ← PDF 파일 보관
│   ├── excel/              ← Excel 파일 보관
│   └── pptx/               ← PPT 파일 보관
├── vercel.json             ← Vercel 설정
├── package.json
└── .gitignore
```

> ⚠️ `index.html`은 반드시 **루트**에 있어야 합니다. `public/` 하위에 넣으면 404가 발생합니다.

---

## 📎 파일 추가 방법

### ① 파일을 폴더에 복사

| 파일 종류 | 경로 |
|---------|------|
| PDF | `files/pdf/파일명.pdf` |
| Excel | `files/excel/파일명.xlsx` |
| PPT | `files/pptx/파일명.pptx` |

### ② GitHub에 push

GitHub Desktop → **Commit to main** → **Push origin**
(Vercel이 자동 재배포, 약 30초)

### ③ 사이트에서 경로 연결

1. 사이트 접속 → **관리자** 로그인 (초기: `admin` / `1234`)
2. 해당 문서 → **📎 파일 경로 추가**
3. 경로 입력:
   - `/files/pdf/파일명.pdf`
   - `/files/excel/파일명.xlsx`
   - `/files/pptx/파일명.pptx`
4. **💾 저장** → **📥 HTML 저장** → 다운로드된 파일로 루트의 `index.html` 교체
5. GitHub Desktop에서 **Commit → Push** → 자동 재배포

