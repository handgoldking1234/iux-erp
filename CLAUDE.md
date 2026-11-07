# IUX ERP 시안 — 작업 안내서

## 한 줄 요약
Claude Design으로 만든 ERP 대시보드 + 그룹웨어(GW) 대시보드 시안.

- 주소: https://iux-erp.vercel.app

## 파일
```
index.html               GW 대시보드로 이동하는 시작 페이지
GW Dashboard.dc.html     그룹웨어 (전자결재·게시판·출퇴근·일정)
ERP Dashboard.dc.html    ERP (수주·매출·수금, 월별 추이, 사업유형별 비중)
support.js               Claude Design 런타임 (수정 금지)
assets/  로고   · uploads/  시안 작업 참고 이미지
```
- 두 화면은 상단 ERP/GW 탭으로 오간다.
- `*.dc.html`은 Claude Design 형식 — 큰 수정은 Claude Design에서 고쳐 다시 내보낼 것. 폰트 Pretendard(CDN).
- 숫자·목록은 예시 데이터.

---

## 공통 작업 원칙 (IUX 프로젝트 전체)
- **언어:** 화면 문구·문서·커밋 메시지는 한국어. 쉬운 말, 기술 용어 최소화.
- **퍼블리싱 시안:** 순수 HTML/CSS + 간단한 스크립트만 넣는다. 서버·DB 연동 코드는 개발 단계에서 따로 붙인다.
- **아이콘:** Lucide. 디자인 시스템을 따로 정하지 않았으면 스포티파이 스타일(다크/화이트 + 포인트 컬러)을 기본으로 쓴다.
- **배포:** GitHub `main` → Vercel 자동 배포. 도메인은 가비아 `iux.kr`의 서브도메인(`*.iux.kr` CNAME → Vercel)을 쓴다.
- **DB:** Supabase 무료 플랜은 활성 프로젝트 2개까지라, 새 프로젝트를 만들지 말고 기존 `iux-cloud`(studio) 프로젝트에 테이블을 얹는 것을 먼저 검토한다.
- **비밀값:** 공개 저장소다. 서비스 키·AI 키·비밀번호는 절대 커밋하지 않는다. 키는 Vercel 환경 변수나 Supabase secrets에 둔다. Supabase anon(public) 키만 코드에 넣을 수 있다.
- **확인:** 고친 뒤에는 브라우저 콘솔 오류 0개, 모바일(390px)과 PC 화면을 눈으로 확인하고 나서 완료라고 한다.
- **브랜치:** `main`은 배포 중인 상태. 큰 작업이나 검증 전 작업은 브랜치(`wip/…`, `claude/…`)에 올리고, `main`을 강제 푸시(-f)로 덮어쓰지 않는다.
- **전체 프로젝트 목록:** https://github.com/handgoldking1234/iux-app/blob/main/docs/PROJECTS.md
