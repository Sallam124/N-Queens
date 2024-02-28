def printSolution(board):
    # Print the current arrangement of queens on the board
    for i in range(N):
        for j in range(N):
            print(board[i][j], end=' ')
        print()

def isSafe(board, row, col):
    # Check if placing a queen at (row, col) is safe
    for i in range(col):
        if board[row][i] == 1:
            return False
        for i, j in zip(range(row, -1, -1), range(col, -1, -1)):
            if board[i][j] == 1:
                return False
        for i, j in zip(range(row, N, 1), range(col, -1, -1)):
            if board[i][j] == 1:
                return False
    return True

def solveNQUtil(board, col):
    # Recursive function to find a valid placement for queens
    if col >= N:
        return True  # All queens are placed, solution found
    for i in range(N):
        if isSafe(board, i, col):
            board[i][col] = 1  # Place queen at (i, col)
            if solveNQUtil(board, col + 1):
                return True  # Recurse for next column
            board[i][col] = 0  # Backtrack if no valid placement
    return False

def solveNQ():
    board = [[0] * N for _ in range(N)]  # Initialize empty board
    if not solveNQUtil(board, 0):
        print("Solution does not exist")
        return False
    printSolution(board)  
    return True

N = 0  
solveNQ()  
