### Python 이란?
- 바로가기
    - <a href="#python">파이썬이란?</a>
    - <a href="#pythonspec">파이썬의 종류</a>
    - <a href="#pythonversion">파이썬 버젼</a>
    - <a href="#pythongrammar">파이썬 문법</a>
    - <a href="#dataandoperator">파이썬 자료형 및 연산자</a>
    - <a href="#function">파이썬 함수</a>
    - <a href="#control">제어문</a>
    - <a href="#class">클래스</a>
    - <a href="#module">모듈</a>
    - <a href="#exception">예외처리</a>
    - <a href="#inputoutput">입출력</a>
    - <a href="#string">문자열 다루기</a>
    - <a href="#date">날짜 다루기</a>
    - <a href="#math">숫자 다루기</a>
    - <a href="#filesystem">파일 시스템</a>
    - <a href="#database">데이터베이스</a>
    - <a href="#os">운영체제 관련 기능</a>
    - <a href="#final">총 정리</a>

- <b id="python">파이썬</b>
    - 1991년 귀도 반 로썸이 발표
    - 특징
        - 가독성 높음(간결, 코드 block을 들여쓰기로 구분)
        - 풍부한 Library
        - 접착성 : 간단하게 library 추가, C로 구현된 부분 사용 가능
        - 무료
        - 유니코드 : 문자열 모두 유니코드
        - 동적타이핑 : 런타임 시에 타입 체크 하는 동적타이핑 지원, 메모리 관리 자동
- <b id="pythonspec">파이썬의 종류</b>
    - Cpython
        - C로 구성된 Python
    - Jython
        - 자바로 구성된 Python
        - 자바 가상 머신에서 구동 가능
        - 자바 library를 지원함
    - IronPython
        - .NET용으로 C#으로 구현된 Python
    - Pypy
        - Python 으로 구현된 Python
- <b>파이썬으로 진행된 Project</b>
    - ![Alt Text](./image/PythonProject.png)
- <b id="pythonversion">파이썬의 Version</b>
    - 2.x style
        - print
            - ex) print "welcome to", ---
        - int/int가 int의 결과로 반영되었음
        - String, Unicode로 구분
    - 3.x style
        - 2 version과의 호환성이 전혀 없음
        - print가 함수형태로 변경
            - ex) print("welcome")
        - long 자료형이 없어지고 int형으로 통일
        - int/int의 결과가 float으로 처리됨.
        - String / bytes로 구분(Unicode를 따로 지정하지 않고 일반 String이 기존 Unicode)
- <b id="pythongrammar">파이썬의 문법</b>
    - 들여쓰기(indentation)
        - 가독성을 높일 수 있음. 그러나 오류가 발생하지 않도록 주의
        - 예약어 아래에 같은 구문 시, 예약어 뒤에 (:) 사용하여 구분
            - <pre><code>for i in Python: 
                &#32; &#32;print(i)
              </code></pre>
    - 주석(#)
        - ```-*- coding: utf-8-*-```
        - 위와 같이 사용 시, 소스코드 인코딩 지정하는 용도로 사용
    - 세미콜론(;)
        - 한 line에 복수의 구문 시 사용. 
            - ```a=1; b=2```
- <b id="dataandoperator">자료형과 연산자</b>
    - 자료형?
        - 프로그램이 연산을 수행하기 위해 임시로 저장한 저장소를 변수라고 하며 이 변수의 유형이 자료형
        - 수치형, 문자형, 리스트형, 튜플형, 사전(Dictionary)형, 부울형이 있다.
        - 변수?
            - 문자 / 숫자 / 밑줄(_)로 구성되며 예약어는 사용 불가하고, 대소문자를 구분하며 숫자를 먼저 대어 이름을 지을 수 없다.
        - 수치형
            - int와 float, complex가 있으며 int는 정수, float는 소수
            - int는 숫자 앞에 0x는 16진수, 0o는 8진수, 0b는 2진수이다.
            - float는 3.14또는 314e-2 지수형으로 표현할 수 있다.
            - complex는 복소수이며 imag는 허수부, real은 실수부, conjugate()는 켤레 복소수를 나타낸다.
        - 문자형
            - '', "", """ """ 등으로 사용 가능하며 기본적으로 유니코드이다. 유니코드 이외의 인코딩 시 bytes로 표현된다.
                - <pre><code>type('가'.encode('utf-8'))</code></pre>의 class type은 bytes이다.
            - Escape 문자 사용하여 표현 가능
                - ![Alt Text](./image/pythonEscape.png)
            - +를 통해 문자열을 잇거나 *를 통해 반복화할 수 있다.
            - 인덱싱, 슬라이싱 또한 가능하다.
                - 'python'[0], 'python'[5], 'python'[1:4], 'python'[-2:] 등을 통해 특정 부분을 나타낼 수 있다.
        - 리스트형
            - 값의 나열과 같으며, 인덱싱, 슬라이싱이 가능하다.
            - 예) ['red', 'green', 'gold', 'black']
            - 특정 index에 추가하거나 확장할 수 있다.(insert, append, extend, +)
            - count를 통해 list의 개수를 알 수 있고 pop을 이용해 값을 뽑아내거나 remove로 삭제, sort로 정렬 가능
        - 세트
            - 값의 모임이며, 순서가 없다. 제공 메소드는 리스트와 유사하고 추가적으로 교집합(intersection)/합집합(union)이 제공된다.
        - 튜플
            - 리스트와 유사하나 읽기 전용이다. 읽는 속도는 빠르다. 제공되는 함수는 적다.
            - 자주 사용되는 것은 count, index 정도이다.
            - 리스트, 세트, 튜플은 상호간 생성자를 통해 변환 가능
        - 딕셔너리(사전)
            - 키 : 값의 쌍으로 이루어져 있다.
            - 예 : {'a' : 1, 'b' : 2, 'c' : 3}
            - items(), keys(), values() 메소드를 통해 키/값, 키, 값을 각각 반환할 수 있다.
            - del문을 이용해 삭제하거나 clear()를 통해 전체 삭제 가능
        - bool(부울)
            - True, False만 가능한 참 거짓 자료형
            - 논리연산 / 비교 연산의 결과로 활용한다.
            - 논리 연산자는 &, |, not이 있다. 비교는 >, <, !=, == 등이 있다.
            - 0은 false이며 다른 숫자는 true. 빈 문자열은 false, 값이 없는 상태인 공란도 false
    - 연산자
        - +,-,*,/,//,%,**,= 등이 있으며 //는 몫만 남기는 방식, **는 거듭제곱
    - 얕은 복사 vs 깊은 복사
        - 변수에는 객체의 주소가 저장된다.
        - 얕은 복사
            - a = [1,2,3], b=a 라고 한다면 동일한 리스트 객체를 공유하여 id(a), id(b)의 값은 동일하다.
            - 즉, 주소가 복사되어 객체를 공유하는 경우를 의미한다.
        - 깊은 복사
            - 객체를 공유하지 않는 복사 방식이다.
            - a = [1,2,3], b=a[:]라고 한다면 각각의 id값은 다르다. 이 때, a list내 element 값을 변경한다면 b는 변경되지 않는다.
