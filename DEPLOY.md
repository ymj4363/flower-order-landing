# 🚀 Cloudflare Pages 배포 가이드

배포용 파일은 `dist/` 폴더에 있습니다. 원본 `index.html`은 그대로 유지됩니다.

## 파일 구조

```
flower-order-landing/
├── index.html          ← 원본 (수정/개발용)
├── dist/
│   ├── index.html      ← 배포용 (SEO·보안 태그 추가)
│   ├── _headers        ← 보안 헤더 설정
│   └── _redirects      ← 리디렉션 규칙
└── DEPLOY.md           ← 이 파일
```

## 배포 방법 (Cloudflare Pages)

### 방법 1: GitHub 연동 (자동 배포 — 추천)

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) 로그인
2. **Workers & Pages** → **Create application** → **Pages** 탭
3. **Connect to Git** → GitHub 저장소 선택
4. 빌드 설정:
   | 항목 | 값 |
   |------|-----|
   | Framework preset | None |
   | Build command | *(비워두기)* |
   | Build output directory | `dist` |
5. **Save and Deploy** 클릭
6. 이후 `main` 브랜치에 push하면 자동 배포 🎉

### 방법 2: 직접 업로드 (빠른 배포)

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) 로그인
2. **Workers & Pages** → **Create application** → **Pages** 탭
3. **Upload assets** 선택
4. 프로젝트 이름 입력 (예: `bloom-flower`)
5. `dist/` 폴더 전체를 드래그 앤 드롭
6. **Deploy site** 클릭

## 배포 후 확인 사항

- [ ] 페이지 정상 로딩 확인
- [ ] 모바일 반응형 확인
- [ ] 주문 폼 동작 확인
- [ ] 커스텀 도메인 연결 (선택): Settings → Custom domains

## 커스텀 도메인 연결 (선택)

1. Cloudflare Pages → 프로젝트 → **Custom domains**
2. 도메인 입력 후 DNS 레코드 자동 설정
3. SSL 인증서 자동 발급 (Let's Encrypt)
