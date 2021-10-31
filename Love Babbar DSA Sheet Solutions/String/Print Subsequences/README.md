# Print All Subsequences Of A String

## Problem Statement
Given a string, we have to find out all subsequences of it. A String is a subsequence of a given String, that is generated by deleting some character of a given string without changing its order.

## Sample Input Output

Input : abc
<br>
Output : a, b, c, ab, bc, ac, abc

Input : aaa
<br>
Output : a, aa, aaa

## Desciption and Approach

A subsequence is a sequence generated from a string after deleting some characters of string without changing the order of remaining string characters.

For example, If we have a string : "abc", Then its subsequences are :- "a", "b", "c", "ab", "ac", "bc", "abc"
1) First we select first character i.e. 'a' , print it and fix it. ----> a
2) Take next charecter i.e. 'b' , print it and fix it ----> ab
3) Keep taking next charecters until string ends ---->abc
4) Delete upto first charecter , start taking charecter from second
5) position from first charecter till string ends ----> ac
6) Similarly go for rest charecters ---->b , bc , c

If we have string of `n` length. Then the number of its non-empty subsequences is `(2n -1)`.

## C++ Code

```
#include <iostream>
#include <string>
using namespace std;

void printSubsequences(string str, int start, int end, string curStr = ""){
	//base case
	if (start == end) {
		return;
	}
	//print current string permutation
	cout<<curStr<< "  ";
	for (int i = start + 1; i< end; i++) {
		curStr += str[i];
		printSubsequences(str, i, end, curStr);
		curStr = curStr.erase(curStr.size() - 1);
	}
}

int main(){
	string s;

	cout<< "Enter string : ";
	cin>> s;
	int len = s.size();
	
	cout<< "Subsequences : ";
	printSubsequences(s, -1, len);
	
	return 0;
}
```
## References

Question: https://www.geeksforgeeks.org/print-subsequences-string/

Video: https://youtu.be/OZiTiLDZJ60