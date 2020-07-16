---
title: 2020-01-09, 2020년 동계모각코 3회차 - 결과
date: 2020-01-09 22:00:00 +0900
tags:
    - blog

---


오늘은 1,2,3 더하기와 카드구매하기 1와 카드 구매하기 2 문제를 풀었습니다.     
첫번째코드는 1,2,3 더하기 입니다.  

~~~java
package b_다이나믹프로그래밍1;
//9095
import java.util.Scanner;

public class B_4_123더하기 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		sc.nextLine();
		int a[] = new int[10001];


		while(T>0) {
			int n = sc.nextInt();

			a[0]=1;
			a[1]=1;
			a[2]=2;

			for(int i=3; i<=n;i++) {
				a[i]=a[i-1]+a[i-2]+a[i-3];			
			}

			System.out.println(a[n]);
			T--;
		}
	}
}
~~~

두번째 문제는 카드구매하기 1 문제입니다.   

~~~java
package b_다이나믹프로그래밍1;
//11052
import java.util.Scanner;
public class B_5_카드구매하기 {
	public static void main(String [] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int P[]=new int[N+1];

		for(int i=1; i<=N;i++) {
			P[i]=sc.nextInt();
		}

		int D[]=new int[N+1];

		for(int i=1;i<=N;i++) {
			for(int j=1; j<=i;j++) {

				if(D[i] <D[i-j]+P[j]) {
					D[i] = D[i-j] + P[j];
				}
			}
		}
		System.out.println(D[N]);
	}
}
~~~

세번째 문제는 카드구매하기 2 문제입니다.   

~~~java
package b_다이나믹프로그래밍1;
//16194
import java.util.Scanner;

public class B_6_카드구매하기2 {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		int N = sc.nextInt();
		int p[]= new int[N+1];

		for(int i = 1; i<=N;i++) {
			p[i]=sc.nextInt();
		}
		int d[] = new int[N+1];

		for(int i = 1; i<=N;i++) {
			d[i] = -1;
			for(int j = 1; j<=i;j++) {
				if(d[i] == -1 || d[i]>d[i-j]+p[j])
					d[i]=d[i-j]+p[j];
			}
		}
		System.out.println(d[N]);
	}
}


~~~

카드 구매하기 문제는 조금 헤깔렸는데 1번문제를 해결하니 다음부터는 잘 풀렸습니다.   
영어 회화는 오늘 신년계획을 발표하였습니다.   
저는 프로그래밍 공부와 영어회화공부, 마지막으로 이번학기 안에 하고싶은 분야 찾기로 신년계획을 발표하였습니다.     
