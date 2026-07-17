# 작업 기준 (WORKFLOW) v1.1 — 2026-07-17
확정: yh / GPT·Claude 교차 검수 반영

## 역할
- GitHub 저장소 = 단일 최신 원본
- GPT·Claude(채팅) = 읽기·검수·diff 제안만
- Claude Code = 유일한 writer, 승인된 수정만 반영
- yh = 최종 승인권자
- (예정) Hermes = 브랜치 생성→검수 취합→PR 생성→yh 승인 대기까지만.
  main 직접 자동 커밋 금지

## 승인 게이트
- 실행 게이트: 큐·핸드오프는 Claude Code 실행 전에 GPT·Claude 양측 합의와
  yh의 실행 승인을 받아야 한다.
- 병합 게이트: Claude Code 실행 후에는 실제 PR diff를 GPT·Claude 양측이
  검수하고, yh가 별도로 merge 승인한다.
- 사전 핸드오프 합의는 사후 PR diff 검수를 대체하지 않는다.
- 저장소 변경은 브랜치에서 수행하고 Pull Request로 제출한다.
  Claude Code는 main에 직접 커밋하지 않으며 merge를 수행하지 않는다.
  이견은 병합 전 브랜치에서 해소한다.
- 이 규칙은 본 public governance 저장소의 CONSTITUTION.md, WORKFLOW.md,
  reviews/ 및 수동 서명 governance 문서 변경에 적용한다.

## 링크 규칙
- 검수·검증 대상은 항상 커밋 고정 raw 링크로 지정한다.
- 검수 기록에 대상 커밋 해시 / 고정 링크 / 결과 / 반영 커밋을 남긴다.

## 문서 규칙
- git history(전체 기록)와 문서 내 변경 이력(버전 요약, D/S 상태)을 둘 다 유지한다.

## 저장소 구성
- 본 저장소(public) = governance 전용: CONSTITUTION.md, WORKFLOW.md, reviews/
- 코드·SPEC 상세·전략 파라미터·백테스트·운영 설정 = private 저장소(코드 착수 시 신설)
- 본 문서의 수정도 diff 제안 + yh 승인 절차를 따른다.

## 큐 형식
- V0.2 핸드오프 형식을 표준으로 한다:
  목적 / 전제 / 작업 / 금지 / 완료 조건(보고 파일 생성 포함) / 작업 원칙

## 보고
- 모든 작업 보고는 로컬 파일로 저장한다. 경로·양식은 로컬 규칙 파일에 정의하며
  저장소에는 기재하지 않는다.
- 보고 강제 3중: 로컬 규칙 파일 / 큐 완료 조건 / Stop hook
