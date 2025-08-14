# Go 언어 개요

Go(골랭)는 Google이 개발한 **컴파일 언어**로, 간결한 문법과 빠른 빌드, **병행성(concurrency)** 지원이 특징입니다.

## 왜 Go인가?
- **단순함**: 문법이 작고 읽기 쉬움, `go fmt`로 일관된 스타일
- **병행 처리**: `goroutine`과 `channel`로 고성능 동시성 처리
- **단일 바이너리**: 의존성 포함한 실행 파일 생성(배포 단순)
- **크로스 컴파일**: 다양한 OS/아키텍처로 빌드 가능

## 주요 특징 (요약 표)
| 특징 | 설명 |
|---|---|
| 빠른 컴파일 | 큰 프로젝트에서도 빠른 빌드 |
| 가비지 컬렉션 | 자동 메모리 관리 |
| 병행성 | goroutine, channel |
| 표준 라이브러리 | 네트워크/HTTP/테스트 등 충실 |
| 툴링 | `go test`, `go mod`, `go vet`, `go fmt` |

## 예시: 가장 작은 HTTP 서버
```go
package main

import (
  "fmt"
  "net/http"
)

func main() {
  http.HandleFunc("/healthz", func(w http.ResponseWriter, r *http.Request) {
    fmt.Fprint(w, "ok")
  })
  http.ListenAndServe(":8080", nil)
}
```

## 다음에 볼 것
- 패키지/모듈(`go mod`), 오류 처리, 테스트(`go test`), 컨텍스트(context)
