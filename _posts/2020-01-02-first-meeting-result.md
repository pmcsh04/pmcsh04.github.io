---
title: 2020-01-02, 2020년 동계모각코 1회차 - 결과
date: 2020-01-02 20:55:00 +0900
tags:
    - blog

---

<blockquote>
<p>
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
</p>
</blockquote>
