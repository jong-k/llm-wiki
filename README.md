# LLM Wiki

> 참고: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

선별한 원천 자료를 바탕으로 LLM이 유지하는 위키를 만들기 위한 재사용 가능한 템플릿.

이 프로젝트는 `docs/llm-wiki/idea.en.md`와 `docs/llm-wiki/idea.ko.md`에 설명된 패턴을 따른다. 원시 자료는 불변으로 두고, LLM이 구조화된 마크다운 위키를 유지하게 하며, `AGENTS.md`를 운영 스키마로 사용한다.

## 구조

```text
.
├── AGENTS.md
├── docs/
├── raw/
│   ├── sources/
│   └── assets/
├── wiki/
│   ├── index.md
│   ├── log.md
│   ├── overview.md
│   ├── sources/
│   ├── entities/
│   ├── concepts/
│   ├── syntheses/
│   ├── questions/
│   └── _templates/
└── tools/
```

## 빠른 시작

1. 원천 문서를 `raw/sources/`에 추가한다.
2. LLM 에이전트에게 `AGENTS.md`를 기준으로 원천 자료를 수집하라고 요청한다.
3. 생성된 위키를 `wiki/index.md`에서 탐색한다.
4. 오래 보존할 분석은 `wiki/syntheses/` 또는 `wiki/questions/`에 남긴다.

`raw/`는 사용자가 제공한 원천 자료를 위한 공간이다. `wiki/`는 LLM이 유지하는 지식을 위한 공간이다. `tools/`는 선택 사항이며, 검색이나 자동화가 필요해질 때까지 비워둬도 된다.

## 다른 프로젝트에 적용하기

다른 프로젝트에서 이 템플릿을 사용하려면 아래 파일과 폴더를 프로젝트 루트로 복사한다.

```text
README.md
AGENTS.md
raw/
tools/
wiki/
```

`docs/`는 이 템플릿의 배경과 참고 자료이므로 복사 세트에는 포함하지 않는다. 복사한 뒤에는 대상 프로젝트에 맞게 `README.md`와 `AGENTS.md`를 먼저 수정한다. 예를 들어 Next.js 프로젝트라면 `raw/sources/`에는 기획서, API 문서, 디자인 문서, 회의록을 넣고, `wiki/concepts/`에는 라우팅, 인증, 상태 관리, 디자인 시스템 같은 개념을 정리하면 된다.
