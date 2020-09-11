# Day 3

삼항 연산자

```java
int result = 조건식 ? true : false
                  1
```
항이 3개 
조건식은 참또는 거짓, 결과가 2개


nextInt 확인

키워드 예약어 자주색 true 와  false (true false의 값의 종류는 논리형)

=============================================================
논리형 자료형의 한 종류

type         byte  값
boolean  1byte true,false(딱 두가지만 들어가는 저장공간)

boolean isBigger = false;

자바에선 삼항연산자에서는 값만 다룰수 있다. 
isBigger?  System.,,,     (X)

boolean isBigger=false; -->초기값 필수
=============================================================
```java
package day3;

import java.util.Scanner;

public class oper2 {

	public static void main(String[] args) {
		Scanner sc =new Scanner(System.in);
		int num1=0, num2=0;
		
		boolean isBigger=false;
		String n1Msg="첫번째 정수 : ";
		String n2Msg="두번째 정수 : ";
		String result;
		
		System.out.print(n1Msg);
		num1=sc.nextInt();
		
		System.out.print(n2Msg);
		num2=sc.nextInt();
		
		isBigger=num1>num2?true:false;
		//정수가 같을 때 는 어떻게 결과를 내야할까?
		
	
		result= isBigger?num1>num2?"첫번째 정수가 더 큽니다.":num1==num2?"두수는 같습니다.":"두번째 정수가 더 큽니다.";
		
		
		System.out.println(result);
		

	}

}
```






```java
package day3;

import java.util.Scanner;

import javax.swing.JOptionPane;

/*
 * Q.다음 중 음식이 아닌 것은?
 * 1.햄버거
 * 2.피자
 * 3.치킨
 * 4.칠판
 */

public class Quiz {

	public static void main(String[] args) {
		//scanner 말고 제이옵션 입력대화상자
		String qMsg="Q.Q.다음 중 음식이 아닌 것은?\n" + 
				" * 1.햄버거\n" + 
				" * 2.피자\n" + 
				" * 3.치킨\n" + 
				" * 4.칠판";
		//전체를 내각 입력한 문자열 값으로 보기!
		
		int yourpick=0;
		boolean isRight=false;
		String result="";
		int answer=4;
		
		yourpick=Integer.parseInt(JOptionPane.showInputDialog(qMsg));//int your pick으로 해버리면 오류가남..ㅜ
		//대화 상자가 나옴
		
		
		result=answer==yourpick? "정답입니다!":yourpick>=1&&yourpick<=4?"정답이 아닙니다!":"?;;";

		
		JOptionPane.showMessageDialog(null,result);
		
		

	}

}
```

​		



조건식이 너무 길어져서 가독성도 떨어지고 불편해요

***************************
```java
       **제어문**

         조건문 
***************************
                      if문-종류2가지 / 첫번째는 그냥 위에서 아래로 검사하는 것 /
                                            두번째는 else, 그게 아니면, 즉 위에서 참나오면 아랜 안본다. = 검사조차하지 않는다. 마지막 else의 조건식
                                             위에가 다 아니면 이란 뜻

   if(조건식){
            실행할 문장
   }
  if(조건식){
            실행할 문장
   }
  if(조건식){
            실행할 문장
   }
------------------------
  if(조건식){
            실행할 문장
   }
  else if(조건식){
            실행할 문장
   }
  else{
          실행할 문장
  }
```

  



```java
package day3;

import java.util.Scanner;

public class ConditionTest {

	public static void main(String[] args) {
		int num1=0,num2=0;
		Scanner sc=new Scanner (System.in);
		
		System.out.print("첫번째 정수");
		num1=sc.nextInt( );
		
		System.out.print("두번째 정수");
		num2=sc.nextInt();
		
		if(num1>num2) {
			System.out.println("첫번째 정수가 더 큽니다~~"); 
		}
		else if(num1<num2) {
			System.out.println("두번째 정수가 더 큽니다~~");
		}
		else {
			System.out.println("두 수가 같아용요요");
		}
		

	}

}
```




```java
package day3;

import javax.swing.JOptionPane;

public class Film {
	public static void name(String[] args) {
	//#s1. 이상형이 식사를 제안할 때
		String qMsg="밥 먹으러 갈래요?";
		String choiceMsg="1.좋아요.\n2.이미 먹었어요.\n3.밥 보다는...\n4.(뺨을 한대 후려치고)그 동안 기다렸어.\n";
		int choice=0;
		
		choice=Integer.parseInt(JOptionPane.showInputDialog(qMsg+choiceMsg));
		
		if (choice==1) {
			JOptionPane.showMessageDialog(null,"넌 너무 쉬워 안녕~");
		}
		else if (choice==2) {
			JOptionPane.showMessageDialog(null,"나도 먹었어.");
		}
		else if (choice==3) {
			JOptionPane.showMessageDialog(null,"입 닫아. 나도 무슨 말인지 알겠어.");
		}
		else if (choice==4) {
			JOptionPane.showMessageDialog(null,"아프다...");
		}
		else {
			JOptionPane.showMessageDialog(null,"다시 한번 말해줄래??");
		}
	}

}
```



너무 반복되는게 많아서 골아퍼,,


```java
   switch 문

switch (변수명){
 case 값1 :
        실행할 문장
        break;

 case 값1 :
        실행할 문장
        break;

 case 값1 :
        실행할 문장
        break;

 case 값1 :
        실행할 문장
        break;
...

 default :
        실행할 문장
}
```

 

