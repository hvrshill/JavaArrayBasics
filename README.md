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

import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int numberOfDishes = sc.nextInt();
        int[] prices = new int[numberOfDishes];

        if (numberOfDishes >= 2) {
            for (int i = 0; i < numberOfDishes; i++) {
                int dishPrice = sc.nextInt();
                prices[i] = dishPrice;
            }

            Arrays.sort(prices);
            System.out.println(prices[prices.length - 1] + prices[prices.length - 2]);
        } else {
            System.out.println(0);
        }
    }
}
###Q4
Nick has been given a list of random numbers by his teacher. These numbers are marks of several students of his class. He is required to arranged the marks in increasing order and hence check whether the new arrangement of marks are successive in nature or not. You need to write a function such that it returns 1 if the complete arrangement consists of consecutive marks, otherwise return 0.

Note
If two students have the same marks, then after arranging them in increasing order, they will not be considered as consecutive.
Input Format
Integer N i.e., size of the array
Integer array for elements of the array
Constraints
NA
Output Format
Return 1 if all the numbers are consecutive after arrangement, otherwise return 0.
Sample Input 0
6
3 7 2 5 4 6
Sample Output 0
1
Explanation 0
After arranging the given numbers in increasing order, the array comes out to be as 2, 3, 4, 5, 6, 7.
As all the numbers in the array are consecutive, therefore 1 is returned.

import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int size = sc.nextInt();
        int[] marks = new int[size];

        for (int i = 0; i < size; i++) {
            marks[i] = sc.nextInt();
        }

        Arrays.sort(marks);
        boolean cons = true;

        for (int i = 1; i < size; i++) {
            if (marks[i] != marks[i - 1] + 1) {
                cons = false;
                break;
            }
        }

        System.out.println(cons ? 1 : 0);
    }
}

###Q5
You are working on a number sequence puzzle. You have an array A, that is supposed to contain all the numbers from 1 to N, but you realize one number is missing. The array might have been shuffled, so the numbers are not in order. Your task is to find and return an integer value representing the missing number from the sequence.
Input Format

An integer value N representing the length of the sequence
An integer array A

Constraints
NA
Output Format

Return an integer value representing the missing number from the sequence.
Sample Input 0

5  
3 1 2 5  
Sample Output 0
4
import java.io.*;
import java.util.*;

public class Solution{

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int size  =  sc.nextInt();
        int Missing = 0;
        int[] s = new int[size - 1]; 
        for(int i = 0; i < size - 1; i++){ 
            s[i] = sc.nextInt();
        }
        Arrays.sort(s);

        
        
        for(int i = 0; i < s.length - 1; i++){ // Iterate up to s.length - 1
            if(s[i+1] - s[i] != 1){ // Compare s[i+1] with s[i]
               Missing = s[i];
                break;
            }
        }
        
        // Handle the case where the missing number is the last element
        if (Missing == 0 && s.length > 0 && s[s.length-1] != size) { // Check if 'Missing' was not updated (meaning missing is the last element)
            Missing = s[s.length-1]; 
            System.out.println(Missing + 1); // If the missing number is 'size', print 'size'
        } else if (Missing != 0) {
            System.out.println(Missing + 1); // Print the missing number if found
        } else {
             // Handle cases like a single element or a complete sequence without any missing elements
            System.out.println(1); // If no gaps and no missing number after the largest element, assume 1 is missing, or
            // Adjust logic based on your problem statement for edge cases
        }
    }
}

###Q6
Alice has a pair of magical shoes that allows her to climb 3 stairs at once. In the city, there are N houses whose roofs Alice wants to reach. The number of stairs to the roof of each house is given in an array A. Alice can reach the roofs of only those houses where the number of stairs is a multiple of 3. Your task is to find and return an integer value representing the count of the number of houses whose roof Alice can climb up to.
Input Format
An integer value N representing the number of houses.
An integer array A representing the number of stairs in each hous
Constraints
NA
Output Format

Return an integer value representing the count of the number of houses whose roofs Alice can climb up to.
Sample Input 0

4  
12 21 3 4  
Sample Output 0

3
Explanation 0

Here, the given array is (12,21,3,4). There is only one house, (the 4th), whose roof Alice cannot go up to as it is not a multiple of 3. Therefore, 3 is returned as the output.
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int op = 0;
        int houses = sc.nextInt();
        int[] houseStairs = new int[houses];
        for(int i=0; i<houses;i++){
            houseStairs[i] = sc.nextInt();
        }
        
        for(int i =0; i < houses ;i++){
            if(houseStairs[i]%3==0){
                op+=1;
            }
        }
        System.out.println(op);
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
    }
}
