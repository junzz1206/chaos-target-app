#  Chaos Target App (Source Code Repository)

이 레포지토리는 Google Online Boutique 마이크로서비스의 소스 코드(Source Code)와 빌드(CI)를 관리하는 공간입니다.

##  디렉토리 구조 및 역할
이 레포지토리에는 오직 애플리케이션 빌드에 필요한 파일만 업로드합니다.

```text
chaos-target-app/
├── .github/
│   └── workflows/
│       └── ci.yaml           # GitHub Actions CI 파이프라인 (빌드 & 이미지 푸시)
├── protos/                   # gRPC 프로토콜 버퍼 정의 파일
├── src/                      # 마이크로서비스 소스 코드 (Google Online Boutique 원본)
│   ├── adservice/
│   ├── cartservice/
│   │   ├── src/
│   │   └── Dockerfile        # 각 서비스별 도커 빌드 파일
│   ├── checkoutservice/
│   ├── frontend/
│   │   ├── templates/
│   │   ├── main.go
│   │   └── Dockerfile
│   └── ... (기타 서비스들)
└── README.md                 # 프로젝트 안내 및 빌드 가이드
```

주의: Kubernetes Manifest(YAML), Helm Chart, Ansible 파일은 이곳이 아닌
chaos-gitops-lab 레포지토리에 업로드하세요.

##  개발 규칙
1. Direct Push 금지: `main` 브랜치에 직접 Push 하지 않습니다. (PR 필수)
2. 빌드 검증: 소스 코드를 올리기 전, 로컬에서 `docker build`가 성공하는지 반드시 확인하세요.
