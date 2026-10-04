#학번/ 이름
22300161 김우성

##Key Learning

***AI 사용과 관련하여

    종류 - Gemini

    목적 - 회원 정보 수정할 때 배열 값 바꾸는 방법과 입력값 검사 조건 고치기

    사용한 것
    - 버튼을 눌렀을 때 입력창의 최신 값을 읽어와서 객체(updatedPerson)로 묶는 방법과 코드 위치 정리
    - 수정 버튼을 눌렀을 때 순번(isIteditingTheList)을 기억해 두고 splice()로 기존 배열 값을 교체하는 방법 적용
    - 수정이 끝난 뒤 상태 변수를 null로 되돌리고, 새 인원은 members.push()로 추가하는 분기 처리
    - 작업이 끝난 뒤 입력창들을 .value = ""로 비워주는 위치와 방법 정리
    - script 태그 실행 시점 문제 해결 및 오타 수정 (#addBtn 선택자, .value 누락, member/members 배열 이름 오타)
    - 이름 2글자 이상, 학번 범위, 출석 횟수 음수 검사 함수 작성과 부등호 방향 및 오타(.length, focus) 수정


    배운 것
    - 입력창의 값을 가져오거나 지울 때는 innerText가 아니라 .value를 써야 한다는 것을 배움
    - 화면을 직접 고치지 않고 배열 데이터를 먼저 바꾼 다음 render()를 실행하는 방식이 더 편하다는 것을 이해함
    - 검사 함수를 만들 때 통과할 값이 아니라 '잘못 입력된 값'을 찾아내야 경고창이 제대로 뜬다는 점을 배움


###Form Elements


####HTML vs CSS


#####Validation & JS


######JavaScript 처리 과정


#######Problem & Solution


########Reflection