- <b id="function">함수</b>
    - 함수란?
        - 여러 statement를 하나로 묶어서 실행할 수 있는 단위로 이미 정의되어 있는 것을 사용하거나 필요한 것을 정의
        - 1회 이상 호출 가능하며 종료 시 결과 값을 호출한다.
    - 선언
        - def로 선언하며 콜론(;)으로 종료.
        - 시작과 끝은 코드의 들여쓰기로 구분하며, 시작/끝은 명시하지 않아도 된다.
        - Header 파일로 나누거나 interface, implementation으로 나누지 않는다.
    - 예시
        - <pre><code>def <함수명>(인수1, 인수2, ... , 인수 N):
              &#32; <구문> # <-- 들여쓰기로 구분
              &#32; return <반환 값>
            </code></pre>
        - <pre><code>def Times(a, b):
            &#32; return a*b
        </code></pre>
    - 선언한 뒤 처리
        - 함수를 선언하면 메모리에 함수 객체가 생성되어 해당 객체를 가리키는 reference가 생성된다.
        - 해당 reference는 다른 변수에 할당 가능하다.
        - 예를 들어 위 ```Times``` 함수를 <pre><code>myTimes = Times</code></pre> 와 같이 사용한다면 myTimes를 이용해 함수를 호출할 수 있다.
            - <pre><code> r = myTimes(10, 10) </code></pre>
    - 반환 및 인수
        - return : 함수를 종료시키고 호출한 곳으로 돌아가게 한다.
            - 여러 개의 값을 튜플로 묶어 값 전달 가능
            - return을 사용하지 않거나 return 만 적어도 함수가 종료된다. 이 경우 리턴값은 None이다.
        - 인수
            - 레퍼런스를 이용해 전달되며 호출자 내부 객체의 레퍼런스이다.
            - 기본 인수
                - 함수 호출 시 인수 지정하지 않아도 기본 값이 할당 되게 지정
                - <pre><code> def Times(a=30, b=20):
                &#32; return a+b;</code></pre>
            - 키워드 인수
                - 인수 이름으로 값 전달. 변수 이름으로 특정 인수 전달이 가능하다.
                - <pre><code>def connectURI(server, port):
                &#32; str="http://" + server + ":" + port
                &#32; return str</code></pre>
            - 가변인수 리스트
                - 인수의 개수가 정해지지 않은 가변 인수 전달 가능. *를 사용해 인수는 튜플 형식 전달 
                - <pre><code> def Times(*ar):
                    &#32; for item in ar:
                    &#32; &#32; res.append(item)
                    return res;</code></pre>
            - 정의되지 않은 인수 처리
                - **를 사용해 정의되지 않은 인수를 Dictionary형식으로 전달할 수 있다.
                - <pre><code> def userURIBuilder(server, port, **user):
                &#32; str = "http://" + server + ":" + port + "/?"
                &#32; for key in user.keys():
                &#32; &#32; str += key + "=" + user[key] + "&"
                &#32; return str
                - <pre><code> userURIBuilder("test.com", "8080", id='userid', passwd='1234')
            - 호출자가 전달하는 변수의 타입에 따라 처리 방식이 다르다. 변수 타입은 다음과 같다
                - Mutable(변경 가능한 변수)
                - Immutable(변경 불가능한 변수)
            - 변경 불가능한 변수
                - 함수 1의 예시
                    - <pre><code>def sum1(x,y):
                        &#32; return x*y; </code></pre>
                - 함수 2의 예시
                    - <pre><code>def sum2(x,y):
                        &#32; x=1
                        &#32; return x + y; </code></pre>
                - a, b를 10, 20으로 초기화 후, 각각의 함수를 해당 인수를 전달하여 호출한다고 가정하자.
                - 이 때, sum1 함수는 x, y가 10,20 reference를 가리키게 되고, sum2에서는 x=1에 의해 x에 reference를 할당하게 된다.
                - 그러나 함수 내부에서 x=1 이라고 지정한 것이 이전에 x=10으로 지정했을 때 영향을 미치지는 않는다.
            - 변경 가능한 변수
                - 만약 ``` wordlist = ['J', 'A', 'M'] ```으로 지정한 뒤에 해당 리스트를 인자로 전달한 경우 내부에서 리스트 내 element를 변경 시, 해당 리스트 내의 값은 실제로 변경된다.
                - 그러나 내부에서 Deep Copy를 하여 새로이 reference를 할당해 변경한 경우, 외부에서 지정한 변수의 값에는 변경이 없다.
    - Scoping rule
        - 이름 공간(namespace)
            - 변수의 이름이 저장되는 장소
            - 함수 내부의 이름 공간, 지역 영역(Local Scope)
            - 함수 밖의 영역, 전역 영역(Global Scope)
            - 파이썬 자체에 정의에 의한 영역, 내장 영역(Built-in Scope)
        - LGB 규칙
            - 변수 이름을 찾을 때는 Local -> Global -> Built-in Scope 순서로 찾는다.
            - 지역 영역에서 전역 영역의 이름을 접근 시, global을 사용한다.
                - <pre><code>a = 10
                def sum(x): &nbsp; &#32; return x+a;</code></pre>
                - 위와 같이 지정 시 global에 있는 a를 찾게 된다.
    - 람다 함수
        - 이름이 없는 1줄 짜리 함수
            - ``` lambda 인수 : <구문> ```
        - 한 줄의 간단한 함수가 필요 시 사용하며, 프로그램의 가독성을 위해 사용하기도 한다.
        - 예
            - <pre><code> g = lambda x, y : x*y
            g(2,3)
            ---> 6
            (lambda x: x * x)(3)
            ---> 9</code></pre>
    - 재귀 함수
        - 함수 내부에서 자기 자신을 계속 호출하는 함수
        - 전달 인자를 변경하면서 연속적인 반복 연산 시에 유용
    - pass 구문
        - 아무 일도 하지 않고 넘긴다. 아무 것도 안하는 함수, 모듈, 클래스를 만들 경우 유용하게 사용
    - ```__doc__``` 속성과 help 함수
        - help 함수는 설명을 볼 수 있다.
            - ```help(print)```
            - 사용자가 만든 함수도 help를 사용해 설명을 볼 수 있다.
        - ```__doc__``` 속성을 이용해 더 자세한 설명을 추가할 수 있다.
            - ``` plus.__doc__ = "return the a+b"```
            - 위와 같이 plus 함수에 대한 설명을 더할 수 있다.
    - iterator
        - 순회 가능한 객체의 요소를 순서대로 접근할 수 있는 객체
        - 내부 반복문을 관리해 주는 객체
        - 내부의 ```__next__()```를 이용해 순회 가능한 객체의 요소를 하나씩 접근 가능하다.
        - 예)
            - <pre><code> s='abc'
            it = iter(s)
            it ---> <iterator object>
            next(it) ---> 'a'
            next(it) ---> 'b'
            it.__next__() ---> 'c'</code></pre>
    - generator
        - return 대신 yield 라는 구문을 이용해 함수 객체를 유지한 채 값을 호출자에 넘겨준다.
        - 값을 넘기고 함수 객체는 그대로 유지한다.
        - 함수의 상태를 그대로 유지하고 다시 호출할 수 있어 순회 가능한 객체를 만들 경우 유용하다.
        - 예)
            - <pre><code> def reverse(data):
            &#32; for index in range(len(data) - 1, -1, -1):
            &#32; &#32; yield data[index]
            for char in reverse('golf'):
            &#32; print(char) ---> f l o g가 순서대로 출력</code></pre>
        - 예2)
            - <pre><code> def abc():
            &#32; data ="abc"
            &#32; for char in data:
            &#32; &#32; yield char </code></pre>
        - abc를 출력하면 함수 객체, abc()를 출력하면 generator객체가 출력된다.
        - iterator를 이용해야 한다.
            - <pre><code> it = iter(abc())
            next(it) --> 'a'
            next(it) --> 'b'
            next(it) --> 'c'</code></pre>
