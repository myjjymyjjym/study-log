# Docker 기초

**Docker**는 애플리케이션을 **이미지**로 묶고, 이를 **컨테이너**로 실행하는 플랫폼입니다.

## 핵심 개념
- **이미지(Image)**: 실행 스냅샷(불변). `repo:tag`로 식별(예: `nginx:1.27`)
- **컨테이너(Container)**: 이미지를 실제로 실행한 인스턴스
- **레지스트리(Registry)**: 이미지를 저장/배포(Docker Hub, GHCR 등)
- **볼륨/네트워크**: 데이터 영속/컨테이너 간 통신

## 자주 쓰는 명령어
```bash
docker run --rm hello-world
docker pull redis:7
docker run --name r1 -d -p 6379:6379 redis:7

docker ps -a
docker logs r1 | tail
docker stop r1 && docker rm r1

docker build -t myapi:1.0 .
docker run --rm -p 8080:8080 myapi:1.0
```

## Dockerfile(멀티스테이지 예시)
```dockerfile
FROM golang:1.22 AS build
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -o server .

FROM gcr.io/distroless/static-debian12
COPY --from=build /app/server /server
EXPOSE 8080
ENTRYPOINT ["/server"]
```

## 다음에 볼 것
- docker-compose로 여러 컨테이너 묶기
- 이미지 최적화(레이어/캐시), 보안 스캔
