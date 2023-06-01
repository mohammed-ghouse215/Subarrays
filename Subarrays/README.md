# Question 1
# Amazing Subarray
You are given a string S, and you have to find all the amazing substrings of S.

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