- <b id="control">제어문</b>
    - if 문
        - 조건식을 평가하고 참인 경우만 구문 수행
        - 2개 이상 구문은 들여쓰기로 블록 지정하여 함수와 동일하며 들여쓰기 정도는 파일 전체를 통일 시킨다.
        - elif와 else를 이용해 다양한 조건을 구성할 수 있다.
        - 조건식의 판단은 자료형의 bool 값과 동일하게 True/False로 판단한다.
            - False는 0, 0.0, (), [], {}, None, '' 인 경우에도 그러하다.
        - and / &, or / |를 통해 조건식을 활용할 수 있다.
        - 구조
            - <pre><code> if <조건식>:
            &#32; <구문> 
            elif <조건식2>:
            &#32; <구문2>
            else
            &#32; <구문3></code></pre>
        - 단축 평가
            - 조건식 전체가 아닌 순차적 진행 시, 식 전체가 자명하다면 더 이상 수식을 평가하지 않는 방법
            - x and y라면 x가 False 시, y는 평가 하지 않고, x or y라면 x가 True 시 y는 평ㅇ가하지 않는다.
            - 이를 통해 연산 속도를 향상시키고 Run time error 발생을 사전에 차단할 수 있다.
    - while 문
        - 조건식이 참인 동안 내부 구문을 반복하여 수행한다.
        - 구조
            - <pre><code> while<조건식>:
            &#32; <구문>
            &#32; else:
            &#32; &#32 <구문></code></pre>
    - for 문
        - 시퀀스형 객체를 순차적으로 순회
        - else
            - 반복문 도중 break 인해 중간에 종료되지 않고 끝까지 수행된 경우 수행된다.
        - 구조
            - <pre><code> for <아이템 I> in <시퀀스형 객체 S>:
            &#32; <구문></code></pre>
        - for문에는 문자열, 리스트, 튜플, 사전 자료형 객체와 이터레이터/제너레이터 객체를 사용할 수 있다.
        - while / for문은 중첩하여 사용 가능하다.
    - break 문
        - 반복문 내에서 벗어날 수 있도록 지정하는 구문
    - continue 문
        - 반복문 내부 블록을 수행하지 않고 다음 item을 선택해 내부 블록의 시작 지점으로 이동하여 반복문을 지속 수행
    - 리스트 내장
        - ```[<표현식> for <아이템> in <시퀀스 객체> (if <조건식>)]```
            - 예 :
                - ```L_1 = [3,4,5], L_2=[1.5, -0.5, 4]```
                - ```[x*y for x in L_1 for y in L_2]```
                    - [4.5, -1.5, 12, 6.0, -2.0, 16, 7.5, -2.5, 20]
        - 기존 시퀀스 객체를 이용해 추가적인 연산을 통해 새로운 리스트 객체 생성
    - 제어문 응용 함수
        - ```filter(<function> | None, 시퀀스 객체)```
            - 함수의 결과 값이 참인 시퀀스 객체의 이터레이터 반환
            - None이 오는 경우 필터링하지 않는다.
            - 예
                - <pre><code> L = [10, 25, 30]
                  IterL = fillter(None, L)
                  for i in IterL:
                    &#32; print("Item: {0}".format(i))
                  Item: 10 
                  Item: 20
                  Item: 30
                  def GetBiggerThan20(i):
                    &#32; return i > 20
                  list(filter(GetBiggerThan20, L)) ---> [25, 30]</code></pre>
        - ```range(['시작값'], '종료값'[,'증가값'])```
            - 수열을 순회하는 이터레이터 객체 반환
            - 시작 값과 증가 값은 생략 가능하며, 이 때는 각 0, 1 할당
            - 예
                - <pre><code> list(range(10)) #종료값만 잇는 경우 - 10은 미포함
                [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
                list(range(5, 10)) # 시작값, 종료값
                [5, 6, 7, 8, 9]
                list(range(10, 0, -1)) # 시작값, 종료값, 증가값
                [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
                list(range(10, 20, 2)) # 10부터 20까지 짝수
                [10, 12, 14, 16, 18]</code></pre>
        - ```map(<funccton>, 시퀀스 객체, ...)```
            - 시퀀스 객체를 순회하며 function의 연산 수행
            - 함수의 인자 수만큼 시퀀스 객체 전달
            - 예
                - <pre><code>L=[1, 2, 3]
                def Add10(i):
                &#32; return i+10
                for i in map(Add10, L):
                &#32; print("Item: {0}".format(i))</code></pre>
            - 위 예시는 각 item이 10씩 더해져서 출력된다.
- <b id="class">클래스</b>
    - 개념
        - 데이터와 데이터를 변형하는 함수를 같은 공간에 작성할 수 있다.
        - 이를 통해 객체 지향 언어처럼 구현할 수 있다.
    - 용어 개념
        - 메서드
            - Class 이름 공간에 속한 함수
        - 인스턴스
            - 하나의 객체를 의미함.
        - 정보 은닉(information hiding)
            - 내부에 정의된 데이터, 함수를 외부에서 접근할 수 없도록 한다.
        - 추상화
            - 각 Class에서 공통 부분을 묶어 공통 class로 만들 수 있다.
        - 다형성
            - 같은 부모 함수를 상속받아 다른 행위를 수행할 수 있다.
    - 예시
        - <pre><code> class Person: # 클래스 정의
        &#32; Name = "default Name" # 멤버변수
        &#32; def print(self): # 멤버 메소드
        &#32; &#32; print("My Name is {0}".format(self.Name))
        p1 = Person() # 인스턴스 객체 생성
        p1.print() # 멤버 변수 값 출력</code></pre>
        - 위 예시 처럼, p1 인스턴스는 Person 클래스를 참조하는 reference가 된다.
    - 클래스와 인스턴스 이름 공간
        - 검색 순서
            - 인스턴스 객체 영역
            - 클래스 영역
            - 전역 영역
        - 멤버 데이터 추가
            - <pre><code> Person.title = "New title" # Class 객체에 새로운 멤버 변수 title 추가
            p1.age = 20 # p1 인스턴스 객체에만 age 멤버 변수 추가</code></pre> 
            - 만약 p2의 인스턴스에서 age를 출력하고자 하면 error가 발생한다.
        - 클래스와 인스턴스 관계
            - isinstance(인스턴스 객체, 클래스 객체)
                - 인스턴스 객체가 어떤 클래스에게서 생성되었는지 확인할 수 있다.
                - boolean 형태로 반환한다.
                - <pre><code> class Person:
                &#32; pass
                p = Person()
                isinstance(p, Person)) # True</code></pre>
    - 생성자와 소멸자
        - 생성자
            - 생성 시 초기화 ㅈ가업 수행
            - 인스턴스 객체 생성 시 자동 호출(```__init__()```)
        - 소멸자
            - 소멸 시 종료 작업 수행
            - 인스턴스 객체 참조 카운터가 '0'이면 호출(```__del__()```)
    - 메서드의 확장
        - 정적(static) 메서드
            - 인스턴스 객체 통하지 않고 class를 통해 직접 호출 가능한 method
            - self 인자가 필요하지 않다.
            - 형식 : <호출할 메소드 이름> = staticmethod(클래스 내 정의한 메소드 이름)
        - class 메서드
            - 클래스 영역의 데이터에 직접 접근할 수 있는 메소드
            - 암시적으로 첫 인자로 클래스 객체가 전달
            - 형식 : <호출할 메소드 이름> = classmethod(클래스 내 정의한 메소드 이름)
    - 연산자 중복
        - 사용자 정의 객체에서 필요한 연산자를 내장 타입과 형태와 동작이 유사하도록 재정의
        - 연산자 중복을 위해 두 개의 밑줄 문자가 앞뒤로 있는 메소드 미리 정의
            - 기본 제공되는 중복 정의가 없어 명시적으로 지정하지 않은 연산자 중복을 하는 경우 Type error가 발생한다.
        - 수치 연산자(내장)
            - ![Alt Text](./image/numOp.png)
    - 상속
        - 부모 클래스의 모든 속성(데이터, 메소드)를 자식 클래스로 물려준다.
        - 클래스의 공통 속성을 부모 클래스에 정의한다.
        - 하위 클래스에는 특화된 메소드와 데이터를 추가로 정의할 수 있다.
        - 형식 : 클래스를 정의 시 다음과 같이 정의
            - 예 : ```class Liger(Tiger, Lion): ...```
        - 장점
            - 동일 코드 중복 작성 방지
            - 코드 유지 보수 용이
            - 개별 클래스에 특화된 기능을 공통된 인터페이스로 접근 가능
        - 상속관계 확인(issubclass)
            - ```issubclass(자식클래스, 부모클래스)```
        - 다중 상속
            - 2개 이상의 클래스를 상속, 두 클래스의 모든 속성 전달 받음
        - 인스턴스 객체 영역
            - 클래스 객체 간 상속을 통한 영역(자식 클래스, 부모 클래스 영역)
                - 자식 클래스에서 부모 클래스로부터 물려받은 데이터, 함수를 재정의하지 않으면 부모 클래스의 데이터, 함수를 호출한다.
                - 이를 통해 중복 데이터 / 메소드를 최소화하여 메모리를 절약할 수 있다.
            - 전역 영역
- <b id=module>모듈</b>
    - 모듈이란?
        - 코드의 모음. 일련의 함수와 데이터를 포함
        - 코드의 재사용성(자주 사용되는 것 구현)
        - 코드를 이름공간으로 구분/관리
        - 복잡하고 어려운 기능 포함 프로그램 간단히 구현
            - 예를 들면 FTP로 서버에 접근해 파일 리스트를 가져오는 프로그램을 간단히 작성할 수 있다.
            - ```from ftplib import FTP```
    - import
        - 모듈을 현재 이름 공간으로 가져오는 역할
        - ```import math```
            - 위와 같이 math 모듈을 import하여 math 모듈의 함수, 데이터를 사용할 수 있게 된다.
        - dir() 함수를 이용해 모듈에 어떤 함수, 데이터가 있는지 확인할 수 있다.
            - ```dir(math)```
        - 방법
            - from <모듈> import <attribute>
                - ex) ```from simpleset import union```
            - from <모듈> import *
            - import <모듈> as <별칭>
                - 모듈 이름을 별칭으로 변경해 import
        - import하면 일어나는 일
            - import시, 해당 모듈의 바이트 코드(.pyc)가 있으면 그것을 import한다.
                - 바이트 코드는 일종의 중간 파일로 import를 빠르게 해주는 역할을 한다.
                - 바이트 코드가 이미 있다면 모듈을 interpreting하지 않고 바로 바이트 코드를 로딩한다.
                - 없다면, 모듈을 interpreting해서 바이트 코드를 생성한다.
            - 모듈을 import 시, 해당 모듈의 코드가 실행되며, 메모리에 모듈 코드가 로딩되면 프로그램이나 파이썬 인터프리터가 끝나기 전까지 변경되지 않는다.
    - 모듈 만들기
        - 직접 데이터, 함수를 모아 모듈을 만들 수 있는데, 큰 프로젝트의 경우 모듈 단위로 일을 진행한다.
        - 모듈은 일반적으로 <모듈이름>.py로 지정하여 저장한다.
        - simpleset 모듈 만들기
            - 텍스트 에디터로 교/차/합집합 함수 생성
            - simpleset.py로 저장하고 해당 모듈을 파이썬 라이브러리 디렉터리에 옮겨서 import하여 사용할 수 있다.
    - 모듈의 경로
        - ```sys.path``` 에 저장된 디렉토리를 검색하여 모듈을 import 시 모듈의 위치를 검색하는 경로를 찾을 수 있다.
        - 경로 밖에 있는 모듈은 import할 수 없다.
        - 모듈 경로 탐색 순서
            - 프로그램이 실행된 디렉터리(현재 프로그램의 디렉터리)
            - PYTHONPATH 환경 변수에 등록된 위치
            - 표준 라이브러리 디렉터리
    - 모듈 직접 실행
        - 모듈이 직접 실행 혹은 다른 곳에서 import 되었는지 구분할 수 있는 ```__name__``` attribute를 통해 구분할 수 있다.
        - 이는 모듈 자기 자신의 이름으로, 직접 실행된 경우는 ```__main__```로 저장된다.
            - <pre><code> if __name__=='__main__':
                &#32; print("모듈을 직접 실행하였음")</code></pre>
    - 패키지
        - 모듈을 하나도 모은 것.
        - 파이썬의 모듈 이름 공간을 구조화하는 방법(패키지 안에 패키지를 구현할 수 있다.)
        - XML 패키지의 구조
            - ![Alt Text](./image/xmlpackage.png)
            - ```from xml import *```와 ```import xml.dom```은 다르다. dom 객체는 후자의 경우에만 제대로 import된다.
            - 상위 패키지의 모듈을 import 하더라도 하위 모듈이 자동으로 다 import 되지는 않기 때문이다.(명시적으로 import해야 attribute를 사용할 수 있다.)
        - 각 디렉터리마다 ```__init__.py``가 꼭 존재 한다.
            - 패키지를 초기화하는 코드들이 포함된다.
- <b id="exception">예외 처리</b>
    - 예외란
        - 프로그램의 제어 흐름을 조정하는 이벤트.
        - 처리를 하지 않는 예외의 경우는 에러를 발생시켜 프로그램을 종료
            - 이러한 unhandled Exception에는 '0'으로 나누거나, DB 접속 시 연결되지 않거나, 파일 열었는데 사용자에 의해 삭제된 경우 등이 있을 수 있다.
        - 구문 에러
            - 오타, 들여쓰기 등의 실수로 인해서 발생
            - 이 경우는 Interpreter가 개발자에게 알려준다.
        - 예외의 종류(일부)
            - NameError - 선언하지 않은 변수를 참조
            - ZeroDivisionError - '0'으로 나누는 경우
            - IndexError : 배열의 인덱스를 벗어나는 참조 값을 참조 시
            - TypeError : 지원하지 않는 연산 시(숫자를 문자로 나누기 등)
        - 내장 예외
            - exceptions 모듈에 사전 정의된 예외로 프로그램 동작 중 자동으로 발생하거나 개발자가 명시적으로 발생 시킬 수 있다.
            - 내장 예외 모듈은 class 구조를 갖는다.
                - Exception : 모든 내장 예외의 기본 클래스
                - ArithmeticError : 수치 연산 예외의 기본 클래스
                - LookupError : 시퀀스 관련 예외의 기본 클래스
                - EnvironmentError : 파이썬 외부 에러의 기본 클래스
    - 예외 처리
        - try구문
            - <pre><code>try:
            &#32; <예외 발생 가능성이 있는 문장>
            except <예외 종류>:
            &#32; <예외 처리 문장>
            except (예외 1, 예외 2):
            &#32; <예외 처리 문장>
            except 예외 as 인자:
            &#32; <예외 처리 문장>
            else:
            &#32; <예외 미발생 시, 수행할 문장>
            finally:
            &#32; <예외 발생 유무에 무관하게 try 블록 이후 수행할 문장></code></pre>
            - 예시
                - <pre><code> def divide(a, b):
                &#32; return a/b
                try:
                &#32; c = divide(5,2)
                except ZeroDivisionError:
                &#32; print("~~")
                except TypeError as e: #전달되는 예외 인스턴스 객체를 e로 받아서 구문으로 활용할 수 있다.
                &#32; print(e.args[0])
                except:
                &#32; print("~~")
                else:
                &#32; print("~~")
                finally:
                &#32; print("~~")</code></pre>
    - 사용자 정의 예외
        - 사용자 정의 예외는 Exception class를 상속받아 구현해야 한다.
        - 내장 예외만으로 부족한 경우 개발자가 직접 예외를 정의해 사용할 수 있다.
        - raise 구문
            - 활용
                - ```raise [Exception]``` # 특정 예외를 발생
                - ```raise [Exception(data)]``` # 예외 발생 시, 관련 데이터 전달
                - ```raise``` # 발생된 예외를 상위로 전달
        - assert 구문
            - 개발 과정에서 디버깅, 제약 설정 등에 발생시킴
            - 인자로 받은 조건식이 거짓이면 AssertionError 발생
            - ```Assert <조건식>, <관련 데이터>```
            - ```__debug__```가 True인 경우만 assert 구문 활성화
                - 명령 prompt에서 최적화 옵션(-O)를 설정 시, ```__debug__```는 False로 설정된다.
            - 예
                - <pre><code> def foo(x): #받은 인자의 type이 정수형인지 검사하는 함수
                &#32; assert type(x) == int, "Input value must be integer"
                &#32; return x * 10
                ret = foo("a") # AssertionError가 발생한다.
                print(ret)</code></pre>
- <b id="inputoutput">입출력</b>
    - 출력
        - print()함수
            - 2.x는 함수가 아니었으나 3.x에서 함수로 변경
            - 입력인자로는 구분자(sep), 끝라인(end), 출력(file)을 지정할 수 있다.
            - 예) ```print("welcome to", "python", sep="~", end="!", file=sys.stderr)```
                - file이라는 출력 인자를 지정하여 표준오류 또는 파일로도 변경할 수 있다.
        - formatting
            - format() 함수를 통해 문자열을 더 자유로이 다룰 수 있다.
            - 문자열 내 값이 들어가길 원하면 {}로 표시하며, {}안의 값은 숫자로 표현하여 format 인자의 인덱스를 나타낸다.
            - 예) ```print("{0} is {1}".format("apple","red"))``` -> 출력은 apple is red로 된다.
            - 키/사전을 이용한 포매팅
                - 키 : ```print("{item} is {color}".format(item="apple", color="red"))```
                - 사전의 경우 : ```dic = {"item":"apple", "color":"red"} // print("{0[item]} is {0[color]}".format(dic))```
            - ** 기호의 경우 dictionary를 입력으로 받은 것으로 판단하고 인자를 하나만 받아 불필요한 index를 생략가능
                - 예) ```print("{item} is {color}".format(**dic))```
            - !기호를 통해 문자열 변환도 가능하다.
                - 예) ```print("{item!s} is {color!s}".format(**dic))``` --> apple is red
                - 예) ```print("{item!r} is {color!r}".format(**dic))``` --> 'apple' is 'red'
                - 예) ```print("{item!a} is {color!a}".format(**dic))``` --> 'apple' is 'red'
                - !s, !r, !a는 각각 str(), repr(), ascii()의 실행결과와 동일하다.
            - : 기호로 정렬, 폭, 부호, 공백처리, 소수점, 타입을 지정할 수 있다.
                - 예) ```print("{0:$>5}".format(10))``` --> $$$10 #이 경우 $를 쓰지 않으면 공백으로 처리된다. 5자리만큼 사용하여 우측 정렬을 하는 것이다.
                - > 는 우측 기준, <는 좌측 기준, ^는 중앙 기준, = 는 부호화와 상관이 있다.
                - "="를 쓰면 부호가 나타난다.
                    - 예) ```print("{0:$>-5}".format(-10))``` --> $$-10
                    - +, -는 각각의 기호, " " 와 같이 공백은 마이너스 시에는 마이너스 부호, 플러스 시에는 공백을 표시하라는 의미이다.
            - 진수 표현법
                - "b"는 이진수, "d"는 십진수, "x"는 16, "o"는 8진수이며 "c"는 문자열을 출력하라는 의미다.
                - "#"은 #x는 16, #o는 8, "#b"는 2진수 -> 앞에 진수 표현이 들어간다. 16은 0x, 8은 0o, 2는 0b와 같이 출력
                - 예) ```print("{0:b}".format(10))``` --> 1010
            - 실수 표현 법
                - "e"는 지수표현, "f"는 일반 실수, "%"는 퍼센트 표현이다.
                - 실수 표현 시, 소수 몇 번째 까지 표현할지 지정할 수 있다.
                - 예) ```print("{0:.3f}".format(4/3))``` --> 1.333
    - 입력
        - input()함수
            - 예) ```a=input('isert any keys:')``` --> 이와 같이 화면에 prompt를 주어 사용자가 키를 입력할 시기를 확인할 수 있게 한다.
    - 파일 입출력
        - open()
            - 파일을 열고 전용 함수로 작업하는 것이 일반적
            - 형식 : ```파일객체 = open(file, mode)```
            - mode는 속성
                - r: 읽기 모드(디폴트)
                - w: 쓰기 모드
                - a: 쓰기 + 이어쓰기 모드
                - + : 읽기 + 쓰기 모드
                - b: 바이너리 모드
                - t: 텍스트 모드(디폴트)
        - 오픈 후 입출력 - read(), write(), close()
            - read() : 데이터를 읽음
            - write() : 함수, 문자열을 씀
            - close() : 파일을 닫음, closed를 통해 파일의 닫힘 여부 bool 값도 판단 가능하다.
            - ```f = open('text.txt', 'w'); f.write('plow deep\nwhile sluggards sleep'); f.close()```
            - 텍스트 모드는 일반 문자열처럼 encoding이 적용되어 binary data를 다룰 때는 오류가 발생하여 binary data 다룰 경우에는 binary mode를 써야 한다.
        - 이외 - readline(), readlines(), tell(), seek()
            - readline() : 호출 시 한 줄씩 읽은 문자열 반환
            - readlines() : 파일의 모든 내용을 줄 단위로 잘라서 리스트 반환
            - tell() : 현재 파일에서 어디까지 읽고 썼는지 위치 반환
            - seek() : 사용자가 원하는 위치로 포인터 이동
        - with~as 구문
            - 코드 구문의 내용이 다 끝나면 자동으로 파일이 닫히게 된다.
            - <pre><code>
            with open('test.txt') as f:
            &#32; print(f.readlines())
            &#32; print(f.closed)
            출력 : ['plow deep\n', 'while sluggards sleep']
            False
            f.closed
            True</code></pre>
        - pickle
            - 문자열은 배운 내용대로 가능하나, 리스트/클래스를 저장 시에 더 쉽게 하려면 pickle 모듈을 사용해야 한다.
            - pickle 모듈로 파일에 쓰거나 읽을 때는 반드시 binary 모드로 파일을 열어야 한다.
            - 쓰기 : dump
                - <pre><code>colors = ['red', 'green', 'black']
                import pickle
                f = open('colors', 'wb')
                pickle.dump(colors, f)
                f.closed</code></pre>
            - 읽기 : load
                - <pre><code>del colors 
                f = open('colors', 'rb')
                colors = pickle.load(f)
                f.close()
                colors # ['red', 'green', 'black']</code></pre>
            - 사용자 정의 클래스
                - 파이썬 객체는 전부 pickle로 저장이 가능하며, 사용자 정의 클래스 객체도 가능하다.
                - <pre><code>class test:
                &#32; var = None
                a = test()
                a.var = 'Test'
                f = open('test', 'wb')
                pickle.dump(a, f)
                f.close()
                f = open('test', 'rb')
                b = pickle.load(f)
                f.close()
                b.var # 'Test'</code></pre>
