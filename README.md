# Concat-Palindrome

Ninu has two strings A and B of lengths N and M respectively. Ninu can rearrange both strings in any way she wants. Let the rearranged string of A be A′ and the rearranged string of B be B′. Determine whether she can construct rearrangements A′ and B′ such that (A′ + B′) is a palindrome.
Here + denotes the concatenation operation. For e.g. abc + xyz = abcxyz.
Note: A string is called palindrome if it reads the same backwards and forwards, for e.g. noon and level are palindromic strings.

def solve():
    T = int(input())  
    for _ in range(T):
        N, M = map(int, input().split())  
        A = input().strip()  
        B = input().strip()  

        freq = [0] * 26

        for c in A:
            if 'a' <= c <= 'z':  
                freq[ord(c) - ord('a')] += 1

        for c in B:
            if 'a' <= c <= 'z':  
                freq[ord(c) - ord('a')] += 1

        odd_count = 0
        for count in freq:
            if count % 2 != 0:
                odd_count += 1

        if (N + M) % 2 == 0:
            if odd_count == 0:
                print("Yes")
            else:
                print("No")
        else:
            if odd_count == 1:
                print("Yes")
            else:
                print("No")


if __name__ == "__main__":
    solve()
