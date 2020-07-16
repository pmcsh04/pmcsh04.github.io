---
title: 2020-01-07, 2020년 동계모각코 2회차 - 결과
date: 2020-01-07 22:10:00 +0900
category: 2019 동계 모각코
---

오늘은 단어뒤집기 2와 쇠막대기 문제를 풀었습니다.     
첫번째코드는 단어뒤집기 2 입니다.  

~~~java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStreamWriter;
import java.util.Stack;

public class Baekjoon_17413 {

   public static void main(String[] args) throws IOException {
      // TODO Auto-generated method stub
      BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
      BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(System.out));

      String s = bf.readLine();
      Stack<Character> st = new Stack<>();
      boolean tag = false;
      // StringBuilder sb = new StringBuilder();

      for (char a : s.toCharArray()) {
         if (a == '<') {
            while (!st.isEmpty()) {
               bw.write(st.pop());
            }
            bw.write(a);
            tag = true;

         } else if (a == '>') {
            bw.write(a);
            tag = false;
         } else if (tag) {
            bw.write(a);
         } else if (a == ' ') {
            while (!st.isEmpty()) {
               bw.write(st.pop());
            }
            bw.write(a);
         } else {
            st.push(a);
         }

      }
      while (!st.isEmpty())
         bw.write(st.pop());

      bw.flush();
   }

}
~~~

두번째 문제는 쇠막대기 문제입니다.   

~~~java
import java.util.Scanner;
//10799
public class Baekjoon_10799 {
	public static void main(String args[]) {
		Scanner sc = new Scanner(System.in);

		String str = sc.next();
		String[] arr = str.split("");
		int cnt = 0 ;

		for(int j=0; j<arr.length; j++) {

			if(arr[j].equals("(")) {
				cnt++;
			}else if(arr[j].equals(")")) {
				cnt--;
			}

			if(cnt<0) {
				System.out.println("NO");
				break;
			}
		}

		if(cnt>=0)
			System.out.println(cnt>0? "NO":"YES");
	}
}

~~~

첫시간에는 익숙하지 않아서 조금 힘들었는데   
두번째 시간의 스택은 첫번째 시간보다는 어렵다고 하지만   
익숙해져서 잘 풀었던 것 같습니다.   
영어 회화는 다음주부터 주제를 정하고 발표하기로 했습니다.   
다음 주에는 신년 계획을 주제로 발표하려고 합니다.   
