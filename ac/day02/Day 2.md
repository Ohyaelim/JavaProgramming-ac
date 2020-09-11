# Day 2

int data=10  ->저장공간
System.out.println(data) ->값


출력함수에서의 변수사용
========================================================
```java
day2
package day2;

public class VariableTask {
	public static void main(String[] args) {
		//이름
		//나이
		//키
		//회사등급(A~F)
		String name="오예림";
		int age=22;
		double height=162.0;
		char AtoF='A';
		System.out.print("이름 : ");
		System.out.println(name);
		
		System.out.print("나이 : ");
		System.out.print(age);
		System.out.println("살");
		
		System.out.print("키 : ");
		System.out.print(height);
		System.out.println("cm");
		
		System.out.print("회사 등급 : ");
		System.out.print(AtoF);
		System.out.println("등급");
	
	}


}
```



==============================================================

서식문자-항상 따옴표 안에서 사용한다.
printf 
f : format 형식, 초기화 -> 컴퓨터가 파일들을 하나씩 수정하고 갖고있을 때 마다


<종류>
%d  : decimal, 정수->10진법//o랑 x는 8진법, 16진법 
%o  : octal, 정수 8진수
%x  : hecadecimal, 16진수
%f   : float, 실수
%c  : char, 문자
%s  : String, 문자열

=================================================================
```java
	//System.out.printf("이름 : %s","오예"); 도 된당
	System.out.printf("이름 : %s 입니다.\n",name);
	System.out.printf("나이 : %d\n",age);
	System.out.printf("키 : %.1f\n",height);
	//.은 소수점 뒤에 숫자는 자릿수 + 반올림 적용된다~~
	System.out.printf("회사등급 : %c\n",AtoF);
	//대행문자 제어문자 따옴표안에서 써서 줄바꿈 해주자
```

=================================================================

<형 변환>

-자동 형변환 
  정수 정수 : 정수
  정수 실수 : 실수
  문자 정수 : 정수

-강제 형변환 (Casting)
  캐스팅-확 바뀐다
  (자료형) 값

==================================================================


```java
package day2;
import java.util.Scanner;
public class Encryption {

	public static void main(String[] args) {
		// TODO Auto-generated method stub]
		String pw=null;
		System.out.print("PW : ");
		pw=new Scanner(System.in).next();
		System.out.print("암호화 된 PW: ");
		for(int i=0;i<pw.lenght();i++) {
			System.out.printf("%c",pw.charAt(i)-10);
		}

	}

}
```


====================================================================
입력 함수

메모장의 커서가 깜빡인다-->입력상태다. 커서가 깜빡이고 있는 상태
입력하기 전에 무엇을 입력해야 할지 사용자에게 알려줘야 함.

Scanner sc = new Scanner(System.in);
sc라는 저장공간에 new Scanner(System.in);이런 값이 들어간것

클래스 안에 메서드가 있다.
메서드를 사용하기 위해서 변수를 만들었다.

외부에서 스캐너를 들고온다.
개발자에게 필요한 도구들, 프로젝트를 만들때마다 jre라는 것에 라이브러리가 생겨,
스캐너를 찾아오자

=====================================================================


Scanner sc = new Scanner(System.in);
타입     변수명     값

클래스에 있는 메서드에 접근하기 위해서 sc라는 이름의 저장공간을 만들고 그안에 값을 넣는다

변수명.메서드()로 사용한다,
next():내가 입력한 값(타입은 문자열이다)

공백 또는 \n(엔터)를 구분점으로 삼고 각가의 값을 각각의 next()로 봐야한다.

통채로를 내가 입력한 문자열 값으로 봐야한다.

String name= sc.nextLine();
공백까지도 한줄로 판단해서 한 줄 그대로를 입력받는것이 nextLine

