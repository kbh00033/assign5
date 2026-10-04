학번/ 이름
22300161 김우성

Key Learning
    데이터 중심 UI 렌더링: 화면의 DOM 요소를 직접 하나씩 수정하지 않고, 데이터 배열(members)을 먼저 변경한 뒤 render() 함수를 다시 실행하여 화면을 동기화하는 구조를 학습함.
    배열을 다루기 위해 사용하는 메서드(명령어)를 활용한 상태 조작: push()를 통한 추가, splice()를 통한 특정 데이터 수정, forEach()를 통해 배열을 순서대로 출력하는 방법을 학습함.
    입력 폼 제어 및 유효성 검증: input의 .value를 통해 실제 입력된 값에 접근하는 방법과, 올바른 데이터만 처리되도록 에러 조건을 검사하는 조건문 설계 방식을 학습함.


CRUD Service
    구현한 서비스 주제: HAC(한동 애니메이션 동아리) 회원 명단 관리 시스템
        이름 (name)
        학번 (studentId)
        별명 (nickName)
        출석 횟수 (attendence)
        전화번호 (phone)
    Create / Read / Update / Delete 구현 방법
        Create: 입력 창의 값들로 새 객체(updatedPerson)를 생성한 뒤 push()로 배열에 추가하고 render()로 배열을 다시 읽어 드림 
        Read: forEach()로 배열을 순회하며 createElement로 tr 태그를 생성해 tbody에 출력하는 render() 함수 실행
        Update: 수정 버튼 클릭 시 해당 번째 번호 값을 isIteditingTheList에 저장하고 입력창에 기존 값을 채움, 추가 버튼 클릭 시 members.splice(isIteditingTheList, 1, updatedPerson)로 기존 데이터를 교체하고 isIteditingTheList 값을 null로 초기화
        Delete : 삭제 버튼 클릭 시 confirm() 확인창을 거쳐 해당 행 요소를 members.splice()로 제거

AI 사용과 관련하여

    종류 
    - Gemini

    목적 
    - 회원 정보 수정할 때 배열 값 바꾸는 방법과 입력값 검사 조건 고치기

    사용한 것
    - 버튼을 눌렀을 때 입력창의 최신 값을 읽어와서 객체(updatedPerson)로 묶는 방법과 코드 위치 정리
    - 수정 버튼을 눌렀을 때 순번(isIteditingTheList)을 기억해 두고 splice()로 기존 배열 값을 교체하는 방법 적용
    - 수정이 끝난 뒤 순번 변수를 null로 되돌리고, 새 인원은 members.push()로 추가하는 if문에 관한 질문
    - 작업이 끝난 뒤 입력창들을 .value = ""로 비워주는 위치와 방법 정리
    - appendChild의 script 태그 실행 시점 문제 해결 
    - 학번 범위, 출석 횟수 음수 검사 함수 작성과 부등호 방향 및 오타(.length, focus) 수정


    배운 것
    - 입력창의 값을 가져오거나 지울 때는 innerText가 아니라 .value를 써야 한다는 것을 배움
    - 화면을 직접 고치지 않고 배열 데이터를 먼저 바꾼 다음 render()를 실행하는 방식이 더 편하다는 것을 이해함
    - 검사 함수를 만들 때 통과할 값이 아니라 '잘못 입력된 값'을 찾아내야 경고창이 제대로 뜬다는 점을 배움
    - appendChild를 거치지 않은 상태에서 찾는다면 해당값이 없어서 버그가 발생한다는 점을 배움

JavaScript
    document.createElement()
        설명: 화면에 새로 추가할 HTML 태그를 만드는 기능입니다.
        예시: document.createElement('tr')//tr태그를 생성
    appendChild()
        설명: 새로 만든 태그를 부모 태그의 맨 마지막 자식으로 쏙 붙여주는 기능입니다.
        예시: auto_add_theMemberList.appendChild(add_tag_tr)
    .trim()
        설명: input이 공백인지 체크하는 기능입니다
    alert()
        설명: 팝업 알림을 띄우는 기능입니다
    confirm()
        설명: 사용자에게 실행 여부를 묻는 기능입니다
        confirm("~하시겠습니까?");
    Array.prototype.forEach()
        설명: 배열 안의 데이터들을 처음부터 끝까지 하나씩 꺼내보며 같은 작업을 반복하는 기능입니다.
        예시: members.forEach(function(person, index) { ... });
    Array.prototype.splice()
        설명: ""배열""의 특정 위치에 있는 데이터를 지우거나, 다른 새 데이터로 바꿀 때 쓰는 기능입니다.
    .remove()
        설명: 화면에서 선택한 ""태그""를 삭제하는 기능이지만, 자바스크립트의 배열까지 삭제하지는 못 합니다
        예시: add_tag_tr.remove()
    Array.prototype.push()
        설명: 배열의 맨 끝에 새로운 데이터를 하나 덧붙여 넣는 기능입니다.
        예시: members.push(updatedPerson)

Problem & Solution
    문제: 한 번 수정한 후 새 회원을 추가하려 해도 계속 기존 수정 위치에 덮어써지는 현상 발생.
    해결: 수정 실행 후 isIteditingTheList = null;로 상태를 초기화하여 다음 입력 시 신규 추가할 지 혹은 기존 맴버를 수정할 지의 조건문에서 분기처리 가능하도록 처리함.
    
    문제: 등록 후 입력(input)창을 비우기 위해 innerText = ""를 사용했으나 입력값이 지워지지 않음.
    해결: innerText = ""에는 문제가 없었지만 input 태그는 닫는 태그가 없어 내용이 아닌 값을 다루어야 하므로 .value = ""로 수정하여 해결함.

Reflection
    새롭게 알게 된 점:
        - 자바 스크립트에는 다양한 매서드(명령어)들이 있으며 어떤 id나 class를 읽어 오면 해당 태그의 내용을 원하는 대로 바꿀 수 있다는 게 놀라웠음 
        - 선택한 태그를 화면에서만 삭제하는 기능은 remove()지만 배열의 특정 위치에 있는 데이터를 지우려면 splice()를 사용해야 한다는 것을 알게 됨

    궁금한 점:
        - 추가/수정된 명단이 유지되도록 백엔드와 연동하는 방법이 궁금함.
        - 브라우저를 새로 고침해도 명단이 초기화 되지 않게 하는 방법이 궁금함.