-default는 어차피 마지막이어서 쓸 필요 없어
기타연산자 break -해당영역 탈출
스위치문의 단점-비교를 할 수 없고 같은지만 볼 수 잇음, 그리고 두개 이상 쓸 수 없음(if문은 엔드 연산 가능하지만 스위치는 안됌)
==========================================

```java
package day3;

import javax.swing.JOptionPane;

public class Film {
	public static void name(String[] args) {
	//#s1. 이상형이 식사를 제안할 때
		String qMsg="밥 먹으러 갈래요?";
		String choiceMsg="1.좋아요.\n2.이미 먹었어요.\n3.밥 보다는...\n4.(뺨을 한대 후려치고)그 동안 기다렸어.\n";
		int choice=0;
		
		choice=Integer.parseInt(JOptionPane.showInputDialog(qMsg+choiceMsg));
		
//		if (choice==1) {
//			JOptionPane.showMessageDialog(null,"넌 너무 쉬워 안녕~");
//		}
//		else if (choice==2) {
//			JOptionPane.showMessageDialog(null,"나도 먹었어.");
//		}
//		else if (choice==3) {
//			JOptionPane.showMessageDialog(null,"입 닫아. 나도 무슨 말인지 알겠어.");
//		}
//		else if (choice==4) {
//			JOptionPane.showMessageDialog(null,"아프다...");
//		}
//		else {
//			JOptionPane.showMessageDialog(null,"다시 한번 말해줄래??");
//		}
		switch(choice) {
		case 1:
			JOptionPane.showMessageDialog(null,"넌 너무 쉬워 안녕~");
			break;
		case 2:
			JOptionPane.showMessageDialog(null,"나도 먹었어.");
			break;
		case 3:
			JOptionPane.showMessageDialog(null,"입 닫아. 나도 무슨 말인지 알겠어.");
			break;
		case 4:
			JOptionPane.showMessageDialog(null,"아프다...");
			break;
		default :
			JOptionPane.showMessageDialog(null,"다시 한번 말해줄래??");
			//default는 if문의 else와 비슷
			
		}
	}

}
```

​	

-----------------------
누적 연산자
예를 들어서 
 int money =10000;
 money=money-1000; (누적)
 money-=1000;

+=

-=

*=

/=



 int data =10;
 data =data +1;
 data += 1;
 data++;

++:1증가
--:1감소

전위형
++data : 바로 적용된다.

후위형

data++ : 그 다음 줄 부터 적용된다.


-------------------------------------------

```java
     반복문(조건식이 참일 때 반복)
```


이름을 백번 출력하세요 -> 백번 씀
반복문이용시 한번에 가능~

for 문

```java
 0      <5          1  
for (초기값; 조건식; 증감량){
    반복할 문장;
}
```


for 문의 핵심은 변수이다.

int i;
i=0 ; i<5 ; i=i+1
i=0 ; i<5 ; i+=1
i=0 ; i<5 ; i++ (후위형으로쓰나 전위형으로 쓰나 상관이 없다)

========================================

```java
for (int i=65;i<70;i++) {
			System.out.println((char)i);
		}
```
==============================================

```java
	//for문 하나로 구구단을 성공시켜라 총 9단 까지 81번 반복
		//a*b=c
		//a는 9번 고정
		//b는 매 반복마다 1증가 
		//a/10 :0~9  -> 0<a<91    : 0  10번
		//a%10 : 0~9                   : 1  10번 
		//a가 0~9 : 0
		//10~19 :1
		//a %10 : 0~9
		//1단-1이 9번 고정
		
		for (int i=1; i<90 ; i++) {
			if(i%10==0) {
				i++;
			}
			System.out.printf("%d X %d = %d\n",i/10+1,i%10,(i/10+1)*(i%10));
		}
```
-----------------------------------------------------

기타연산자 

break; : 영역 탈출
특정 조건에서 자주 쓰이는 기타연산자

continue : 다음 반복으로 넘어가기 -만나자마자 밑에있는 문장 실행안하고 다음반복으로 넘어가는것


===================================================================================

while문

```java
while (조건식){
      반복할문장
}
```


while문은 변수가 없다!!!!->변화하는 증감량이 필요할땐 for문을 써야한다는 것

while문은 단순한 문장 반복시에 사용된다.
무한반복을 의미한다.

조건식이 참하고 트루라는 상수값-무한반복 ///for도 가능 for(;true;){};
특정조건에서 break써서 탈출

=========================================================================================
```java
	String qMsg="[나가기 : x입력]\nQ.다음 중 음식이 아닌 것은?\n" + 
				" * 1.햄버거\n" + 
				" * 2.피자\n" + 
				" * 3.치킨\n" + 
				" * 4.칠판";
		//전체를 내각 입력한 문자열 값으로 보기!
		
		String yourpick="";
		String result="";
		String answer="4";
		
		
		
		while(true) {
			yourpick=JOptionPane.showInputDialog(qMsg);//int your pick으로 해버리면 오류가남..ㅜ
			//대화 상자가 나옴
			
			if (yourpick.equals("X")||yourpick.equals("x")) break;
			
			result=yourpick.equals(answer)? "정답입니다!":Integer.parseInt(yourpick)>=1&&Integer.parseInt(yourpick)<=4?"정답이 아닙니다!":"?;;";

			
			JOptionPane.showMessageDialog(null,result);
			
		}
```


​		
