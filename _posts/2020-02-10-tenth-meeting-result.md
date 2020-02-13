---
title: 2020-02-10, 2020년 동계모각코 10회차 - 결과
date: 2020-02-10 22:10:00 +0900
tags:
    - blog

---

오늘은 모각코 마지막 시간으로 대회문제 두문제를 풀었습니다.     
첫번째코드는 상금헌터 입니다.  

~~~java
import java.util.Scanner;
public class b_카카오페스티벌_1 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int t = sc.nextInt();

		for(int i=0;i<t;i++) {
			int a = sc.nextInt();
			int b = sc.nextInt();
			int sum = 0;
			if(a==1) {
				sum+=5000000;
			}
			if(a>=2 && a<=3) {
				sum+=3000000;
			}
			if(a>=4 && a<=6) {
				sum+=2000000;
			}
			if(a>=7 && a<=10) {
				sum+=500000;
			}
			if(a>=11 && a<=15) {
				sum+=300000;
			}
			if(a>=16 && a<=21) {
				sum+=100000;
			}
			if(a>=22 && a<=100) {
				a=0;
			}

			if(b==1) {
				sum+=5120000;
			}
			if(b>=2 && b<=3) {
				sum+=2560000;
			}
			if(b>=4 && b<=7) {
				sum+=1280000;
			}
			if(b>=8 && b<=15) {
				sum+=640000;
			}
			if(b>=16 && b<=31) {
				sum+=320000;
			}
			if(b>=32 && b<=100) {
				b=0;
			}
			System.out.println(sum);
		}
	}
}

~~~

두번째 문제는 인형들 문제입니다.   

~~~java
import java.util.*;
import java.lang.Math;
public class b_카카오페스티벌_2 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int k = sc.nextInt();
		int a[] = new int[n];
		double temp=1000000000;

		for(int i=0; i<n; i++) {
			a[i]= sc.nextInt();
		}

		for(int p=0;p<=n-k;p++) {
			double m = 0;
			double v = 0;
			double sigma = 0;

			for(int i=p; i<p+k;i++) {
				m += a[i];
			}
			m = m/k;

			for(int i=p; i<p+k;i++) {
				v+=((a[i]-m)*(a[i]-m));
			}
			v = v/k;
			sigma = Math.sqrt(v);

			if(temp>sigma) {
				temp = sigma;
			}			
		}
		System.out.println(String.format("%.11f", temp));
	}
}
~~~

총 6문제가 있던 카카오페스티벌 문제입니다.   
그 중에서 쉬운 두문제만 한번 풀어보았습니다.    
둘다 괜찮을거라고 생각하였고 풀었는데 2번은 왜 안풀리는지 아직 잘 모르겠습니다.   
다른 사람들이 올려놓은 코드로 공부를 하고 이유를 알아보려고 합니다.   

오늘은 모각코 마지막 시간이 었습니다.   
알고리즘 과목은 제가 제일 못해서 싫어하는 분야중 하나였습니다.      
그러다보니 안하게 되었는데 조원들과 같이 정해놓고 문제를 푸니까 재미도 있고 강제성이 있어서 하게 되었고   
지금도 잘한다고는 할 수 없지만 기초의 실력정도는 생긴것 같아서 좋았습니다.   
많이 배운 것 같아서 좋은 시간이었다고 생각합니다.   
   
