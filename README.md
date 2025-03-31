# TimeTOGO-dev-env
# 🚌 TimeTOGO Dev Environment

로컬 개발 및 테스트를 위한 통합 Docker 환경입니다. 이 레포는 TimeTOGO의 프론트엔드와 백엔드를 컨테이너로 묶어 실행할 수 있도록 구성되어 있습니다.

---

## 📁 레포 구성 (3개)

### 1. `TimeTOGO-frontend`
- React Native 기반 모바일 앱
- 별도 레포로 존재 (이 레포에서 Submodule 또는 Clone)

### 2. `TimeTOGO-backend`
- Spring Boot + PostgreSQL 기반 API 서버
- TimescaleDB 사용

### 3. `TimeTOGO-dev-env` ← 현재 이 레포
- 위 두 레포를 통합 실행하는 `docker-compose.yml` 포함
- `.env`를 통해 DB 설정 및 포트 환경변수 관리

---

## 🔧 사용 전 준비사항

### 1. Submodule 또는 git clone 으로 FE/BE 연결
```bash
# 또는 git clone 으로도 가능
# frontend (React Native)
git submodule add https://github.com/your-org/TimeTOGO-frontend frontend

# backend (Spring Boot)
git submodule add https://github.com/your-org/TimeTOGO-backend backend
```

### 2. `.env` 파일 작성


---

## 🚀 실행 방법
```bash
docker-compose up --build
```

### 확인 URL
- 프론트엔드 (React Native 개발서버): http://localhost:8081
- 백엔드 (Spring Boot API): http://localhost:8080
- DB Admin (pgAdmin): http://localhost:5050

---

## 🧪 개발 흐름
1. FE, BE 각 레포에서 독립적으로 개발
2. 필요한 경우 이 `dev-env`에서 통합 테스트
3. ECS/Fargate 및 Cloud 배포는 각 레포 CI/CD에서 진행

---

## 📌 참고
- TimescaleDB는 PostgreSQL 확장입니다 (시계열 데이터 지원)
- Spring Boot 백엔드에서 Timescale을 일반 PostgreSQL처럼 연결하면 됩니다

---

## 🙌 협업 시
- FE/BE 팀은 각자 자기 레포에서 작업
- 로컬 통합 테스트 필요할 때 이 레포 clone 해서 사용하세요