- <b id="string">문자열 다루기</b>
    - 문자열 클래스
        - str : 내장된 기본 클래스로 문자열을 다루는 클래스
            - capitalize() : 첫 문자만 대문자, 나머지는 소문자 유지
            - count(keyword, [start, [end]]) : start, end를 통해 slicing을 하여 특정 word가 얼마나 나왔는지 확인할 수 있다.
            - encode([encoding, [errors]]) : 기본 유니코드 이나 이를 사용해 특정 문자열 스타일로 변환 가능, cp949 또는 utf-8등으로 가능하다.
                - errors에 strict(기본)을 지정하면 지정 불가한 인코딩을 지정 시 예외가 발생한다.
                - ignore를 사용하면 error를 무시하며 replace로 지정 시, ???로 지정된다. 
                - xmlcharrefreplcace 또는 backslashreplace를 통해 다른 것으로 지정할 수도 있다.
            - endswith(postfix, [start, [end]]) : bool값을 반환하며, 특정 postfix로 문자열이 끝나면 true를 반환한다. 슬라이싱을 통해 체크할 부분을 지정할 수 있다.
            - expandtabs([tabsize]) : \t라는 tab을 공백으로 치환시킨다. 숫자를 인자로 넣으면 1개의 공백으로 치환
            - find(keyword, [start, [end]]) : 특정 키워드가 슬라이싱된 곳에 있는 위치를 나타낸다. 못 찾으면 -1 반환
            - index(keyword, [start, [end]]) : find와 동일하나 못 찾으면 예외를 발생시킨다.
            - isalnum() : 알파벳, 숫자로 표현된 경우만 True 반환
            - isalpha() : 알파벳인 경우만 True
            - islower() : 모든 알파벳이 소문자인 경우만 True, 숫자 등은 신경 쓰지 않음
            - isspace() : 모두 공백이면 True(탭, 개행, 스페이스)
            - istitle() : 각 단어가 대문자에 이어 소문자로 나오면 True
            - isupper() : 모두 대문자면 True, 숫자 등은 신경 쓰지 않음
            - isdecimal(), isdigit() : 10진수면 True
            - isnumeric() : 숫자에 관련되면 다 True
            - join(sequence) : ```".".join("HOT") --> 'H.O.T'```
            - lower() : 모든 영문자를 소문자로 반환
            - lstrip([chars]) : 인자로 지정한 문자열을 왼쪽에 있으면 다 지움
            - rstrip([chars]) : 인자로 지정한 문자열을 오른쪽에서 다 지움
            - maketrans(x, [y, [z]]) : 입력 인자가 하나라면 ```transmap = str.maketrans({"p":"P"})``` map 형태로 반환하여 그것을 통해 특정 문자열을 translate할 수 있다.
                - 예 : ```"python is powerful".translate(transmap)```
                - 입력 인자가 둘이면 각 문자열의 길이는 동일하게 인자로 줘야 하며 각각의 index를 1번째 인자를 2번째 인자로 변환한다.
                - 세 개면 3번째 인자로 지정된 문자는 다 지운다.
            - partition(separator) : 문자열을 separator로 나눈다.
            - replace(old, new, [count]): old를 new로 반환시키며 count를 지정하면 그 숫자만큼만 변환한다.
            - rfind(keyword, [start, [end]]) : 우측에서 key를 찾고 없으면 -1을 반환
            - rindex(keyword, [start, end]]) : 우측에서 index를 찾는데 없으면 에러 반환
            - rpartition(separator) : separator를 우측에서부터 찾아 그 기준으로 값을 나눈다.
            - rsplit([separator, [maxsplit]) : separator가 없으면 공백 기준으로 나눈다, maxsplit을 지정하면 그 횟수만큼 split한다
            - rstrip([chars]) : 우측에서 부터 지정한 문자열을 다 제거한다.
            - split([separator, [maxsplit]) : 좌측에서 부터 separator로 나누며, maxsplit 지정 시 그 횟수만큼 split한다.
            - splitlines([keep]) : True로 인자를 넣으면 \n 등 new line이 포함된 결과로 나누어 확인할 수 있다.
            - startswith(prefix, [start, [end]]) : prefix로 지정한 단어가 있으면 True
            - strip([chars]) : 양쪽에서 지정한 모든 문자열 제거
            - swapcase() : 소문자는 대문자, 대문자는 소문자로
            - title() : 모든 단어를 첫 문자는 대문자, 나머지는 소문자로
            - upper() : 모든 영 소문자를 대문자로
    - 정규표현식
        - 특정한 규칙을 가진 문자열을 표현하며, 주어진 패턴으로 문자열을 검색/치환시에 사용하며 vi,grep 등 프로그램에서 사용된다.
        - ![Alt Text](./image/regex.png)
        - 예
            - app.e : app, e 사이의 모든 1개의 문자가 포함되는 모든 문자. - apple, appLe 등
            - ^app : app으로 시작하는 모든 것
            - ple$ : ple 로 끝나는 모든 문자
            - appl[a-z] : appl 뒤에 a~z까지 모든 small 문자 한개만 매칭
            - appl[^a-z] : 소문자가 오는 경우를 제외한 모든 경우
            - apple|E : apple, applE 만
        - escape 문자열
            - ![Alt Text](./image/escape.png)
        - 정규표현식 모듈
            - search(pattern, string[, flags]) : string 전체에 대해 pattern이 존재하는지 검사 후 MatchObject 인스턴스 반환
            - match(pattern, string[, flags]) : string 시작에서 pattern이 존재하는지 검사 후 MatchObject 인스턴스 반환
            - split(pattern, string[, maxsplit=0]) : pattern을 구분자로 string을 분리하여 리스트로 반환
            - findall(pattern, string[, flags]) : string에서 pattern과 매치되는 모든 경우를 찾아 리스트로 반환
            - sub(pattern, repl, string[, count]) : string에서 pattern과 일치한 부분에 대해 repl로 교체해 결과 문자열 반환
        - 모듈 예제
            - <pre><code> >>> import re
            >>> re.match('[0-9]*th', '35th') # 결과로 Match 객체 반환
            <_sre.SRE_Match object at 0x02F023A0>
            >>> bool(re.match('[0-9]*th', ' 35th')) # 불린으로 검색 결과 확인, 공백이 있어서 False
            False
            >>> bool(re.search('[0-9]*th', ' 35th'))
            True
            >>> bool(re.match('ap', 'This is an apple')) # 문자열 시작부터 검색
            False
            >>> bool(re.search('ap', 'This is an apple')) # 문자열 전체에서 검색
            True </code></pre>
            - <pre><code>
            >>> re.findall(r"app\w*". "application orange apple banana") # 매치되는 문자열이 있는 경우
            ['application', 'apple']
            >>> re.findall(r"king\w*", "application orange apple banana") # 매치되는 문자 []
            []</code</pre>
            - <pre><code>
            >>> re.sub("-", "", "901225-1234567") #주민등록번호 형식 변경
            '9012251234567'
            >>> re.sub(r"[:,|\s]", ", ", "Apple:Orange Banana|Tomato") # 필드 구분자를 통일
            'Apple, Orange, Banana, Tomato'
- <b id="date">날짜 다루기</b>
    - 컴퓨터의 시간 표현
        - Time stamp
        - UTC(협정세계시)
            - 세슘 원자 기준
        - 그리니치 평균시
            - 그리니치 천문대 기준 좌우 시간, UTC와 거의 동일
        - LST(지방표준비, Local Standard Time)
            - 한국은 UTC+9
        - 일광절약 시간제(Daylight Saving Time)
            - 서머타임시에 사용
    - 시간 모듈
        - struct_time 시퀀스 객체(읽기 전용)
            - tm_year : 년도
            - tm_mon : 월(yyyy)
            - tm_mday : 일(1~12)
            - tm_hour : 시(0~23)
            - tm_min : 분(0~59)
            - tm_sec : 초(0~61, 윤초 때문에 61도 있음)
            - tm_wday : 요일(월요일부터 0)
            - tm_yday : 누적 날짜(1월1일부터의 누적일)
        - time 모듈의 함수
            - time.time() : 1970년 1월 1일 자정 이후 누적 초 float 단위
            - time.sleep(secs) : 현재 동작 중인 프로세스를 주어진 초만큼 정지
            - time.gmtime([secs]) : 입력된 초를 변환해, UTC 기준의 struct_time 시퀀스 객체로 반환
            - time.localtime([secs]) : 입력된 초를 변환해, 지방표준시 기준의 struct_time 시퀀스 객체 반환
            - time.asctime([t]) : struct_time 시퀀스 객체 인자로 받아 'Sun Mar 15 18:49:28 2009'와 같이 변환
            - time.mktime(t) : 지방 표준시인 struct_time 시퀀스 객체를 인자로 받아 time()과 같은 누적된 초 반환
        - strptime, strftime
            - 사용자가 직접 포맷 지정해 출력
            - 원형
                - time.strftime(format[, t]) : struct_time객체를 사용자 정의한 형태로 변환
                - time.strptime(string[, format]) : 사용자가 정의한 형식을 struct_time객체로 변환
            - 지시자
                - ![Alt Text](./image/format_inst.png)
    - 날짜, 시간 모듈
        - datetime 모듈 : 기념일과 같은 날짜, 시간 연산을 위해 사용
            - 예) : 오늘 부터 1000일 후, 기념일 계산 등
            - 주요 클래스
                - datetime.date : 일반적인 그레고리안 달력의 연,월,일
                - datetime.time : 시간을 시, 분, 초, 마이크로 초, 시간대 로 표현
                - datetime.datetime : date클래스와 time 클래스의 조합
                - datetime.timedelta : 두 날짜 혹은 시간 사이의 기간
            - 생성자
                - datetime.date(year, month, day)
                    - year는 1~9999, month는 1~12, day는 1~ 해당 월의 날짜 안으로만 넣지 않으면 예외 발생
        - time 클래스
            - 생성자
                - datetime.time(hour[, minute[, second[, microsecond[, tzinfo]]]])
                - 시, 분, 초, 마이크로초, 시간대 정보를 입력 받아 time 객체 생성
        - timedelta 클래스
            - 두 날짜 , 시간 사이의 기간
            - 생성자
                - timedelta([days[, seconds[, microseconds[, milliseconds[, minutes[, hours[, weeks]]]]]]])
                - delta 객체를 만들어 상호 연산 또한 가능하다.(*, // 등도 가능)
                - boolean 연산 또한 객체 끼리 가능하다. 어느 쪽이 더 크고 작고를 비교할 수 있다.
                - 다른 시간 객체와 timedelta 객체 간의 연산도 가능하다.
                    - 예를 들어 현재 시간 today() 함수로 객체를 만들고 timedelta 객체를 만들어 연산하여 다른 날짜를 연산할 수 있다.
- <b id="math">숫자 다루기</b>
    - 내장 함수
        - 모듈 import 없이 사용 가능
        - sum(iterable[, start]): 순회 가능한 객체의 총 합계
        - max(iterable): 순회 가능한 객체의 최대값
        - min(iterable): 순회 가능한 객체의 최소값
        - abs(x) : x의 절대 값
        - pow(x, y[, z]) : x의 y제곱
        - round(x[, n]) : x의 반올림 결과
        - divmod(a, b): a/b의 몫, 나머지 튜플로 반환
        - 순회 가능한 객체의 경우 list tuple등이 있으며 해당 객체를 넣으면 알아서 연산을 진행함, start등을 지정해 slicing도 가능
    - math 모듈
        - 함수
            - math.ceil(x) : N >= x 만족하는 가장 작은  정수 N 반환
            - math.floor(x) : N <= x 만족하는 가장 큰 정수 N 반환
            - math.trunc(x) : x의 정수 부분만 반환
            - math.copysign(x, y) : y의 부호만 x에 복사해 반환
            - math.fabs(x) : x의 절대값 반환
            - math.factorial(x) : x의 계승 값 반환, x!
            - math.fmod(x, y) : 나머지 연산 수행
            - math.fsum(iterable) : 입력받은 값의 합계 반환
            - math.modf(x) : 입력받은 x의 순수 소수부분, 정수 부분 분리해 튜플 반환
        - 지수 로그 연산
            - math.pow(x, y) : x의 y 제곱
            - math.sqrt(x) : x의 제곱근
            - math.exp(x) : e^x 값
            - math.log(x[, base]) : 밑은 base인 log x
        - 삼각 함수
            - math.degrees(x) : 라디안 표현한 각도를 60분법 변환
            - math.radians(x) : 60분법 표현 각도를 라디안으로 변환
            - 이외 sin, asin, cosh, asin, cos, atan, sinh 등의 함수도 있다.
    - 분수 모듈(fractions)
        - Fraction 클래스
            - 유리수와 관련된 연산을 효율적으로 처리하는 분수 모듈
            - 생성자
                - fractions.Fraction(분자=0, 분모=1)
                - fractions.Fraction(Fraction 객체)
                - fractions.Fraction(문자열)
            - 지원 메서드
                - 기본 연산 및 floor, ceil, round가 가능하다. 최대 공약수 반환하는 method 또한 있다.
                - ```f = Frantion.from_float(3.14); f.__floor__()```
    - 십진법 모듈(decimal)
        - 부동 소수점의 표현 방식
            - 소수점의 위치를 고정하지 않고 그 위치를 나타내는 수를 따로 적는 방식으로 유효숫자를 나타내는 가수, 소수점 위치 풀이하는 지수로 나눈다.
            - '[가수]*[밑수][지수]'와 같이 나타낸다.
            - 컴퓨터 시스템은 밑수를 2, 부호 나타내는 MSB를 추가해 세 부분으로 나눈다.
            - 1: 부호, 8 비트 : 지수부, 23비트 : 가수부
            - 이에 따라 정확한 실수를 나타내지 못하는 문제가 발생할 수 있다. 또한 연산에 문자가 발생할 수 있다.
            - 이를 해결하기 위해 사용되는 것이 십진법 모듈이다.
        - 생성자
            - decimal.Decimal([value[, context]])
            - value에는 Infinity, Inf, NaN, -0 등의 값도 넣을 수 있다.
        - 연산
            - 모든 수치 연산 및 인자로 전달이 가능하다.
            - max, min, sum 등의 내장 함수 인자로 전달이 가능하다.
    - 랜덤 모듈(random)
        - method
            - random.seed([x]) : 임의 숫자 생성기의 초기화 작업, x를 주지 않거나 NaN이 들어가면 현재 시스템 시간 기반
            - random.random() : '0.0 <= ㄹ < 1.0' 사이의 임의의 float 숫자 반환
            - random.uniform(a, b) : 인자로 받은 두 값 사이의 임의의 float 숫자 반환
            - random.gauss(m, sb) : 가우스 분포의 난수 반환
            - random.randrange([start], stop[, step]) : 내장 함수인 range()의 아이템 중에서 임의로 선택해 반환(중복 허용)
                - 예) ```[random.randrange(20) for i in range(10)] # [1, 5, 6, 19, 12, 4, 5, 3, 10, 1]```
                - 예) ```[random.sample(range(20), 10] #[19, 1, 16, 17, 9, 3, 2, 6, 5, 15]``` -> 중복 비 허용을 원한다면 이와 같이 사용
            - random.randint(a, b) : 'a <= N <= b' 인 임의의 정수 N 반환
            - random.choice(seq) : 입력받은 시퀀스 객체의 임의의 아이템 반환
                - 예) ```l = list(range(10)); [random.choice(l) for i in range(3)] # [9, 2, 2]``` -> 중복 값이 생김
                - 예) ```random.sample(l, 3) #[5, 8, 7]```-> 중복 값 허용 하지 않고 싶은 경우
            - random.shuffle(x[, random]) : 입력받은 시퀀스 객체 섞음
