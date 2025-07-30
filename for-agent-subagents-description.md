# 서브에이전트 역할 설명

Claude Code가 참조할 서브에이전트들의 역할과 활용 방법.

## Python 서브에이전트

### python-programmer
역할: Python 코드 작성 및 구현
활용: 새로운 기능 구현, 버그 수정, 코드 개선이 필요할 때
특징: 코딩프로토콜에 따라 일관된 코드 작성

### python-testbuilder  
역할: Python 테스트 코드 작성
활용: 특정 클래스/모듈에 대한 테스트가 필요할 때
특징: 외부 의존성 분석 후 체계적인 테스트 작성

### python-reviewer
역할: Python 코드 품질 검증 및 개선 제안
활용: 코드 리뷰가 필요하거나 품질 개선을 원할 때
특징: 컨텍스트 분석 후 실용적 개선안 제시

### python-documenter
역할: Python 모듈 기술 문서 작성
활용: API 문서, 사용 가이드 작성이 필요할 때
특징: 다른 AI 에이전트를 위한 빠른 시그니처 레퍼런스 문서 작성

## 서브에이전트 선택 가이드

### 개발 단계별 활용
1. 새 기능 개발: programmer → testbuilder → tester → reviewer → documenter
2. 버그 수정: tester (원인 분석) → programmer (수정) → tester (재검증)
3. 코드 개선: reviewer (문제점 파악) → programmer (개선) → tester (검증)
4. 문서 정비: documenter

### 문제 해결별 활용
- 코딩 오류: programmer에게 수정 요청
- 테스트 오류: testbuilder에게 수정 요청
- 설계 충돌: Claude Code가 직접 판단 후 적절한 에이전트 활용
- 품질 개선: reviewer → programmer 순서로 활용

## 주의사항
- 각 서브에이전트는 독립적으로 작업하며 서로를 직접 호출하지 않음
- 모든 협업은 Claude Code를 통해 이루어짐
- 서브에이전트들의 완료 보고는 간소화되어 있어 결과물 확인 필요