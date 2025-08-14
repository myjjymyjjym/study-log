# study-log (Starter)

개인 학습 노트를 정리하기 위한 기본 템플릿입니다. 폴더는 주제 → 하위주제 → 노트 형태로 구성합니다.

```
topics/
  language/
    go/
      notes/
        go-intro.md
  infra/
    docker/
      notes/
        docker-intro.md
assets/
  images/          # 노트에 넣을 스크린샷/그림
_snippets/
  markdown-cheatsheet.md
```

## 사용법
1. 이 레포를 GitHub에서 새로 만들거나(clone) 복사하세요.
2. `topics/` 아래에 폴더와 `.md` 파일을 추가해가며 기록합니다.
3. 이미지는 `assets/images/`에 넣고 상대경로로 링크합니다:
   `![설명](../../../assets/images/example.png)`
4. 커밋 메시지 예시:
   - `docs(go): add go routines note`
   - `docs(docker): update compose section`
   - `chore: reorganize folders`

Tip: JetBrains(GoLand/PhpStorm)나 VS Code의 Markdown 미리보기로 확인하면서 편집하세요.