==================================================================
​	
```java
	Scanner sc= new Scanner(System.in);
	
	int num1=0,num2=0,result=0;
	System.out.println("첫번째 정수 :");
	num1=sc.nextInt();
	System.out.println("두번째 정수 :");
	num2=sc.nextInt();
	result=num1+num2;
	System.out.printf("%d + %d = %d",num1,num2,result);
```
==================================================================
	Scanner sc = new Scanner(System.in);	
		String numMsg="두정수를 공백으로";
// 메세지를 변수로 넣어놓ㄷ아야 나중에 다시 변경할 때 하나하나 바꾸지 않아도 돼서 꿀꿀
		int num1 = 0, num2 = 0;
		int result=0;
		
		System.out.println(numMsg);
		num1 = Integer.parseInt(sc.next());
		num2= Integer.parseInt(sc.next());
		result=num1+num2;
		System.out.printf("%d+%d=%d",num1,num2,result);
=================================================================


대화상자
JOptionPane.showInputDialog("이름을 입력하세요");
=================================================================


```java
package day2;

import javax.swing.JOptionPane;

public class InputTest2 {

	public static void main(String[] args) {
		String name="";
		
		name=JOptionPane.showInputDialog("이름을 입력하세요");
		JOptionPane.showMessageDialog(null,"이름 : "+ name);

	}

}
```


==================================================================
```java
name=JOptionPane.showInputDialog("숫자를 입력하세요");
	JOptionPane.showMessageDialog(null,"합 : "+ name);
	String n1Msg="첫번째 정수를 입력하세요";
	String n2Msg="두번째 정수를 입력하세요";
	
	num1=Integer.parseInt(JOptionPane.showMessageDialog(n1Msg));
	num2=Integer.parseInt(JOptionPane.showMessageDialog(n2Msg));	
    
	result=num1+num2;
	
	JOptionPane.showMessageDialog(null,num1+"+"+num2+"="+result);
```
==================================================================

연산자
기능이 있는 특수문자를 연산자라고 한다.

최우선 연산자
단항 연산자
산술 연산자
쉬프트 연산자
관계 연산자
논리 연산자
삼항 연산자
대임 연산자

(최단산쉬관리삼대)
================================================================
비트 연산

and & : 둘다 1일때 1
or |  : 둘 중 하나라도 1일 때 1
xor  : 두 비트 숫자가 다를 때 1
^     : ~a=-a-1

//빅데이터는 비트연산 잘 알고 있어야햄

System.out.println(10|11);

==============================================
not 
~
0을 1로 
1을 0으로 만들어주는 것
================================================
shift연산
비트가 이동된다는 것

좌시프트는 값이 커질 수!도 있다
우시프트는 무조건 값이 작아진다
과연 속도만 빠르게 해주려고 시프트연산을 사용할까?
놉


<<로 엄청큰수넣어서 포멧시켜버리는 해킹방법

포렌식->복구 : 좌시프트를 한다고해도 내부적으론 있는 것.
그만큼 우시프트한다

=================================================

a<<b  : a를 b만큼 좌로 비트 이동
a>>b  : a를 b만큼 우로 비트 이동

비어 있는 칸은 0으로 채워 지고 넘어가는 비트는 자동으로 잘린다,.
양수 : 0
음수 : 1

=================================================
면접때 이론적으로 설명하는 법이 필요해

조건식 : 결과가 참 또는 거짓으로 단 2개만 나오는 식

a>0 : 응 또는 아니

비교 연산자
==  : 같다. =은 대입연산자로 우측의 값을 좌측에 넣어주는 것
!=   : 같지 않다.
>,< : 초과, 미만
>=,<= : 이상, 이하

논리 연산자
&& :AND --> A와 B모두 참일 때 참
||  :OR --> 둘 중에 하나라도 참이면 참
!    :!A --> 참이면 거짓으로 거짓이면 참으로 바꾸어주는 것 (단항연산자)

========================================================
boolean
0과 1은 1비트
boolean은 1바이트-->낭비? : 정보의 최소단위는 바이트이기 때문에 어쩔 수 없이 바이트를 사용하는거야
그런데 1비트만 사용해도 충분히 할 수 있다는 것을 알면 돼.






