# MemberLiveInformationService 문서화

## 1. 서비스 개요
### 서비스 목적 및 책임
`MemberLiveInformationService`는 회원의 생활 정보를 관리하는 서비스입니다. 이 서비스는 회원과 관련된 생활 정보를 저장, 업데이트 및 조회하는 기능을 제공합니다.

### 주요 비즈니스 운영
- 회원의 생활 정보 저장
- 회원의 생활 정보 업데이트
- 특정 회원의 선택된 생활 정보 조회

### 공개 메서드 목록
- `saveAll(List<MemberLiveInformation> memberLiveInformations)`
- `updateMemberLiveInformation(long memberId, UpdateMemberLiveInformationRequest request)`
- `findMemberSelectedLiveInformation(Long memberId)`
- `findMemberLiveInfoIds(Long memberId)`

### 트랜잭션 요구 사항
- `updateMemberLiveInformation` 메서드는 트랜잭션을 필요로 하며, 데이터베이스의 일관성을 보장합니다.

### 일반적인 오류 시나리오 및 처리 방법
- 존재하지 않는 회원 조회 시 `NoExistMemberException` 발생
- 존재하지 않는 생활 정보 조회 시 `NoExistLiveInformationException` 발생

---

## 2. 비즈니스 로직 처리
### 2.1. saveAll 메서드
- **메서드 시그니처 및 목적**: 
  ```java
  public void saveAll(final List<MemberLiveInformation> memberLiveInformations)
  ```
  회원의 생활 정보를 저장합니다.

- **입력 매개변수 및 검증 규칙**: 
  - `memberLiveInformations`: 저장할 생활 정보 목록 (null 체크 필요)

- **예상 반환 값**: 
  - 없음 (void)

- **트랜잭션 경계 및 격리 수준**: 
  - 읽기 전용 트랜잭션

- **비즈니스 규칙 및 검증 로직**: 
  - 입력 값이 null이 아닌지 확인

- **오류 시나리오 및 처리 전략**: 
  - 입력 값이 null일 경우 예외 처리 필요

- **사용 예제**:
  ```java
  List<MemberLiveInformation> liveInfos = new ArrayList<>();
  memberLiveInformationService.saveAll(liveInfos);
  ```

### 2.2. updateMemberLiveInformation 메서드
- **메서드 시그니처 및 목적**: 
  ```java
  @Transactional
  public void updateMemberLiveInformation(final long memberId, final UpdateMemberLiveInformationRequest request)
  ```
  특정 회원의 생활 정보를 업데이트합니다.

- **입력 매개변수 및 검증 규칙**: 
  - `memberId`: 회원 ID (존재 여부 확인)
  - `request`: 업데이트 요청 (유효한 생활 정보 ID 목록 포함)

- **예상 반환 값**: 
  - 없음 (void)

- **트랜잭션 경계 및 격리 수준**: 
  - 트랜잭션 경계 내에서 실행

- **비즈니스 규칙 및 검증 로직**: 
  - 회원 ID가 존재하는지 확인
  - 요청된 생활 정보 ID가 유효한지 확인

- **오류 시나리오 및 처리 전략**: 
  - 존재하지 않는 회원 ID 또는 생활 정보 ID에 대한 예외 처리

- **사용 예제**:
  ```java
  UpdateMemberLiveInformationRequest request = new UpdateMemberLiveInformationRequest(...);
  memberLiveInformationService.updateMemberLiveInformation(memberId, request);
  ```

### 2.3. findMemberSelectedLiveInformation 메서드
- **메서드 시그니처 및 목적**: 
  ```java
  public FindMemberLiveInformationResponses findMemberSelectedLiveInformation(final Long memberId)
  ```
  특정 회원의 선택된 생활 정보를 조회합니다.

- **입력 매개변수 및 검증 규칙**: 
  - `memberId`: 회원 ID (존재 여부 확인)

- **예상 반환 값**: 
  - `FindMemberLiveInformationResponses`: 선택된 생활 정보 응답 객체

- **트랜잭션 경계 및 격리 수준**: 
  - 읽기 전용 트랜잭션

- **비즈니스 규칙 및 검증 로직**: 
  - 회원 ID가 존재하는지 확인

- **오류 시나리오 및 처리 전략**: 
  - 존재하지 않는 회원 ID에 대한 예외 처리

- **사용 예제**:
  ```java
  FindMemberLiveInformationResponses responses = memberLiveInformationService.findMemberSelectedLiveInformation(memberId);
  ```

