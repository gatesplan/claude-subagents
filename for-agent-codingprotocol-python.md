# Python Coding Protocol for Agent
- 이 문서는 에이전트의 원활하고 균일한 Python 코딩을 위한 프로토콜이다.
- 모든 에이전트는 Python 언어 사용시 이 코딩 프로토콜을 준수해야 한다.
- 이 파일은 루트 폴더의 중앙 지침이므로 에이전트는 절대 이 파일을 수정하지 않는다.

## 중요 규칙
- 하나의 파일은 오직 하나의 함수 또는 하나의 클래스만 포함한다.

## 클래스 디렉토리 및 코드 작성 규칙
- 모듈 클래스의 파일명과 클래스명은 CamelCase로 작성한다.
- 예외 클래스는 책임 모듈 폴더 아래에 위치한다.
- 클래스는 항상 단일 책임 원칙을 따른다.
- 각 클래스는 항상 다음 디렉토리 구조를 따른다.
```
└─ClassName  # CamelCase
    └─tests  # tests folder
    └─__init__.py
    └─for-agent-moduleinfo.md
    └─ExceptionNo1.py
    └─ExceptionNo2.py
    └─ClassName.py
    └─SubClassIfNeeded.md
```