- <b id="filesystem">파일 시스템</b>
    - os.path
        - 파일 경로 생성 및 수정, 파일 정보를 가져올 수 있다.
        - import
            - ```from os.path import *```
        - method
            - os.path.abspath(path) : 절대 경로 반환
            - os.path.basename(path) : 입력받은 경로의 기본 이름 반환(abspath와 반대임)
            - os.path.dirname(path) : 입력받은 파일/디렉터리의 경로를 반환한다.
            - os.path.exists(path) : 입력받은 경로가 있으면 True, 없으면 False
            - os.path.expanduser(path) : 입력받은 경로안의 ~를 현재 사용자 디렉터리의 절대 경로로 대체한다.
            - os.path.expandvars(path) : path안에 환경 변수가 있으면 확장, 즉, 환경변수를 지정한 값으로 확장하는 것
            - os.path.getatime(path) : 입력받은 경로에 대한 최근 접근 시간을 반환한다. 파일 또는 권한 없으면 os error 발생
                - 이 함수의 결과를 알아볼 수 있게 하고자 하는 경우 time 모듈을 import 하여 gmtime을 이용하여 변환
            - os.path.getmtime(path) : 입력 받은 경로에 대한 최근 변경 시간 반환, 파일 없거나 권한 없으면 os error
            - os.path.getctime(path) : 입력 받은 경로에 대한 생성 시간 반환. 파일 없거나 권한 없으면 os error
            - os.path.getsize(path) : 입력받은 경로에 대한 바이트 단위의 파일 크기 반환, 파일 없거나 권한 없면 os error
            - os.path.isabs(path) : 절대 경로면 True, 아니면 False인데 실제 파일 존재 여부는 무시
            - os.path.isfile(path) : 파일이면 True, 아니면 False, 즉 경로가 파일인지 검사
            - os.path.isdir(path) : 경로가 디렉터리인지 아닌지 검사, 디렉터리면 True
            - os.path.join(path1[, path2[, ...]]) : 해당 os 형식에 맞게 입력받은 경로 연결
                - 만약 1번 인자, 2번 인자가 둘 다 절대 경로, 3번 인자가 상대경로면 2,3번만 합친다.
            - os.path.normcase(path) : 해당 os에 맞게 입력받은 경로의 문자열 정규화
            - os.path.normpath(path) : 입력받은 경로 정규화
            - os.path.split(path) : 입력 받은 경로를 디렉터리, 파일 부분으로 나누는데, 실제 파일 존재여부는 확인 하지 않는다.
            - os.path.splitdrive(path) : 입력 받은 경로를 드라이브 부분과 나머지로 나누는데, 실제 파일 존재 여부는 비확인
            - os.path.splitext(path) : 입력 받은 경로를 확장자와 그 외로 나누며, 실제 파일 존재 여부는 비확인
    - glob 모듈
        - windows의 dir 명령이나 linux의 ls명령과 유사한 기능을 제공
        - 함수
            - glob.glob(path) : path 경로에 대응하는 모든 파일, 디렉터리의 리스트 반환, 경로 방식에 따라 절대 경로로 결과 나타나게 할 수 있다.
                - path 인자는 정규표현식을 통해 입력할 수 있다.
            - glob.iglob(path) : glob과 동일하게 동작 수행하나 리스트가 아닌 iterator를 반환
    - tree 만들기
        - tree는 하위 디렉터리 구조를 보여주는 tool이다. cmd창에서 tree 명령으로 수행 가능하다.
        - 기본 예제 소스 코드
            - ![Alt Text](./image/tree_code.png)
