```
package com.stacks;

import java.util.Stack;
import java.util.StringTokenizer;

public class InfixToPostfix {
    boolean isOperator(char op){
    	return (op=='+'||op=='-'||op=='*'||op=='/'||op=='^'||op=='('||op==')');
    }
    boolean isSpace(char op){
    	return op==' ';
    }
    boolean lowerPrecedence(char op1,char op2){
    	switch(op1){
    	case '+':
    	case '-':
    		 return !(op2=='+'||op2=='-');
    	case '*':
    	case '/':
    		 return op2=='^'||op2=='(';
    	case '^':
    		 return op2=='(';
    	case '(':
    		 return true;
    	default:
    		 return false;
    	}
    }
    String convertToPostFix(String infix){
    	Stack opStack = new Stack();
    	char ch;
    	StringTokenizer parser = new StringTokenizer(infix,"+-*/^() ",true);
    	 StringBuffer postfix = new StringBuffer(infix.length());
    	while (parser.hasMoreTokens()) {     
            
            String token = parser.nextToken();         
                                                              
            ch = token.charAt(0);         
    
            if ( (token.length() == 1) && isOperator(ch) ) {    
            	 while (!opStack.empty() &&
                         !lowerPrecedence(((String)opStack.peek()).charAt(0), ch))
                        // (Operator on the stack does not have lower precedence, so
                        //  it goes before this one.)
                    
                        postfix.append(" ").append((String)opStack.pop());

                     if (ch==')') {
                        // Output the remaining operators in the parenthesized part.
                           String operator = (String)opStack.pop();
                           while (operator.charAt(0)!='(') {
                              postfix.append(" ").append(operator);
                              operator = (String)opStack.pop();  
                           }
                     }
                     else
                        opStack.push(token);// Push this operator onto the stack.
          
                  }
                  else if ( (token.length() == 1) && isSpace(ch) ) {    // else if
                                                               // token was a space
                    ;                                                  // ignore it
                  }
                  else {  // (it is an operand)
                    postfix.append(" ").append(token);  // output the operand
                  }//end if
        
                }// end while for tokens
        
            // Output the remaining operators on the stack.
               while (!opStack.empty())
                  postfix.append(" ").append((String)opStack.pop());
            
            // Return the result.

               return postfix.toString();


          }//end convertToPostfix

    
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		 String[] testString = {"2 + 3 * 4 / 5", 
                 "2*3 - 4 + 5 / 6",
                 " 35 - 42* 17 /2 + 10",
                 " 33.2 - 17.5 * 2.0 ^ 3.2",
                 "3 * (4 + 5)",
                 "3 * ( 4 - (5+2))/(2+3)"};

InfixToPostfix converter = new InfixToPostfix();

System.out.println("\nTest for convertToPostfix:\n");

for (int i=0; i<testString.length; i++) {
System.out.println("infix: " + testString[i]);
System.out.println("postfix: " + converter.convertToPostFix(testString[i]));
System.out.println();
}
	}

}


```