### 2.4. findMemberLiveInfoIds 메서드
- **메서드 시그니처 및 목적**: 
  ```java
  public List<Long> findMemberLiveInfoIds(final Long memberId)
  ```
  특정 회원의 생활 정보 ID 목록을 조회합니다.

- **입력 매개변수 및 검증 규칙**: 
  - `memberId`: 회원 ID (존재 여부 확인)

- **예상 반환 값**: 
  - `List<Long>`: 회원의 생활 정보 ID 목록

- **트랜잭션 경계 및 격리 수준**: 
  - 읽기 전용 트랜잭션

- **비즈니스 규칙 및 검증 로직**: 
  - 회원 ID가 존재하는지 확인

- **오류 시나리오 및 처리 전략**: 
  - 존재하지 않는 회원 ID에 대한 예외 처리

- **사용 예제**:
  ```java
  List<Long> liveInfoIds = memberLiveInformationService.findMemberLiveInfoIds(memberId);
  ```

---

## 3. 상세 구성 요소 문서화
### a. 서비스 클래스
- **클래스 이름 및 비즈니스 목적**: 
  `MemberLiveInformationService`는 회원의 생활 정보를 관리하는 서비스입니다.

- **의존성 주입 및 자동 주입된 구성 요소**: 
  - `MemberLiveInformationRepository`
  - `LiveInformationRepository`
  - `MemberRepository`

- **트랜잭션 관리 구성**: 
  - `@Transactional` 어노테이션을 사용하여 트랜잭션을 관리합니다.

- **예외 처리 전략**: 
  - 사용자 정의 예외를 통해 오류를 처리합니다.

- **검증 접근 방식**: 
  - 메서드 내에서 입력 값 검증을 수행합니다.

### b. 비즈니스 DTOs
- **필드 설명 및 검증 제약 조건**: 
  - `UpdateMemberLiveInformationRequest`: 생활 정보 ID 목록을 포함합니다.
  
- **데이터 변환/매핑 로직**: 
  - DTO를 사용하여 요청 및 응답 객체를 변환합니다.

- **도메인 모델 관계**: 
  - `Member`, `LiveInformation`, `MemberLiveInformation` 간의 관계를 정의합니다.

---

## 4. 통합 지점
### 문서화된 상호작용
- **저장소 및 데이터베이스 작업**: 
  - `MemberLiveInformationRepository`, `LiveInformationRepository`, `MemberRepository`와 상호작용합니다.

- **다른 서비스**: 
  - 현재 다른 서비스와의 직접적인 상호작용은 없습니다.

- **외부 시스템**: 
  - 외부 시스템과의 통합은 현재 없습니다.

- **이벤트 게시/처리**: 
  - 이벤트 게시/처리는 현재 구현되어 있지 않습니다.

---

## 5. 구현 흐름
### 다이어그램
1. **구성 요소 다이어그램** (Mermaid)
   ```mermaid
   graph TD;
       A[MemberLiveInformationService] --> B[MemberLiveInformationRepository];
       A --> C[LiveInformationRepository];
       A --> D[MemberRepository];
   ```

2. **시퀀스 다이어그램** (Mermaid)
   ```mermaid
   sequenceDiagram
       participant M as Member
       participant S as MemberLiveInformationService
       participant R as MemberLiveInformationRepository
       M->>S: updateMemberLiveInformation(memberId, request)
       S->>R: deleteByMemberId(memberId)
       S->>R: saveAll(memberLiveInformations)
   ```

3. **상태 다이어그램** (Mermaid)
   ```mermaid
   stateDiagram-v2
       [*] --> Idle
       Idle --> Updating
       Updating --> Updated
       Updated --> [*]
   ```

---

## 6. 테스트 고려 사항
- **주요 테스트 시나리오**:
  - 존재하는 회원의 생활 정보 업데이트
  - 존재하지 않는 회원 ID로 업데이트 시도
  - 유효하지 않은 생활 정보 ID로 업데이트 시도

- **모킹 요구 사항**: 
  - `MemberLiveInformationRepository`, `LiveInformationRepository`, `MemberRepository`를 모킹하여 단위 테스트 수행

- **고려해야 할 중요한 비즈니스 엣지 케이스**: 
  - 회원이 없는 경우
  - 요청된 생활 정보 ID가 일부 또는 전부 존재하지 않는 경우

이 문서는 `MemberLiveInformationService`의 기능과 사용법을 명확하게 이해하는 데 도움이 됩니다.