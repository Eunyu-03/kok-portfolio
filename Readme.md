# KOK - 청년과 기업을 연결하는 실무 중심 직업 체험 플랫폼

## 1. ERD 작성

### ERD

- **SQL 활용 능력단위**에서 배운 DML 문법으로 실제 데이터를 직접 insert, update, delete, select 하고 확인했습니다.
- **데이터베이스 구현 능력단위**에서 배운 테이블 간의 관계를 고려하여 ERD를 구성하였습니다.

<img width="9038" height="6284" alt="image" src="https://github.com/user-attachments/assets/96b929b1-6316-4b98-800d-e9f344d79501" />


## 2. UI/UX 화면 설계

### 벤치마킹 웹 사이트: 로켓펀치

- **화면 구현 능력단위**에서 배운 HTML, CSS, JS를 활용하여 로켓펀치 사이트를 클론 코딩하였습니다.
- JS로 유효성 검사 등 동적 이벤트를 추가했습니다.
&nbsp;

&nbsp;

&nbsp;
**예시 이미지**
&nbsp;

&nbsp;

&nbsp;
<img width="1915" height="905" alt="image" src="https://github.com/user-attachments/assets/ed63a61b-7445-456d-98ad-b5fa360a1394" />

<img width="1900" height="898" alt="image" src="https://github.com/user-attachments/assets/101a3970-53f5-4b2e-9400-eb4d056268be" />
&nbsp;

&nbsp;

&nbsp;
**클론 코딩**
&nbsp;

&nbsp;

&nbsp;
<img width="1917" height="902" alt="image" src="https://github.com/user-attachments/assets/1086ec91-eb68-4426-b54f-214ad340a764" />

<img width="1898" height="904" alt="image" src="https://github.com/user-attachments/assets/37b49627-dbbd-41ac-80b3-1c6ec4104004" />
&nbsp;

&nbsp;

&nbsp;

## 3. 담당 업무

### 1. 프론트엔드

- **통합 구현 능력단위**에서 배운 기술을 활용하여 화면을 구성하였다.

<img width="1527" height="550" alt="image" src="https://github.com/user-attachments/assets/ff688077-9f7b-4167-aefc-74efe623fcb0" />

기업 콘솔
- 기업 홈(공고와 광고 관련 정보 표시)
- 기업 프로필 편집
- 체험 공고 등록
- 체험 공고 목록
- 체험 공고 수정
- 인턴 공고 등록
- 인턴 공고 목록
- 인턴 공고 수정
- 새 광고
- 광고 목록
- 결제 내역

### 2. 백엔드

- **서버 프로그램 구현 능력단위**에서 배운 기술을 활용하여 백엔드 서버 구축에 Spring Boot를 이용하였다.

<img width="2381" height="375" alt="image" src="https://github.com/user-attachments/assets/6137c258-2264-4a06-8d6f-6c52f687c773" />
 
체험 공고
- 체험 공고 목록 불러오기
- 키워드와 카테고리 선택으로 체험 공고 목록 필터링
- 체험 공고 상세 불러오기
- 체험 공고 저장하기
- 체험 공고 공유하기(url 복사)
- 체험 간편 지원하기

인턴 공고
- 인턴 공고 목록 불러오기
- 키워드와 카테고리 선택으로 인턴 공고 목록 필터링
- 인턴 공고 상세 불러오기
- 인턴 공고 저장하기
- 인턴 공고 공유하기(url 복사)
- 인턴 간편 지원하기

마이페이지
- 프로필 편집(프로필 사진 변경, 이름 변경, 직군 카테고리 변경, 소개 변경)
- 내 게시글 목록(클릭 시 해당 게시글 상세로 이동)
- 저장한 체험 공고 목록(클릭 시 해당 공고 상세로 이동)
- 저장한 인턴 공고 목록(클릭 시 해당 공고 상세로 이동)
- 지원한 체험 공고
- 체험 공고 지원 취소
- 지원한 인턴 공고
- 인턴 공고 지원 취소
- 결제 내역 목록 불러오기
- 보관함에 이력서 파일 저장
- 보관함 이력서 파일 목록 불러오기
- 보관함에 저장된 이력서 파일 삭제

지원자 평가
- 체험 공고에 합격했고, 체험일이 지난 지원자 평가 남기기

## 6. 트러블 슈팅

### 오류 발생

프로필 업데이트 시 프로필 변경을 선택하지 않고 완료를 누르면 profile에 아무 파일도 들어오지 않아 profile이 null이 되어 NullPointerException이 터졌다.

#### <오류> - at com.example.kok.service.MemberServiceImpl.updateProfile(MemberServiceImpl.java:221)
<img width="2319" height="219" alt="image" src="https://github.com/user-attachments/assets/05a862fb-7cdb-47a9-ab70-cc075a8e222a" />

#### <이전 코드>
<img width="1142" height="1139" alt="image" src="https://github.com/user-attachments/assets/b1c29c39-c7df-4822-8f11-2b7ebb139e6b" />

### 해결

#### <수정된 코드>
<img width="1309" height="1252" alt="image" src="https://github.com/user-attachments/assets/1a142b88-636c-4670-b05d-d5dc4d3de55d" />

profile이 null이 아닐 경우에만 업데이트하도록 조건문을 걸어 프로필 변경을 선택하지 않으면 원래 프로필이 유지가 되도록 했다.

### 오류 발생

공고 상세 조회를 할 때 Redis에 chaching으로 experienceNoticeDTO를 키 값으로 담으려다 상세 페이지가 로딩되지 않는 오류가 생겼다.

#### <오류>
<img width="2311" height="330" alt="image" src="https://github.com/user-attachments/assets/cb32308d-62fb-4117-92eb-7006105da3c0" />

#### <이전 코드>
<img width="1022" height="715" alt="image" src="https://github.com/user-attachments/assets/6392669b-5d1d-404f-8319-86aae866b29a" />

### 해결

#### <수정된 코드>
<img width="982" height="787" alt="image" src="https://github.com/user-attachments/assets/433a7950-1083-4473-b125-e43d57e2f7e8" />

#### <Redis 키, 밸류>
<img width="368" height="84" alt="image" src="https://github.com/user-attachments/assets/ef596e7a-c7f0-476d-b717-cb4df1f2ea79" />

finNoticeById의 파라미터인 id로 키 값을 변경하였다. 그 결과 상세 페이지 로딩도 잘 되고 Redis에도 값이 잘 담기는 것을 확인할 수 있었다.

## 7. QA 테스트


