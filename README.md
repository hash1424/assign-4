# assign-4
14feb


package com.company;

public class FEB14 {
    public static int busyStudent(int[] startTime, int[] endTime, int queryTime) {
        //"1.) https://leetcode.com/problems/number-of-students-doing-homework-at-a-given-time/
        int result = 0;
        for (int i = 0; i < startTime.length; i++) {
            result += startTime[i] <= queryTime && queryTime <= endTime[i] ? 1 : 0;
        }
        return result;
    }

    public int[] runningSum(int[] nums) {
    
    
        //2.) https://leetcode.com/problems/running-sum-of-1d-array/
        for (int i = 1; i < nums.length; i++) {
            nums[i] += nums[i - 1];
        }
        return nums;
    }

    public static void main(String[] args) {
        /*3.)  Given two arrays, find the intersection between them?
        Input : int[]  arr1 = {1, 2, 3, 4, 5, 6};
        int[] arr2 = {2, 3, 4, 7, 8};
        Output : { 2, 3, 4}*/

        int[] arr1 = {1, 2, 3, 4, 5, 6};   
        int[] arr2 = {2, 3, 4, 7, 8};
        int i = 0;
        int j = 0;
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] == arr2[j]) {
                System.out.print(arr1[i]);      
                i++;
                j++;
            } else if (arr1[i] > arr2[j]) {
                j++;
            } else {
                i++;
            }
        }
    }

    private static void secLargest() {
        //Java Program to find Second Largest Number in an Array

        int integers[] = {12, 34, 55, 3, 4, 66};
        int max = integers[0];
        int secondmax = integers[0];

        for (int i = 0; i <= 5; i++) {
            if (integers[i] > max) max = integers[i];
        }
        for (int i = 0; i <= 5; i++) {
            if (integers[i] > secondmax && integers[i] < max) secondmax = integers[i];
        }
        System.out.println(" the maximum number is: " + max + "\n the second maximum number is:" + secondmax);

    }
}




15feb


package com.company;
import java.util.Arrays;
import java.util.List;
import java.util.*;

public class FEB15<vector> {
    public static void main(String[] args) {}
          public static void spirallyTraverse(int [][]mat ){
              int top = 0, left = 0, bottom = mat.length - 1, right = mat[0].length - 1;
              if (mat == null || mat.length == 0 || left > right)
                  return;
              while (top <= bottom && left <= right) {
                  // for top row
                  for (int i = left; i <= right; i++) {
                      System.out.print(mat[top][i] + " ");
                  }
                  top++;
                  if (top > bottom)
                      return;
                  // for right column
                  for (int i = top; i <= bottom; i++) {
                      System.out.print(mat[i][right] + " ");
                  }
                  right--;
                  if (left > right)
                      return;
                  // print bottom
                  for (int i = right; i >= left; i--) {
                      System.out.print(mat[bottom][i] + " ");
                  }
                  bottom--;
                  if (top > bottom)
                      return;
                  for (int i = bottom; i >= top; i--) {
                      System.out.print(mat[i][left] + " ");
                  }
                  left++;
           }
    }
    private static void addTwoDMatrix(int[][] mat1, int[][] mat2) {
        int res[][]=new int[mat1[0].length][mat1[0].length];
        for(int i=0;i<mat1[0].length;i++) {
            for(int j=0;j<mat2.length;j++) {
                res[i][j]=mat1[i][j]+mat2[i][j];
            }
        }
        print2DMatrix(res);
    }
    private static void print2DMatrix(int[][] mat) {
        for (int[] val: mat) {
            System.out.println(Arrays.toString(val));
        }
    }
    private static void printFirstSecondDiagonal(int[][] mat1) {
        for(int i=0;i<mat1[0].length;i++) {
            for(int j=0;j<mat1.length;j++) {
                if(i+j==mat1.length-1)
                    System.out.print(mat1[i][j]+" ");
                if(i==j) {
                    System.out.print(mat1[i][j]+" ");
                }
            }
            System.out.println();
        }
    }
}
  
  
  
  
  16feb
  
  package com.company;
import java.util.Scanner;
import java.util.StringJoiner;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class FEB16 {
    public static void main(String[] args) {
         FrequencyODDEVEN();
            main();
        StringRepresent();
    }

    private static void FrequencyODDEVEN() {
        // 1.) Find the frequency of odd and even in matrix

        int i, j, count1 = 0, count2 = 0;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter number of Row ");
        i = sc.nextInt();
        System.out.println("Enter number of column ");
        j = sc.nextInt();
        int a[][] = new int[i][j];
        System.out.println("Enter all the element oF Matrix ");

        for (int x = 0; x < i; x++) {
            for (int y = 0; y < j; y++) {
                a[x][y] = sc.nextInt();
            }
        }
        System.out.println("Given Matrix is ");
        for (int x = 0; x < i; x++) {
            for (int y = 0; y < j; y++) {
                System.out.print(a[x][y] + " ");
            }
            System.out.println("");
        }
        for (int x = 0; x < i; x++) {
            for (int y = 0; y < j; y++) {
                if ((a[x][y] % 2) == 0) {
                    count1++;
                } else {
                    count2++;
                }
            }
        }
        System.out.println("Even number frequency:" + count1);
        System.out.println("Odd number frequency:" + count2);
    }

    static void printDiagonalSums(int[][] mat, int n)
    // 2.) Find the sum of anti diagonal elements in given matrix
    {
        int principal = 0, secondary = 0;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {

                if (i == j)
                    principal += mat[i][j];

                if ((i + j) == (n - 1))
                    secondary += mat[i][j];
            }
        }

        System.out.println("Diagonal:"
                + principal);

        System.out.println("Anti Diagonal:"
                + secondary);
    }

    private static void main() {

        int[][] a = {{1, 5, 7},
                {2, 6, 8},
                {5, 8, 2},};

        printDiagonalSums(a, 3);
    }
    private static void StringRepresent(){
           /* 3.) Display the string represented by each row of given matrix.

            Input:["Hello"  "Geekster"]
                  ["Good"  "Day"]
            Output:
            Row 0 : HelloGeekster
            Row 1 : GoodDay             */
        Stream<String> str = Stream.of("Hello","Geekster");
        Stream<String> str1 = Stream.of("Good","Day");
        String res = str.collect(Collectors.joining("","{","}"));
        String res1 = str1.collect(Collectors.joining("","{","}"));
        System.out.println(res);
        System.out.println(res1);

    }
}




