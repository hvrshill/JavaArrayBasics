# JavaArrayBasics
Problems and Solution


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
