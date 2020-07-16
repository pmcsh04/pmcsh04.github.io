---
title: 2020-01-30, 2020년 동계모각코 7회차 - 결과
date: 2020-01-30 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 테크로미노와 카잉달력 문제를 풀었습니다.     
첫번째코드는 테크로미노 문제 입니다.  

~~~java
package b_브루트포스;
//14500 틀린코드
import java.util.Scanner;
public class B_5_테트로미노 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);

		int n = sc.nextInt();
		int m = sc.nextInt();

		int a [][] = new int [n][m];
		for(int i=0;i<n;i++) {
			for(int j=0;j<m;j++) {
				a[i][j] = sc.nextInt();
			}
		}
		int max = 0;

		for(int i=0;i<n;i++) {
			for(int j=0;j<m-3;j++) {
				int p = a[i][j]+a[i][j+1]+a[i][j+2]+a[i][j+3];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-3;i++) {
			for(int j=0;j<m;j++) {
				int p = a[i][j]+a[i+1][j]+a[i+2][j]+a[i+3][j];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j]+a[i][j+1]+a[i+1][j]+a[i+1][j+1];
				if(p>max) {
					max = p;
				}
			}
		}


		for(int i=0;i<n-2;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j]+a[i+1][j]+a[i+2][j]+a[i+2][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-2;j++) {
				int p = a[i][j]+a[i][j+1]+a[i][j+2]+a[i+1][j];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-2;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j]+a[i][j+1]+a[i+1][j+1]+a[i+2][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-2;j++) {
				int p = a[i+1][j]+a[i+1][j+1]+a[i+1][j+2]+a[i][j+2];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-2;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j]+a[i+1][j]+a[i+1][j+1]+a[i+2][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-2;j++) {
				int p = a[i][j+1]+a[i][j+2]+a[i+1][j]+a[i+1][j+1];
				if(p>max) {
					max = p;
				}
			}
		}

		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-2;j++) {
				int p = a[i][j]+a[i][j+1]+a[i][j+2]+a[i+1][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-2;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j+1]+a[i+1][j+1]+a[i+1][j]+a[i+2][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-1;i++) {
			for(int j=0;j<m-2;j++) {
				int p = a[i][j+1]+a[i+1][j]+a[i+1][j+1]+a[i+1][j+2];
				if(p>max) {
					max = p;
				}
			}
		}
		for(int i=0;i<n-2;i++) {
			for(int j=0;j<m-1;j++) {
				int p = a[i][j]+a[i+1][j]+a[i+2][j]+a[i+1][j+1];
				if(p>max) {
					max = p;
				}
			}
		}
		System.out.println(max);
	}
}

~~~

두번째 문제는 카잉달력 문제입니다.   

~~~java
package b_브루트포스;

import java.util.Scanner;
public class B_6_카잉달력 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();

		for(int i=0;i<n;i++) {

			for(int j=0;j<=3;j++) {
				int M = sc.nextInt();
				int N = sc.nextInt();
				int x = sc.nextInt();
				int y = sc.nextInt();

				int X = 1;
				int Y = 1;
				boolean ok = false;
				for(int p=1;p<20000;p++) {
					if(X==x && Y==y) {
						System.out.println(p);
						ok = true;
						break;
					}


					X+=1;
					Y+=1;
					if(X == M+1) {
						X=1;
					}
					if(Y == N+1) {
						Y=1;
					}

				}
				if(!ok) {
					System.out.println(-1);
				}
			}
		}
	}

}
~~~
카잉 달력 문제는 별로 어렵지 않았던 것 같습니다.   
숙제로 풀어온 문제랑 비슷했기 때문입니다.    
그런데 테트로미노 문제는 예전에 수업시간에 했던 문제랑 비슷해서 잘 풀줄 알았는데   
막상 코드를 돌려보니 답이 나오지 않았습니다.   
다음주까지 다시 문제를 풀어 보려고 합니다.   
