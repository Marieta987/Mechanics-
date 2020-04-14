# Mechanics


package com.company;
import java.util.Scanner;
public class Main {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Input parameters for first ber");

        System.out.println("Input m1");
        float m1 = sc.nextFloat();
        System.out.println("Input nyu1");
        float nyu1 = sc.nextFloat();
        System.out.println("Input F");
        float F1 = sc.nextFloat();

        //Second ber

        System.out.println("the second ber ");
        System.out.println("Input m1");
        float m2 = sc.nextFloat();
        System.out.println("Input nyu2");
        float nyu2 = sc.nextFloat();

       // Third ber

        System.out.println("the third ber");
        System.out.println("Input m3");
        float m3 = sc.nextFloat();
        System.out.println("Input nyu3");
        float nyu3 = sc.nextFloat();

        //time
        System.out.println("Input time");
        int time = sc.nextInt();



        //int G = 10;
        float M = m1 + m2 + m3;






        System.out.println("printing a1 " + computeA1(M,nyu1,F1));

        System.out.println("printing a2 " + computeA2(m2,nyu2));

        System.out.println("printing a3 " + computeA3(m3,nyu3));


        float A1 = computeA1(M,nyu1,F1);
        float A2 = computeA2(m2,nyu2);
        float A3 = computeA3(m3,nyu3);


        System.out.println(position(A1,time));
        System.out.println(position(A2,time));
        System.out.println(position(A3,time));





    }


    public static boolean checkF(float F ){
        if(F>=-300|| F<=300){
            return true;
        }
        return false;
    }
    public static boolean checkM (float m){
        if (m<=10||m>0){
            return true;
        }
        return false;
    }
    public static boolean checkNyu(float nyu){
        if(nyu>=0||nyu<=0.5){
            return true;
        }
        return false;
    }
//If M1 = M2 = M3 a = 1/5g;


    public static float computeA1 (float M,float nyu,float F){

        float N = M * 10;
        float F_force = nyu * M;
        if(checkF(F)==true&& checkNyu(nyu)){
        return (M*10 + F_force  + F + N)/M;}
        else return 0;
}
public static float computeA2 (float m2,   float nyu){

        int g = 10;

        float N = m2 * g;
    float F_force = nyu* N;
    if(checkNyu(nyu)==true && checkM(m2)==true)
        return (m2*10+ F_force + N)/m2;
    else return 0;
}

public static float computeA3 (float m3,float nyu){

        int g = 10;
        float N = m3 * g;
        float F_force = nyu*N;
        if(checkM(m3)==true&&checkNyu(nyu)==true)
        return (m3 * g + F_force )/ m3;
        else return 0;

}


public static float position(float A,int t){
       return (A*t*t)/2;
}






}
