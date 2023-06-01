# Amazing Subarray
Total number of subarrays = n*(n+1)/2; n= length of array
No of Subarrays starting with an index = length of array - index;

You are given a string S, and you have to find all the amazing substrings of S.
If A[] = {1,2,3,4}
No of subarrays = 4*(4+1)/2 = 10;
1
1 2       2 
1 2 3     2 3     3  
1 2 3 4   2 3 4   3 4  4

Number subarrys starting with 3 
index = 2 
length = 4;
4-2 = 2;

Total number of subarays 3 is a part of
Range
(index+1) * (Length-index)
------------------------------------------
Generate all subarrays
for(int i=0;i<n;i++){
            for(int j=i;j<n;j++){
                ArrayList<Integer> small = new ArrayList<>();
                for(int k=i;k<=j;k++){
                    small.add(A[k]);
                }
                ans.add(small);
            }
        }
---------------------------------------------                                                              
An amazing Substring is one that starts with a vowel (a, e, i, o, u, A, E, I, O, U).
// Code //
public class Solution {
    public int solve(String A) {
        int len = A.length();
        int count = 0;
        for(int i=0;i<len;i++){
           
            char ch = A.charAt(i);
            if(ch=='a'||ch=='e'||ch=='i'|| ch=='o'||ch=='u'|| ch=='A' ||ch=='E'|| ch=='I'||ch=='O'|| ch=='U'){
            count = ( count + ( len - i ) ) % 10003;
            }

        }
        return count;
    }
}
-----------------------------------------------------
Maximum subarray:
Two ways we can solve this with O(n^2)
1. Using sum count 
int C[] = {1,2,3,4,-10}; int ans = 0;
 for(int i=0;i<n;i++){
            int sum = 0;
            for(int j=i;j<n;j++){
                sum = sum + C[j];
                    ans = Math.max(ans,sum);
            }
        }
2. Using prefix sum
3. Generate prefix sum 
4. C[] = {1,3,6,10,0};
5. for(int i=0;i<n;i++){
            for(int j=i;j<n;j++){
                if(i==0){
                sum = prefix_sum[j];
                }
                else{
                sum = prefix_sum[j]-prefix_sum[i-1];
                }
                ans = Math.max(ans,sum);
            }
        }
        
   3. Kadane's algorithm
     for(int i=0;i<n;i++){
     if(sum>=0){
     sum = sum + C[i];
     }
     else{
     sum = C[i];
     }
     }
-----------------------------------------------
Alternating subarrays
Day 36 - Intermediate DSA: Arrays : Subarrays HomeWork Question -1
------------------------------------------------
Generate Subarrays with given length
for(int i=0;i<=n-B;i++){
    int sum = 0;
   for(int j=i;j<B+i;j++){
    System.out.print(A[j]+" "); 
          sum = sum +A[j];
      }
    System.out.print("Sum = "+sum);
    System.out.println();
}
------------------------------------------------
Day 41 - Intermediate DSA: Bit Manipulations - 1 HW Question-3
Day 47 - Intermediate DSA : Hashing - 1  HW Question-1
Day 48 - Intermediate DSA : Hashing - 2  AS Question-1
Day 48 - Intermediate DSA : Hashing - 2  HW Question-4
Day 48 - Intermediate DSA : Hashing - 2  HW Question-5
Day 55 - Advanced DSA : Arrays - 1  HW Question-1
Day 55 - Advanced DSA : Arrays - 1 AS Question-3
Day 68 - Advanced DSA : Sorting - 3  HW Question-1
Day 92 - Advanced DSA : Tries - 2 HW Question-2
