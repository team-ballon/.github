
# 🛍️ AI 기반 관리자 중심 쇼핑몰 플랫폼

> **목표**: 관리자/입점사 업무에 초점을 맞춘 상거래 운영 플랫폼을 구축하고, **AI 에이전트**로 트렌드 분석·재고 예측·이탈 고객 탐지를 자동화합니다.

- **메인 데모**: https://ba1lon.shop/
- **관리자 UI 템플릿**: https://admin.ba1lon.shop/
- **파트너 UI 템플릿**: https://partner.ba1lon.shop/

---

## 🧩 Tech Stack
- **Frontend**: React + Bootstrap Template (Responsive)
- **Backend**: Java Spring, Python
- **Infra**: Vultr VPS, GitHub Actions (CI/CD), Nginx
- **DB/Storage**: PostgreSQL, Cloudflare(이미지)

## ✅ 핵심 기능 요약
- **USER**
  - 검색/필터, 장바구니/주문/결제, 주문/배송 조회, 리뷰
- **SYS(관리자)**
  - RBAC 계정, 로그 기록, 대시보드(최신 분석 렌더링), 이벤트 공지
  - AI: 트렌드 분석, 재고 예측(임계치 알림), 이탈 고객 탐지, PDF/Excel 리포트
- **PARTNER**
  - 입점 신청/상태 조회, 상품 등록 승인 플로우, 재고·매출 관리/리포트
  - 이벤트 신청, 키워드 트렌드 대응, 시간대별 판매 리포트

## 🔒 보안/비기능 요구사항
- 비밀번호 **bcrypt**, 민감정보 **AES-GCM**(DB)
- 관리자 페이지 **계정 기반 접근 제한**, 전 구간 **HTTPS**
- GitHub Actions로 **CI/CD**, Vultr VPS 배포, PostgreSQL 사용

## 🚀 로컬 개발
```bash
# 1) 프론트(스토어)
cd apps/web-storefront
npm i && npm run dev

# 2) 프론트(관리자/파트너)
cd ../web-admin
npm i && npm run dev

# 3) 백엔드(Spring)
cd ../../apps/svc-order
./gradlew bootRun

# 4) AI 서비스(Python)
cd ../svc-ai
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python manage.py runserver
