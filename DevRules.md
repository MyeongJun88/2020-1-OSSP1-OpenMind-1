# 2020-1-OSSP1-OpenMind-1
# 팀프로젝트 협업 규칙
___
## 1. 프로젝트 개발환경 세팅

### 1) 자료보관

Develop 브랜치에 올라간 이슈에 관련한 모든 자료는 깃헙에서 공유해야함   
데이터 셋이나 발표자료는 구글드라이브에서 공유   

### 2) 라이브러리

차후 추가 예정   

### 3) 개발환경

차후 추가 예정   


___
## 2. 깃헙 사용규칙

### 1) Commit 메세지 작성 방법

from http://blog.weirdx.io/post/33832

* 제목과 본문을 한 줄 띄워 분리하기
* 제목은 영문 기준 50자 이내로
* 제목 첫글자를 대문자로
* 제목 끝에 . 금지
* 제목은 명령조로
* 본문은 영문 기준 72자마다 줄 바꾸기
* 본문은 어떻게보다 무엇을, 왜에 맞춰 작성하기
### 2) Branch 이름

from https://gmlwjd9405.github.io/2018/05/11/types-of-git-branch.html

2. Develop branch
다음 출시 버전을 개발하는 브랜치 즉, 모든 기능이 추가되고 버그가 수정되어 배포 가능한 안정적인 상태라면 master 브랜치에 merge한다.   
평소 개발의 기준

3. Feature branch
새로운 기능 개발 및 버그 수정이 필요할 때마다 develop 브랜치로부터 분기한다. 로컬 저장소에서 관리한다.   
개발이 완료되면 develop 브랜치로 merge하여 공유한다. 
    1. develop 브랜치에서 새로운 feature 브랜치를 분기한다.
    2. 새로운 기능에 대한 작업을 수행한다.
    3. 작업이 끝나면 develop 브랜치로 병합한다.
    4. 더 이상 필요하지 않은 feature 브랜치는 삭제한다.
    5. 새로운 기능에 대한 feature 브랜치를 중앙 원격 저장소에 올린다(push)

* feature 브랜치 이름 기준
    * master, develop, release-(RB_), or hotfix- 제외
    * [feature/기능요약] 형식을 추천 EX) feature/login


### 3) 변수 작성 방법

변수는 한 목적으로만 사용하기   
변수는 항상 소문자로 시작하고, 다음 단어는 대문자로 구분하기   
함수의 매개변수 역시 그 의미를 명확히 표현하는 단어로 작성하기   

### 4) 함수 작성 방법

함수명은 항상 대문자로 시작하고, 다음단어는 대문자로 구분하기   
변수명과 함수명을 같게 하지 말기   
함수의 접두사 공통으로 사용하기 함수   

### 5) 버전 표기 기준

버전 x.y.z

* x: 기존 버전과 호환되지 않게 바뀔 시(대규모 업데이트)
* y: 기존 버전과 호환되면서 새로운 기능을 추가할 때


추후 추가되는 함수는 순차적으로 번호 부여   
* z: 기존 버전과 호환되면서 버그 수정했을 시
수정하지 않을 시: 0   
수정할 시: 1   
* 부가설명: 기여한 부분 설명
예) GetInput() 버그수정 및 새로운 기능(Enter를 누를 시 게임 일시정지) 추가. 기존 버전과 호환됨: 0.2.1-enter   


### 6) Merge 규칙

(1) Merge 확인 작업   
각자 맡은 코드 수정 후, Issue 표에 수정한 내용을 정리한다. 팀원은 Pull request에 있는 해당 Issue를 보고 피드백을 남긴다.(merge 찬성 혹은 개선 내용 추가)   

(2) Merge 결정 후   
Merge를 하기로 결정났으면 merge를 진행한다.   


### 7) Issue 규칙

한 기능 당 하나의 issue를 생성하여, 댓글을 통해 의견을 주고받는다.   

### 8) 문서화 규칙

수정할 곳에 관한 issue를 생성하여, 댓글을 통해 피드백을 남긴다.   

# Improve found open source code to clean code based on readability
___

* 전역변수의 사용 줄이기: 하나의 함수 내에서만 쓰이는 전역 변수를 해당 함수 내에 넣어주어 지역변수로 변환하여 준다.
* 같은 의미를 갖는 변수들 구조체로 선언하기: Xpos변수, Ypos변수, direction,lives, speed변수들은 모두 뱀과 관련한 변수들이기 때문에 Snake구조체를 만들어 묶어주고, 마찬가지로 Xfood변수와 Yfood 변수는 Food 구조체로 묶어준다.
* 하나의 함수에는 하나의 기능을 하도록 설계하기: main.c 코드의 DrawMap()함수에서는 맵을 그리는 기능과 더불어 사용자의 입력에 따른 위치 변화의 기능까지 포함하고 있기 때문에 각각의 기능을 다른 함수로 표현하여 준다.
* 매직넘버 사용하기: 매직넘버화를 통해 상수의 가독성을 높여준다.
* 조건식의 함수화: 조건식을 변수나 비교연산자로 표현하기 보단 함수로 표현하여 코드의 가독성을 높인다.
* 함수 분리: 조건식을 변수나 비교연산자로 표현하기 보단 함수로 표현하여 코드의 가독성을 높인다.


# Improve errors of found open source code

---
* 컴파일 환경 Warning Level 오류 개선: Warning Level을 최상으로 했을 때의 빌드 오류를 수정하여 준다.
* 조건문 else문 오류 개선: 조건문을 작성할 때 if문만 사용하고 else문을 써주지 않아 오류처리에 실패할 경우가 있기 때문에 항상 if문을 써주면 else문을 반드시 써서 오류처리를 해준다.
* 반복문 return 오류 개선: 조건문과 마찬가지로 반복문에서도 항상 return을 잘 활용하여 무한루프에 빠지지 않게 하고, 함수일 경우 return값을 잘 정의해 주어야 한다.
