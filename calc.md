
+package com.lansin.test;
+
+import java.util.Scanner;
+
+public class Calc {
+	public static void main(String[] args) {
+		Scanner input=new Scanner(System.in);
+		int a=input.nextInt();
+		String c=input.next();
+		int b=input.nextInt();
+		System.out.println( a + c +b+"=");
+		int result=new Calc().getResult(a, c, b);
+		System.out.println(result);
+	}
+	public int getResult(int x,String s,int y) {
+		int result=0;
+		if (s.equals("+")) {
+			result=x+y;
+		}else if (s.equals("-")) {
+			result=x-y;
+		}else if (s.equals("*")) {
+			result=x*y;
+		}else if (s.equals("/")) {
+			result=x/y;
+		}
+		return result;
+	}
+}
+  
