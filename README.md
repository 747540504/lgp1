# lgp1
package java1;

import java.util.Scanner;

public class java01 {
	public static void main(String[] args){
		Scanner in=new Scanner(System.in);
		System.out.println("请输入年份：");
		int year=in.nextInt();
		System.out.println("请输入月份：");
		int month=in.nextInt();
		int sum=0;
		for(int i=1900;i<year;i++){
			if(i%4==0&&i%100!=0||i%400==0){
				sum=sum+366;
			}else{
				sum=sum+365;
			}
		}
		for(int j=1;j<month;j++){
			if(j==2){
				if(year%4==0&&year%100!=0||year%400==0){
					sum=sum+29;
				}else{
					sum=sum+28;
				}
			}if(j==4||j==6||j==9||j==11){
				sum=sum+30;
			}else{
				sum+=31;
			}
		}
		sum+=1;
		int wekday=sum%7;
		System.out.println("日\t一\t二\t三\t四\t五\t六");
		for(int i=1;i<=wekday;i++){
			System.out.print("\t");
			}
		for(int i=1;i<=30;i++){
			if(sum%7==6){
				System.out.print(i+"\n");
			}else{
				System.out.print(i+"\t");
			}
			sum++;
		}
	}
}
