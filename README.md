# 말해봄 — AI 면접 코칭 팀 프로젝트 공개 소스 스냅샷

음성 면접 전사·증거 기반 LLM 코칭·피드백 기록 서비스의 **실제 소스 구조**를 유지한 개인 포트폴리오입니다.

- [개인 쇼케이스](https://nanocode00.github.io/malhaebom-showcase/)
- 핵심: backend/ FastAPI·코칭 런타임·MCP 연동, frontend/ React, mcp_server/, skills/, prompts/, supabase/
- 기여 범위: LLM 후보 평가, STT 도메인 적응, Agent/MCP 검증, 품질 게이트. **팀 전체 코드를 혼자 작성한 것은 아닙니다.**
- 실제 서비스 API 및 Supabase 인증정보는 포함하지 않습니다. GitHub Pages는 별도의 정적 쇼케이스입니다.

## 실행/검증 가이드

아래 명령은 **실행 방법 안내**이며, 새 공개 스냅샷에서 전부 통과했다고 주장하지 않습니다.
외부 STT/LLM 모델, GPU, 배포 인증정보와 제3자 데이터가 필요한 경로는 추가 설정이 필요합니다.

```bash
python -m pip install -r backend/requirements-ci.txt
python -m pytest backend/tests/test_coaching_validation.py -q
cd frontend && npm ci && npm run build
```

## 공개 범위

과거 Git 이력, 실제 키·서비스 운영 데이터, 원천 음성/라벨, 모델 가중치, 이용권이 명확하지 않은 평가 데이터, 개인 정보가 담긴 증거 및 generated artifact는 제외합니다.
이 저장소는 개인 포트폴리오 **소스 공개**이지 제3자 콘텐츠의 재배포 허가를 의미하지 않습니다.
코드 사용·배포 권리와 제3자 이미지/모델 라이선스는 각각 별도로 검토해야 합니다.

## 공개본 검증 기록 (2026-11-09)

- Python 소스 330개와 JSON 설정 22개가 구문 검사를 통과했습니다.
- 프런트엔드 npm ci 후 TypeScript 검사 및 Vite 프로덕션 빌드에 성공했습니다.
- Vitest 279개 중 275개 통과, 한글 글꼴 바이너리가 필요한 PDF 테스트 4개 조건부 제외입니다.
- 개인/팀 사용자 데이터·모델 가중치·음성 데이터·폰트 파일은 포함하지 않았습니다.
- FastAPI 백엔드 전체 pytest 및 외부 LLM/STT 통합 E2E는 미실행이며 재현을 보장하지 않습니다.
- 본인이 운영한 백엔드 주소가 없으므로 이전 팀 Cloud Run 주소는 기본값에서 제거했습니다.
