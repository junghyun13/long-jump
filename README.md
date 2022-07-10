# long-jump
# python
# You can jump 1 hex or 2 hexes at a time. When there are a total of 4 squares, (1 space, 1 space, 1 space, 1 space) (1 space, 2 spaces, 1 space) (1 space, 1 space, 2 space) (2 spaces, 1 space, 1 space) (2 spaces, 2 spaces) There are 5 ways to get to the very end of the space. Given the number n of cells to be used in the long jump, find out how many ways Hyojin can reach the end, and complete the solution, a function that returns the remainder after dividing 1234567. 한번에 1칸, 또는 2칸을 뛸 수 있습니다. 칸이 총 4개 있을 때, (1칸, 1칸, 1칸, 1칸) (1칸, 2칸, 1칸) (1칸, 1칸, 2칸) (2칸, 1칸, 1칸) (2칸, 2칸) 의 5가지 방법으로 맨 끝 칸에 도달할 수 있습니다. 멀리뛰기에 사용될 칸의 수 n이 주어질 때, 효진이가 끝에 도달하는 방법이 몇 가지인지 알아내, 여기에 1234567를 나눈 나머지를 리턴하는 함수, solution을 완성하세요. 
def solution(n):
    dp = [0] * (n+1) #n=1인경우 dp[1]에서 에러가 날 수있어서 1개 더 늘려서 선언
    dp[0] = 1
    dp[1] = 2
    for i in range(2,n):
        dp[i] = dp[i-2] + dp[i-1]
    return dp[n-1] % 1234567 #정답은 실제 개수를 1234567로 나눈 나머지 값이므로
a=solution(4)
print(a)
#result--> 5
