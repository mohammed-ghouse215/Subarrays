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
