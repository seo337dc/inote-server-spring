# inote-server-spring

> `inote-money`의 BE 도메인을 Spring Boot로 재구현하는 학습/포트폴리오용 프로젝트.
> 기존 프로덕션 BE인 [`inote-server`](https://github.com/seo337dc/inote-server)(NestJS)는 레거시로 그대로 유지 — 이 레포는 완전히 별도.

---

## 목적

- Java/Spring 학습 로드맵의 실전 프로젝트 단계 ([career-notes](https://github.com/seo337dc/career-notes) 참고)
- 새 토이 프로젝트 대신, 이미 도메인·스키마·API를 아는 `inote-money`의 BE 모듈을 Spring으로 포팅해 학습 효율을 높임
- 목표: "동일 도메인을 NestJS와 Spring 양쪽으로 구현해보고 JPA vs Prisma, DI 컨테이너 차이를 직접 비교"할 수 있는 포트폴리오 근거 마련

## 상태

🚧 **착수 전** — Java 기본기 + Spring 핵심 원리 학습 완료 후 시작 예정

## 포팅 대상 후보

`inote-server`(NestJS) 기준 모듈 중 하나를 선정해 재구현:

- `money/stocks` — CRUD + 외부 API 연동, 적당한 복잡도
- `money/terms` + `money/books` — 좋아요 토글(unique 제약), JPA 연관관계 매핑 연습에 적합

## DB

기존 프로덕션 Neon(Prisma 관리 스키마)에 붙이지 않고, **별도 Neon 프로젝트/브랜치**를 새로 파서 사용한다. Hibernate `ddl-auto`가 Prisma 관리 스키마와 충돌하거나 운영 데이터를 건드릴 위험을 피하기 위함.

## 예정 스택

| 항목 | 기술 |
|------|------|
| 언어 | Java |
| 프레임워크 | Spring Boot |
| ORM | Spring Data JPA (+ QueryDSL 검토) |
| 빌드 도구 | Gradle |
| DB | PostgreSQL (Neon, 별도 프로젝트) |
| 인증 | Spring Security (JWT 또는 세션 — 검토 예정) |
| 테스트 | JUnit5 + Mockito |
