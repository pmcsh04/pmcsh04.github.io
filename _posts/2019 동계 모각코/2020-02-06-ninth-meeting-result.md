---
title: 2020-02-06, 2020년 동계모각코 9회차 - 결과
date: 2020-02-06 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 N과 M 5 과 N과 M 6 문제를 풀었습니다.     
첫번째코드는 N과 M 5 입니다.  

~~~java
package B_브루트포스N과M;

import java.util.*;
public class B_N과M5 {
    static boolean[] c = new boolean[10];
    static int[] a = new int[10];
    static int[] num = new int[10]; // 이걸 새로 만듬

    static StringBuilder go(int index, int n, int m) {
        if (index == m) {
            StringBuilder sb = new StringBuilder();
            for (int i=0; i<m; i++) {
                sb.append(num[a[i]]);
                if (i != m-1) sb.append(" ");
            }
            sb.append("\n");
            return sb;
        }
        StringBuilder ans = new StringBuilder();
        for (int i=0; i<n; i++) {
            if (c[i]) continue;
            c[i] = true;
            a[index] = i;
            ans.append(go(index+1, n, m));
            c[i] = false;
        }
        return ans;
    }   
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();
        for (int i=0; i<n; i++) {
            num[i] = sc.nextInt();
        }
        Arrays.sort(num,0,n);
        System.out.print(go(0,n,m));
    }
}

~~~

두번째 문제는 N과 M 6 문제입니다.   

~~~java
package B_브루트포스N과M;

import java.util.*;
public class B_N과M6 {
    static boolean[] c = new boolean[10];
    static int[] a = new int[10];
    static int[] num = new int[10];
    static StringBuilder go(int index,int start, int n, int m) {
        if (index == m) {
            StringBuilder sb = new StringBuilder();
            for (int i=0; i<m; i++) {
                sb.append(num[a[i]]);
                if (i != m-1) sb.append(" ");
            }
            sb.append("\n");
            return sb;
        }
        StringBuilder ans = new StringBuilder();
        for (int i=start; i<n; i++) {
            if (c[i]) continue;
            c[i] = true;
            a[index] = i;
            ans.append(go(index+1,i+1, n, m));
            c[i] = false;
        }
        return ans;
    }   
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();
        for (int i=0; i<n; i++) {
            num[i] = sc.nextInt();
        }
        Arrays.sort(num, 0, n);
        System.out.print(go(0,0,n,m));
    }
}
~~~

이번 N과 M을 푸는 데는 그렇게 오랜 시간이 걸리지 않았습니다.  
지난 8회차때 푼 N과 M 문제가 중요하였고 그것을 이용하여 풀면 되기 때문입니다.     
12번까지 다 N과 M 1,2,3,4를 이용하면 풀 수 있기에 복습하고 남은 문제들을 풀려고 합니다.      
다음 시간이 모각코 마지막 시간입니다.    
