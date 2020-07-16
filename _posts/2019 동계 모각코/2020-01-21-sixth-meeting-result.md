---
title: 2020-01-21, 2020년 동계모각코 6회차 - 결과
date: 2020-01-21 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 가장 긴 바이토닉 수열과 연속 합 문제를 풀었습니다.     
첫번째코드는 가장 긴 바이토닉 부분 수열 입니다.  

~~~java
package b_다이나믹프로그래밍1도전;
import java.util.Scanner;
public class B_9_가장긴바이토닉부분수열 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int a [] = new int[n];
		for(int i = 0; i<n;i++) {
			a[i]=sc.nextInt();
		}
		int d [] = new int[n];
		int q [] = new int[n];

		for(int i=0; i<n;i++) {
			d[i]=1;
			for(int j=0; j<i; j++) {
				if(a[j]<a[i] && d[i] <d[j]+1) {
					d[i] = d[j]+1;
				}
			}
		}

		for(int i=n-1;i>=0;i--) {
			q[i]=1;
			for(int j=i;j<=n-1;j++) {
				if(a[i]>a[j]&&d[i]<d[j]+1) {
					q[i]=q[j];
				}
			}
		}

		int ans = d[0];
		int ans2 = q[0];
		for(int i=1; i<n;i++) {
			if(ans<d[i]) {
				ans = d[i];
			}
			if(ans<q[i]) {
				ans2 = q[i];
			}
		}
		System.out.println(ans+ans2);

	}
}

}
~~~

두번째 문제는 연속 합 문제입니다.   

~~~java
package b_다이나믹프로그래밍1;
//11053
import java.util.Scanner;

public class B_ㄷ_연속합 {
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
두 문제 다 정해진 시간내에 풀었습니다.   
팀원들이랑 정해진 모각코 문제를 풀면서 알고리즘 실력이 느는 것 같아서 좋았습니다.    
남은 모각코 시간에도 더 열심히 하려고 합니다.    
