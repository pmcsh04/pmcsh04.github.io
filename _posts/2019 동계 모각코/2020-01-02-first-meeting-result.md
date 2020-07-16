---
title: 2020-01-02, 2020년 동계모각코 1회차 - 결과
date: 2020-01-02 20:55:00 +0900
category: 2019 동계 모각코
---
첫번째 모각코 시간에는 계획을 세웠습니다.   
우선, 백준이랑 영어회화를 한다고 했었는데   
백준은 알고리즘을 복습하고 그거에 맞는 백준 문제를 푸는 것으로 하였습니다.    
영어회화는 아직 정하지 못해서 좀 더 고민중입니다.   

오늘은 스택 2문제를 풀었습니다.   
첫번째 스택문제를 올리겠습니다.   

~~~java
import java.util.Scanner;

public class Baekjoon_10828 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int size = 0;
		int [] a = new int[n];

		while(n > 0) {
			String p = sc.next();

			if(p.equals("push")){
				int x = sc.nextInt();
				a[size] = x;
				size++;
			}else if(p.equals("pop")) {
				if(size == 0) {
					System.out.println(-1);
				}else {
					System.out.println(a[size-1]);
					size--;
				}
			}else if(p.equals("size")) {
				System.out.println(size);
			}else if(p.equals("empty")) {
				if(size == 0) {
					System.out.println(1);
				}else {
					System.out.println(0);
				}
			}else if(p.equals("top")) {
				if(size == 0) {
					System.out.println(-1);
				}else {
					System.out.println(a[size-1]);
				}
			}
			n--;
		}
	}
}
~~~

두번째 문제는 문장을 받고 단어마다 글자를 거꾸로 바꾸는 문제입니다.   
저에게는 좀 어려웠던 문제였습니다.   

~~~java
import java.util.Scanner;
import java.util.Stack;

public class Baekjoon_9093 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);
		int T = sc.nextInt();
		sc.nextLine(); // 엔터값 없애기.

		for(int i = 0; i<T ; i++) {
			Stack<Object> stack = new Stack<>();
			String str = sc.nextLine();

			for(int j=0; j<str.length();j++) {
				char c = str.charAt(j);

				if(c ==' ') { // 띄어쓰기이면
					while(!stack.empty()) {
						System.out.print(stack.pop()); // 스택이 비어있을때 까지 pop
					}
					System.out.print(" ");
				}else { // 띄어쓰기가 아니면
					stack.add(str.charAt(j)); // 스택에 추가.
				}
			}
			/*
			 * 밑에는 엔터때매 첨가한 것이라 생각된다.
			 */
			while(!stack.empty()) { // 스택이 비어있을때 까지
				System.out.print(stack.pop()); //  빼낸다.
			}
			System.out.println();
		}
		sc.close();
	}
}
~~~

첫번째 시간에는 스택 위주로 문제를 풀었고
두번째 시간부터는 미리 관련 개념들을 정해놓고 공부해와서   
모각코 시간에 문제를 푸는 것으로 하려고 합니다.   
