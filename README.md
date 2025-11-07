# 6주차 Spring Boot 백엔드 교육 커리큘럼

## 전체 목표
- 백엔드 개발의 전체적인 이해
- Java Spring Boot 기반 REST API 개발 능력 습득
- Git 협업 플로우 체득
- 간단한 POC 결과물 완성 (Postman 테스트 가능)
- 시큐어 코딩 기본 원칙 이해 및 적용

---

## **1주차: 개발 환경 세팅 & 개발 기초**

### 학습 목표
- 개발 환경 구축 및 도구 사용법 이해
- Java 기본 문법 및 OOP 개념 학습
- Git/GitHub 기본 워크플로 체득

### Task 목록
1. **환경 세팅**
   - JDK 21, IntelliJ Community Edition 설치
   - Git, Postman 설치 및 설정
   - GitHub 계정 생성 및 SSH/Token 인증 설정

2. **Java 기초 학습**
   - 자료형, 변수, 제어문(if, for, while)
   - 클래스, 객체, 메서드 개념
   - 패키지와 접근 제어자 이해

3. **Git 워크플로 실습**
   - Git 기본 명령어 (init, clone, add, commit, push, pull)
   - 브랜치 생성 및 전환
   - GitHub에 코드 푸시하기
   - Pull Request 생성 및 리뷰 경험

---

## **2주차: Spring Boot 기초 & REST API 입문**

### 학습 목표
- Spring Boot 프로젝트 구조 이해
- DI/IoC 개념 학습
- 첫 REST API 작성 및 테스트

### Task 목록
1. **Spring Boot 프로젝트 생성**
   - Spring Initializr로 프로젝트 생성
   - IntelliJ 빌드 시스템 이해 (선택: Gradle/Maven 개념 소개)
   - 프로젝트 구조 파악 (src/main/java, resources)

2. **Spring 핵심 개념**
   - DI(Dependency Injection) 이해
   - IoC(Inversion of Control) 개념
   - 어노테이션 기본 (@Component, @Service, @RestController)

3. **첫 REST API 작성**
   - Controller 작성 (GET /health, GET /hello)
   - ResponseEntity 사용법
   - Postman으로 API 테스트

4. **계층 구조 이해**
   - Controller - Service - Repository 패턴
   - DTO(Data Transfer Object) 개념

---

## **3주차: 토이 프로젝트 개발 #1 - CRUD 구현**

### 학습 목표
- Spring Data JPA 기초
- 데이터베이스 연동 (H2)
- CRUD API 완성

### Task 목록
1. **데이터 계층 구현**
   - H2 Database 설정
   - JPA Entity 작성 (@Entity, @Id, @GeneratedValue)
   - Repository 인터페이스 작성 (JpaRepository)

2. **Member CRUD API**
   - POST /members (멤버 등록)
   - GET /members (목록 조회)
   - GET /members/{id} (상세 조회)
   - PUT /members/{id} (수정)
   - DELETE /members/{id} (삭제)

3. **Session CRUD API**
   - 주차별 세션 정보 관리
   - POST /sessions, GET /sessions, GET /sessions/{id}
   - Session과 Member 관계 설정

4. **유효성 검증**
   - @Valid, @NotNull, @Size 등 검증 어노테이션
   - MethodArgumentNotValidException 처리

---

## **4주차: 토이 프로젝트 개발 #2 - 비즈니스 로직 & 예외 처리**

### 학습 목표
- 복잡한 비즈니스 로직 구현
- 전역 예외 처리
- 엔티티 간 관계 매핑

### Task 목록
1. **Submission(과제 제출) 기능 구현**
   - Submission 엔티티 설계 (Member-Session 관계)
   - POST /submissions (과제 제출)
   - GET /submissions?memberId={id} (필터링 조회)
   - 제출 기한 체크 로직 구현

2. **비즈니스 로직 강화**
   - 출석 상태 관리
   - 과제 제출 상태 추적
   - 주차별 리포트 API (GET /reports/week/{no})

3. **예외 처리 & 응답 표준화**
   - @ControllerAdvice로 전역 예외 처리
   - 커스텀 예외 클래스 작성
   - 일관된 에러 응답 포맷 (ErrorResponse DTO)

4. **로깅**
   - SLF4J + Logback 사용
   - 요청/응답 로깅
   - 에러 로그 기록

---

## **5주차: 토이 프로젝트 개발 #3 - 품질 향상 & 문서화**

### 학습 목표
- 단위 테스트 작성
- API 문서 자동화
- 코드 리팩토링

### Task 목록
1. **테스트 작성**
   - JUnit 5 기초
   - Service 계층 단위 테스트
   - MockMvc를 이용한 Controller 테스트
   - @WebMvcTest, @DataJpaTest 활용

2. **API 문서화**
   - Swagger/SpringDoc 설정
   - API 문서 자동 생성
   - Swagger UI로 테스트

