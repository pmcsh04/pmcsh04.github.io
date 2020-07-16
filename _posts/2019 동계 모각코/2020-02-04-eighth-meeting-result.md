---
title: 2020-02-04, 2020년 동계모각코 8회차 - 결과
date: 2020-02-04 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 N과 M 1 과 N과 M 2 문제를 풀었습니다.     
첫번째코드는 N과 M 1 입니다.  

~~~java
package B_브루트포스N과M;
import java.util.*;
public class B_N과M1 {
   static boolean[] c = new boolean[10]; // c-> 그 수가 사용되었는지 기록. 0~9
    static int[] a = new int[10]; // a-> 결과 0~9

    static void go(int index, int n, int m) {
    	if (index == m) { // m-1까지 있으므로 m일때는 출력
            for (int i=0; i<m; i++) {
                System.out.print(a[i]);
                if (i != m-1) System.out.print(' ');
            }
            System.out.println();
            return;
        }

        for (int i=1; i<=n; i++) { // n은 사용할 수 있는 숫자.
        	if (c[i]) continue; // c[i]가 true이면 (c[i]가 사용한 숫자이면) 건너뛴다.
        	c[i] = true; // 사용.
            a[index] = i; // 이걸 사용했다
            go(index+1, n, m); // 다음 인덱스로 가자.
            c[i] = false; // 끝나면 다시 false.
        }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();

        go(0,n,m);
    }
}
~~~

두번째 문제는 N과 M 2 문제입니다.   

~~~java
package B_브루트포스N과M;
import java.util.*;
public class B_N과M2 {
   static boolean[] c = new boolean[10]; // c-> 그 수가 사용되었는지 기록. 0~9
    static int[] a = new int[10]; // a-> 결과 0~9
    static void go(int index,int start, int n, int m) {
    	if (index == m) { // m-1까지 있으므로 m일때는 출력
            for (int i=0; i<m; i++) {
                System.out.print(a[i]);
                if (i != m-1) System.out.print(' ');
            }
            System.out.println();
            return;
        }

        for (int i=start; i<=n; i++) { // n은 사용할 수 있는 숫자.
        	if (c[i]) continue; // c[i]가 true이면 (c[i]가 사용한 숫자이면) 건너뛴다.
        	c[i] = true; // 사용.
            a[index] = i; // 이걸 사용했다
            go(index+1,i+1, n, m); // 다음 인덱스로 가자.
            c[i] = false; // 끝나면 다시 false.
        }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();
        go(0,1,n,m);
    }
~~~

N과 M시리즈는 12문제가 있습니다.  
이 중 아직 두 문제밖에 풀지 않았습니다.     
저한테는 좀 어려운 문제였고 이렇게 풀 수 있다는 방법을 알고나니 좀 더 노력해야겠다고 생각이 들었습니다.   
아직 많이 부족하다는 것을 알았고, 남은 10문제들도 비슷한 방법으로 풀 수 있으니 계속 풀어봐야 할 것 같습니다.   
