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

## 4. 트러블 슈팅

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

## 5. QA 테스트

- **애플리케이션 테스트 수행 능력단위**에서 배운 내용을 토대로 QA 테스트 문서를 작성, 수행했다.

<img width="1492" height="505" alt="image" src="https://github.com/user-attachments/assets/55ff60f2-4b0f-4c6b-814d-d3694332a70d" />

## 6. 앱 전환-Web View

- **통합 구현 능력단위**에서 배운 react-native 기술을 활용하여 미디어 쿼리로 모바일 화면을 구축하였다.

<img width="1179" height="2556" alt="image" src="https://github.com/user-attachments/assets/7e6d38ca-fb23-4517-a253-92773deebe8d" />

<img width="1179" height="2556" alt="image" src="https://github.com/user-attachments/assets/399899d1-9bfa-4fb0-9c48-394e0249e0d0" />

## 7. 인프라 구축 구분

(예정)

## 8. 느낀 점

### 기획: 탄탄한 기획이 순조로운 작업으로 이어진다!

이번 프로젝트를 통해 기획이 단순한 시작점이 아니라, 전체 개발 흐름을 좌우하는 핵심이라는 점을 깊이 체감했다. 단순히 기능을 나열하는 것이 아닌, 사용자와 기업 양측의 니즈를 면밀히 분석하고 이를 서비스 구조에 녹여내는 과정이 매우 중요했다. 특히 ‘체험을 통해 인턴으로 이어지는 구조’는 구직자에게는 실질적인 기회를 제공하고, 기업에게는 인력 공백을 최소화할 수 있는 현실적인 솔루션이 될 수 있다는 점에서 설득력 있는 기획이라고 느꼈다. 이러한 구조는 단순한 채용 플랫폼을 넘어, 양측의 문제를 동시에 해결하는 연결고리 역할을 하도록 설계되었다.

기획 단계에서 충분한 고민과 시뮬레이션이 이루어졌기 때문에, 개발 중에도 방향성을 잃지 않고 일관된 결과물을 만들 수 있었다. 실제 기능을 구현하면서도 기획 의도를 되새기며 사용자 경험을 고려한 로직을 설계하려 노력했고, 이는 서비스 완성도 향상으로 이어졌다. 이번 경험을 통해 기획은 단순한 문서 작업이 아니라, 개발자에게도 깊은 이해와 공감이 필요한 과정이라는 점을 배웠다. 앞으로도 사용자 중심의 사고를 바탕으로 기획과 개발을 유기적으로 연결하는 능력을 키워나가고 싶다.

### 협업: 슬랙 중심의 유연한 커뮤니케이션

이번 프로젝트에서는 슬랙을 중심으로 한 실시간 커뮤니케이션이 협업의 핵심 역할을 했다. 개발 중 발생하는 이슈나 변경 사항을 빠르게 공유하고, 기능별로 스레드를 나누어 논의함으로써 혼선 없이 작업을 이어갈 수 있었다. 특히 슬랙과 GitHub를 연동해 코드 리뷰, 병합 요청, 이슈 트래킹 등을 자동화하면서 협업의 흐름을 끊김 없이 유지할 수 있었다. 회의 없이도 팀원 간의 의사소통이 원활하게 이루어졌고, 이는 개발 속도와 품질 모두에 긍정적인 영향을 주었다.

또한 슬랙을 통해 각자의 작업 상황을 투명하게 공유하고, 필요한 경우 즉시 피드백을 주고받을 수 있었기 때문에, 물리적으로 떨어져 있어도 마치 한 공간에서 함께 일하는 듯한 협업 환경이 조성되었다. 이러한 경험을 통해 도구를 잘 활용한 커뮤니케이션이 팀워크를 강화하고, 프로젝트의 완성도를 높이는 데 얼마나 중요한지를 실감할 수 있었다.

### 총평: 실전 경험이 만든 성장의 발판

이번 프로젝트는 단순한 기능 구현을 넘어, 백엔드 개발자로서의 실전 역량을 한층 끌어올릴 수 있었던 소중한 경험이었다. 도메인 중심 설계(DDD)와 RESTful API 설계, 그리고 보안과 성능을 고려한 구조 설계까지, 실제 서비스 환경에서 요구되는 다양한 요소들을 직접 다뤄볼 수 있었다. 특히 유지 보수를 고려해 용도별로 간결하고 정갈하게 코드를 작성하는 것이 얼마나 중요한지 체감했고, 이는 장기적인 서비스 운영에 있어 핵심적인 요소임을 깨달았다.

또한 사용자 중심의 기능을 개발하면서 단순한 CRUD를 넘어서, 실제 서비스에서 발생할 수 있는 다양한 예외 상황과 디테일한 로직을 다루는 능력이 향상되었다고 느낀다. 예를 들어 공고 필터링이나 파일 업로드 같은 기능은 단순해 보이지만, 실제 구현 과정에서는 복잡한 조건과 예외 처리가 필요했고, 이를 해결하면서 문제 해결 능력도 함께 성장할 수 있었다.

기술적인 성장에 더해 서비스 전체를 바라보는 시야와 협업을 통한 문제 해결 능력까지 함께 키워준 값진 경험이었다. 앞으로도 더 많은 실전 프로젝트를 통해 백엔드 개발자로서의 깊이와 넓이를 동시에 확장해 나가고 싶다.