- <b id="database">데이터베이스</b>
    - SQLite3
        - 개요
            - 디스크 기반 가벼운 DB 라이브러리로 서버가 별도로 불필요해 자원을 적게 사용
            - 모바일 디바이스에 기본적으로 사용되며 파이썬에 기본 포함된다.
            - 별도의 모듈 설치 없이 pysqlite 모듈을 사용하면 된다.
        - 모듈 함수
            - connect 함수 : DB에 연결하고 연결된 객체 반환
            - complete_statement(sql) : SQL 문장에 대해 True 반환
            - register_adapter(type, callable) : 사용자 정의 파이썬 자료형을 SQLite3에서 사용토록 등록, callable을 통해 변환 시 사용할 함수 지정
            - register_converter(typename, callable) : SQLite3에 저장된 자료를 사용자 정의 자료형으로 변환, typename을 통해 자료형 지정
        - Connection class
            - cursor() : Cursor 객체 생성
            - commite() : 현재 트랜잭션 변경 내역 DB에 반영
            - rollback() : 가장 최근의 commit() 이후 지금까지 작업한 내용에 대해 되돌림
            - close() : DB 연결 종료
            - isolation_level : 트랜잭션의 격리 수준 확인/설정
                - none으로 지정 시 auto commit 모드가 된다.
            - execute, executemany, executescript 계열 메소드 : 임시 Cursor 객체 생성해 해당 execute 계열 메서드 수행
            - create_aggregate메서드 : 사용자 정의 집계 함수 생성
            - create_collation 메서드 : 문자열 정렬 시 SQL 구문에서 사용될 이름 및 정렬 함수 지정
                - 첫 문자열이 더 작으면 -1, 같으면 0, 더 크면 1
            - iterdump() : 연결된 DB의 내용을 SQL 질의 형태로 출력
        - Cursor class
            - execute 메서드 : SQL 문장 실행
            - executemany 메서드 : 동일한 SQL 문장을 parameter만 변경해 수행
            - executescript 메서드 : 세미콜론으로 구분된 연속된 SQL 문장 수행
            - fetchone() : 조회된 결과에서 데이터 1개 반환하고 없으면 None
            - fetchmany 메서드 : 조회된 결과에서 입력받은 size 만큼의 데이터를 리스트 형태 반환
            - fetchall() : 조회된 결과 모두를 리스트 형태로 반환, 없으면 빈 리스트 반환
    - SQLite3 사용법
        - import : ```import sqlite3```
        - Connection 객체 생성
            - ```con = sqlite3.connect("test.db")``` -> 실제 파일 이용한 Connection 객체 생성, 이미 생성된 db에 대해서도 조회, 연산이 가능
            - ```con = sqlite3.connect(":memory:")``` -> 메모리를 이용한 객체 생성으로, 끊어지면 작업한 내용 모두 사라짐. 연산속도는 더 빠름
        - execute 메서드를 통한 SQL 문 수행 및 쿼리
            - <pre><code>
            import sqlite3
            con = sqlite3.connect(":memory:")
            cur = con.cursor()
            cur.execute("CREATE TABLE PhoneBook(Name text, PhoneNum text);")
            cur.execute("INSERT INTO PhoneBook VALUES('Someone', '010-1234-5678')
            name = "Someone"
            phoneNumber = '010-5678-1234'
            cur.execute("INSERT INTO PhoneBook VALUES(?,?);", (name, phoneNumber))
            </code></pre>
            - 사전을 이용한 인자 전달
                - ```cur.execute("INSERT INTO PhoneBook VALUES(:inputName, :inputNum);", {"inputNum":phoneNumber, "inputName":name})```
            - 시퀀스 객체를 이용한 인자 전달
                - ```datelist = (('Tom', '010-543-5432'), ('DSP', '010-123-1234'))```
                - ```cur.executemany("INSERT INTO PhoneBook VALUES(?, ?);", datalist)```
        - fetch를 통한 record 조회
            - <pre><code>
            cur.execute("SELECT * FROM PhoneBook;")
            for row in cur:
                &#32; print(row)
            </code></pre>
            - fetchone, fetchmany를 통해 조회시
                - fetchone은 하나를 조회하며, fetchmany를 바로 그 뒤에서 사용하면 나머지 조회되지 않은 결과 중 지정한 수만큼 모두 반환한다.
                - 만약 fetchmany에 인자로 지정한 숫자가 실제 저장된 데이터 크기보다 크면 전체를 다 반환
            - fetchall
                - 기존 조회된 결과의 다음부터 모든 결과를 다 반환함
                - 즉 fetchone 이후에 fetchall하면 one에서 반환된 것 이후 내용을 전부 반환
        - 트랜잭션 처리
            - DCL 명령어를 통해 SELECT 수행하고 결과를 모두 fetch 시에는 기존에 commit을 수행하지 않았다면 수행한 SQL 구문이 반영되지 않을 수 있다.
        - 정렬 : Order by
            - SELECT 구문에 Order BY를 지정하여 반환되는 결과를 정렬할 수 있다.
            - DESC를 지정하면 내림차순으로 지정된다.
            - 사용자 임의의 정렬 방식을 지정 시에는 미리 정렬 함수를 지정하고 SELECT 문에서 해당 정렬 방식을 명시적으로 지정해야 한다.
                - <pre><code>
                def OrderFunc(str1, str2): # 대소문자 구별 없이 정렬
                &#32; s1=str1.upper()
                &#32; s2=str2.upper()
                &#32; retrun (s1 > s2) - (s1 < s2)
                con.create_collation('myordering', OrderFunc) # SQL 구문에서 호출할 이름, 함수 등록
                cur.execute("SELECT Name FROM PhoneBook ORDER BY NAME COLLATE myordering")
                </code></pre>
        - 내장, 집계 함수
            - abs(x) : 절대값 반환
            - length(x) : 문자열 길이 반환
            - lower(x) : 소문자로 변환 후 반환
            - upper(x) : 대문자로 변환 후 반환
            - min(...) : 최소값 반환
            - max(...) : 최대값 반환
            - random(*) : 임의의 정수 반환
            - count(x) : NULL이 아닌 튜플 개수 반환
            - count(*) : 튜플의 개수 반환
            - sum(x) : 합 반환
        - 자료형
            - SQLite3의 자료형과 Python 자료형 상호 대응
                - NULL - None
                - INTEGER - int
                - REAL - float
                - TEXT - str, float
                - BLOB - buffer
        - DB 덤프 만들기
            - 현재 상태를 SQL구문으로 추출하고 싶은 경우 Dump를 이용하면 된다.
            - iterdump()를 통해 print하면 됨
            - <pre><code>
            import sqlite3
            con = sqlite3.connect(":memory:")
            cur = con.cursor()
            cur.execute("CREATE TABLE PhoneBook(Name text, PhoneNum text);")
            cur.execute("INSERT INTO PhoneBook VALUES('Derick', '010-1234-5678');")
            list = (('Tom', '010-543-5432'), ('DSP', '010-123-1234'))
            cur.executemany("INSERT INTO PhoneBook VALUES(?,?);", list)
            for l in con.iterdump():
            &#32; print(l)
            </code></pre>
            - 위 덤프 예제의 실행 결과는 다음과 같다
                - ![Alt Text](./image/dump_result.png)
        - 예시
            - ![Alt Text](./image/example_sqlite3.png)