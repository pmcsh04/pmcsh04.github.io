---
title: 2020-01-16, 2020년 동계모각코 5회차 - 결과
date: 2020-01-16 22:10:00 +0900
tags:
    - blog

---

오늘은 오르막수와 스티커문제를 풀었습니다.     
첫번째코드는 오르막수 입니다.  

~~~java
package b_다이나믹프로그래밍1도전;
import java.util.*;
import java.math.*;

public class B_3_오르막수 {
    public static long mod = 10007;
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        long[][] d = new long[n+1][10];
        for (int i=0; i<=9; i++) {
            d[1][i] = 1;
        }
        for (int i=2; i<=n; i++) {
            for (int j=0; j<=9; j++) {
                for (int k=0; k<=j; k++) {
                    d[i][j] += d[i-1][k];
                    d[i][j] %= mod;
                }
            }
        }
        long ans = 0;
        for (int i=0; i<10; i++) {
            ans += d[n][i];
        }
        ans %= mod;
        System.out.println(ans);
    }
}
~~~

두번째 문제는 스티커 문제입니다.   

~~~java
package b_다이나믹프로그래밍1도전;
import java.util.Scanner;
public class B_4_스티커 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int t = sc.nextInt();
		for(int i = 1 ; i<=t;i++) {
			int p = sc.nextInt();
			int [][] a = new int[2][p+1];
			int [][] q = new int[p+1][3];
			for(int b=1; b<=p;b++) {
				a[1][b]=sc.nextInt();
			}
			for(int b=2; b<=p;b++) {
				a[2][b]=sc.nextInt();
			}

			for(int j=1; j<=p;j++) {
				q[j][0]=q[j-1][0]+q[j-1][1]+q[j-1][2];
				q[j][1]=q[j-1][0]+q[j-1][2];
				q[j][2]=q[j-1][0]+q[j-1][1];
			}
			System.out.print(Math.max(q[p][0],Math.max(q[p][1],q[p][2])));
		}
	}

}
~~~

포도주 시식까지는 풀지 못하였습니다.   
도전 문제는 초반 문제들은 쉬웠는데 생각하는 부분이 조금 많아서 헤깔렸습니다.   
이 문제들을 잘 정리해서 똑같은 문제들이 나오면 꼭 풀도록 할 것입니다.   
영어 회화 시간에 강점과 약점을 발표했습니다.        
역시나 말하기가 힘들었는데 조금더 용기를 가지고 발표해야겠다고 생각하였습니다.   
