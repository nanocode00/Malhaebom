# 말해봄 Mk.2 — 모델 평가와 검증 한계

## LLM 후보 평가

- **40종** OpenRouter 모델 사전 검증
- **22종 × 30건 = 660건** 합성 시나리오 기반 본평가
- 별도 최종 후보 **4종 × 30건 = 120건** 비교

판단 축은 구조화 출력 계약 준수, 지연, 비용, 서비스 인터페이스 호환성이었습니다. 합성 30건의 성적은 **독립적 사람 평가, 실제 사용자 만족도, 운영 환경 전체 E2E 품질의 대체 지표가 아닙니다.**

## STT 도메인 적응 실험

Whisper Medium QLoRA 후보 C2 기록:

| 평가 | 결과 |
|---|---|
| 면접 도메인 1,233건 | WER **9.77%** |
| 기존 도메인 119건 — 적응 전 | WER **15.33%** |
| 기존 도메인 119건 — 적응 후 | WER **16.81%** |

새로운 면접 도메인 결과만으로 모델의 전반적 성능이 좋아졌다고 주장하지 않습니다. 기존 도메인 유지 성능은 **악화**되었고, 서비스 운영 모델의 전면 교체 성공도 입증하지 않았습니다.

## Agent·CI 관련 검증

- FastMCP/인증/DB 저장 경로의 검증 및 과거 DB 행 오판 결함 발견
- PR 정책 검사에서 최신 HEAD와 검사 시점의 경합 문제 개선
- 초기 Backend/Frontend GitHub Actions CI 체크 통과 확인

이 기록은 전체 인증·OAuth→음성녹음→코칭→저장·조회 사용자 시나리오의 독립 평가 완료나 장기 운영 안정성을 뜻하지 않습니다.

## 근거

[프로젝트 경험 기록](https://github.com/nanocode00/resume/blob/main/experiences/malhaebom.md) · [작업군별 검증 원장](https://github.com/nanocode00/resume/blob/main/experiences/malhaebom-rework-checkpoint.md)
