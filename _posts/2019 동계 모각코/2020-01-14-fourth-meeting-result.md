---
title: 2020-01-14, 2020년 동계모각코 4회차 - 결과
date: 2020-01-14 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 연속합과 제곱수의 합과 합분해 문제를 풀었습니다.     
첫번째코드는 연속합 입니다.  

~~~java
package b_다이나믹프로그래밍1;
//11053
import java.util.Scanner;

public class B_9_ㅎ_연속합 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int a[]= new int [n];
		for(int i = 0; i<n; i++) {
			a[i] = sc.nextInt();
		}

		int [] d = new int[n];

		for(int i = 0; i<n;i++) {
			d[i]=1;
			for(int j=0; j<i; j++) {
				if(a[j]<a[i] && d[i] <d[j]+1) {
					d[i] = d[j]+1;
				}
			}
		}

		int v[] = new int [n];
		for(int i=0; i<n; i++) {
			v[i] = -1;
		}

		for(int i=0; i<n; i++) {
			for(int j=0; j<i; j++) {
				if(d[i]<d[i+1])
					v[i] += a[i];				
			}

		}

		int ans = v[0];
		for(int i=0; i<n;i++) {
			if(ans <v[i]) {
				ans =v[i];
			}
		}
		System.out.println(ans);
	}
}


~~~

두번째 문제는 제곱수의 합 문제입니다.   

~~~java
package b_다이나믹프로그래밍1;
//1699
import java.util.*;
import java.lang.Math;
public class B_9_ㅎ_제곱수의합 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int count = 0;
		while(n>=0) {
			if((n-(Math.pow(Math.floor((Math.sqrt(n))),2))>0)) {
				count++;
				n-=Math.pow(Math.floor((Math.sqrt(n))),2);

			}else {
				count++;
				break;
			}
		}
		System.out.println(count);
	}
}

~~~

세번째 문제는 합분해 문제입니다.   

~~~java
package b_다이나믹프로그래밍1;

import java.util.Scanner;
public class B_9_ㅎ_합분해 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int k = sc.nextInt();
		int a[][] = new int[n+1][k+1];
		a[0][0]=1;
		for(int i=1;i<=n;i++) {
			for(int j=1; j<=n;j++) {
				a[i][j] = a[n-i][k-1]+a[i][1];				
			}

		}
		System.out.println(a[n][k]);
	}


}


~~~

연속합 문제는 조금 어려웠는데 저런 문제를 과거에도 풀어 봤었는데 이런 문제를 잘 못푸는 것 같아 연습이 필요 한 것 같습니다.   
지난 학기에 알고리즘때 DP에 대해서 공부를 했었는데 이번 기회에 확실히 정리 한 것 같아서 좋습니다.   
영어 회화 시간에 자기소개 발표 했는데 영어로 말하려니 단어가 생각이 안나고 힘들었습니다.     
영어 회화도 착실히 준비해가야겠다고 생각하였습니다.