3. **코드 품질 개선**
   - 리팩토링 (중복 코드 제거, 메서드 분리)
   - 코드 컨벤션 적용
   - SonarLint 같은 정적 분석 도구 사용 (선택)

4. **배포 준비**
   - application.yml 프로파일 설정 (dev, prod)
   - 환경 변수 관리
   - JAR 빌드 및 실행

---

## **6주차: 시큐어 코딩 & 최종 마무리**

### 학습 목표
- 보안 취약점 이해 및 방어 기법
- OWASP Top 10 주요 항목 학습
- 최종 데모 준비

### Task 목록
1. **시큐어 코딩 기초**
   - **SQL Injection 방어**
     - JPA/JPQL 파라미터 바인딩 확인
     - Native Query 사용 시 주의사항

   - **XSS(Cross-Site Scripting) 방어**
     - 입력값 검증 및 이스케이핑
     - Content-Type 헤더 설정

   - **인증/인가 기초**
     - Spring Security 간단 적용 (선택)
     - API Key 방식 인증 구현 (기본)

   - **민감 정보 보호**
     - 환경 변수로 DB 정보 관리
     - 로그에 민감 정보 노출 방지

   - **CORS 설정**
     - 허용 도메인 설정
     - 안전한 CORS 정책

2. **보안 점검**
   - 모든 입력값 검증 확인
   - 에러 메시지에 민감 정보 노출 여부 체크
   - 의존성 취약점 점검 (OWASP Dependency Check 선택)

3. **최종 통합 & 버그 픽스**
   - 전체 API 통합 테스트
   - 발견된 버그 수정
   - 성능 점검 (N+1 쿼리 등)

4. **데모 준비**
   - Postman 시나리오 작성
   - 발표 자료 준비 (아키텍처, 주요 기능, 회고)
   - 실행 가이드 문서화

---

## 추천 토이 프로젝트: Study Tracker API

### 핵심 기능
1. **멤버 관리** - 스터디원 정보 등록/조회/수정/삭제
2. **세션 관리** - 주차별 학습 주제 및 과제 관리
3. **과제 제출** - 멤버별 과제 제출 상태 추적
4. **리포트** - 주차별 출석/제출 현황 요약

### 기술 스택
- **Language**: Java 21
- **Framework**: Spring Boot 3.x
- **Database**: H2 (개발), MySQL (선택)
- **ORM**: Spring Data JPA
- **Build**: IntelliJ
- **Documentation**: Swagger/SpringDoc
- **Testing**: JUnit 5, MockMvc

> **참고**: 실무에서는 Gradle이나 Maven 같은 빌드 도구를 주로 사용하지만, 학습 단계에서는 IntelliJ 빌드 시스템을 사용하여 빌드 설정보다 Java와 Spring Boot 개념 학습에 집중합니다.

### 주요 엔티티 설계

```java
// Member: 스터디원 정보
- id: Long
- name: String
- email: String
- role: String (MENTOR, MENTEE)
- createdAt: LocalDateTime

// Session: 주차별 세션 정보
- id: Long
- weekNumber: Integer
- title: String
- description: String
- dueDate: LocalDate
- createdAt: LocalDateTime

// Submission: 과제 제출
- id: Long
- memberId: Long
- sessionId: Long
- submittedAt: LocalDateTime
- githubUrl: String
- status: String (SUBMITTED, LATE, MISSING)
- comment: String
```

### API 엔드포인트 예시

```
# Member
GET    /api/members           - 멤버 목록
GET    /api/members/{id}      - 멤버 상세
POST   /api/members           - 멤버 등록
PUT    /api/members/{id}      - 멤버 수정
DELETE /api/members/{id}      - 멤버 삭제

# Session
GET    /api/sessions          - 세션 목록
GET    /api/sessions/{id}     - 세션 상세
POST   /api/sessions          - 세션 생성
PUT    /api/sessions/{id}     - 세션 수정
DELETE /api/sessions/{id}     - 세션 삭제

# Submission
GET    /api/submissions                    - 제출 목록
GET    /api/submissions?memberId={id}      - 멤버별 제출 내역
POST   /api/submissions                    - 과제 제출
PUT    /api/submissions/{id}               - 제출 수정
DELETE /api/submissions/{id}               - 제출 삭제

# Report
GET    /api/reports/week/{weekNumber}      - 주차별 리포트
GET    /api/reports/member/{memberId}      - 멤버별 통계
```

---

## 운영 방식

### 주간 일정
- **오프라인 세션**: 주 1회 
- **온라인 Q&A**: 카카오톡 상시 운영
- **과제 제출**: 세션 이후 5일 이내

### 협업 도구
- **GitHub**: 코드 관리, PR, Issue 트래킹
- **Notion**: 태스크 보드 (TODO → In Progress → Review → Done)
- **Postman**: API 테스트 및 문서화

### Git 브랜치 전략
- `main`: 배포용 (보호 브랜치)
- `develop`: 개발 통합 브랜치
- `feature/*`: 기능 개발 브랜치
- PR 규칙: 최소 1명 리뷰 후 머지