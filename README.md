# JavaArrayBasics
Problems and Solution

###Q1
In an e-commerce platform, the system manages a list of product IDs that are used to track each product. The platform needs to efficiently insert new product IDs into a sorted list to maintain the order. Rahul, a software engineer, has been tasked with creating a function to insert a new product ID into the correct position in the sorted list of product IDs.
Rahul needs to ensure that the list is always sorted, and the product ID is inserted in the right position without disturbing the existing order.
Given an array of product IDs (sorted in non-decreasing order) and a new product ID, your task is to insert the new product ID into the array, keeping the list sorted.
Input Format
The first line contains an integer n representing the number of existing product IDs.
The second line contains n integers representing the product IDs in sorted order.
The third line contains an integer newProductId, which represents the new product ID to be inserted.
Constraints

1 ≤ n ≤ 1000
The product IDs are integers and are sorted in non-decreasing order.
The new product ID to be inserted is an integer.
Output Format

Output the new array with the product ID inserted at the correct position, maintaining the sorted order.

Sample Input 0
5
101 105 110 120 130
107
Sample Output 0
101 105 107 110 120 130
Explanation 0
The array is initially sorted as [101, 105, 110, 120, 130]. The new product ID 107 is inserted in the correct position, between 105 and 110, resulting in the array [101, 105, 107, 110, 120, 130].

Sample Input 1
4
100 200 300 400
150

Sample Output 1
100 150 200 300 400
'''java

import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner sc = new Scanner(System.in);
        int totID = sc.nextInt();
        int[] List = new int[totID];
        int[] nList = new int[totID+1];
        for(int i=0; i<=totID-1; i++){
          int prod =sc.nextInt();
           List[i] = prod;
        }
        Arrays.sort(List);
        int newID = sc.nextInt();
        for (int i = 0; i < List.length; i++) {
                nList[i] = List[i];
            }
        nList[nList.length - 1] = newID;
        Arrays.sort(nList);
        for(int i=0; i<=nList.length-1; i++){
            System.out.print(nList[i]+ " ");
        }
        
    }
}

'''
###Q2
Charles is given an array A. He wants to find the count of occurrence of second largest element in the array. Your task is to help him find and return an integer value representing the count of occurrence of the second largest element in an array.
Note
If the array contains the same elements, then return 0
The array has only consecutive elements
Input Format
An integer N, representing length of array.
An integer array A
Constraints
NA
Output Format
Return an integer value representing the count of occurrence of the second largest element in an array.
Sample Input 0
8
1 2 3 4 4 5 5 5
Sample Output 0

2

'''java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int l = sc.nextInt();
        int[] nList = new int[l];
        int sum = 0;

        for (int i = 0; i < l; i++) {
            int prod = sc.nextInt();
            nList[i] = prod;
        }

        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;

        // Find largest
        for (int i = 0; i < l; i++) {
            if (nList[i] > largest) {
                largest = nList[i];
            }
        }

        // Find second largest (less than the largest)
        for (int i = 0; i < l; i++) {
            if (nList[i] > secondLargest && nList[i] < largest) {
                secondLargest = nList[i];
            }
        }

        for (int i = 0; i < nList.length; i++) {
            if (secondLargest == nList[i]) {
                sum += 1;
            }
            }
        

        System.out.println(sum);
    }
}

'''
###Q3
You are planning a dinner menu for an event, and you have a list of N dishes stored in array A, each with a certain cost associated with it. You must select two such dishes, such that the sum of their costs is maximum among all available pairs. Your task is to find and return an integer value representing the sum of such available pair. Return 0 in case of no such pair available.
Input Format
An integer value N representing the number of dishes available.
An integer array A representing the cost of dishes
Constraints
NA
Output Format
Return an integer value representing sum of such pair available. In case, there are no such pair present, return 0.
Sample Input 0
4
1 10 5 15
Sample Output 0
25
Explanation 0
Here, A = (1,10,5,15). The pair with maximum sum would be 10 and 15, since they are the largest in the array of prices and their sum would be 25. Therefore, 25 is returned as the answer

'''java
import java.io.*;
import java.util.*;
public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int numberOfDishes = sc.nextInt();
        int[] prices = new int[numberOfDishes];
        for(int i = 0; i <numberOfDishes; i++){
            int dishPrice = sc.nextInt();
            prices[i] = dishPrice;
            
        }
        Arrays.sort(prices);
        System.out.println(prices[prices.length-1]+prices[prices.length-2]);
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
    }
}

