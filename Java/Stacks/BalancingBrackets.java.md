Hackerrank Problem --> https://www.hackerrank.com/challenges/balanced-brackets/
```
package com.stacks;

import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.Stack;

public class BalancingParanthesis {

	public static void main(String[] args) throws Exception {
		// TODO Auto-generated method stub
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		int N = Integer.parseInt(br.readLine()), i, j;
		char ch;
		boolean flag;
		Stack<Character> st = new Stack();
		for (j = 0; j < N; j++) {
			flag = false;
			String str = br.readLine();
			flag = true;
			for (i = 0; i < str.length(); i++) {
				ch = str.charAt(i);
				if (ch == '[' || ch == '{' || ch == '(') {
					st.push(ch);
				} else if (ch == ']' || ch == ')' || ch == '}') {
					// System.out.println(st);
					if (st.isEmpty() || (ch == ']' && st.peek() != '[') || (ch == ')' && st.peek() != '(')
							|| (ch == '}' && st.peek() != '{')) {
						flag = false;
						break;
					}
					st.pop();
				}
			}
			System.out.println(flag && st.isEmpty() ? "YES" : "NO");
			st.clear();
		}

		

	}
}

```
