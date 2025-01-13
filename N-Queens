class Solution {
public:
    // Stores all valid board configurations
    vector<vector<string>> combs;
    // Represents the current board state
    vector<string> board;
    // Tracks the column position of queens for each row
    int placedWhereFor[9] = {0};

    // Checks if a queen can be placed at (row, col)
    bool place(int row, int col) {
        for (int i = 0; i < row; i++) {
            // Same column conflict
            if (placedWhereFor[i] == col) return false;
            // Diagonal conflict
            if (abs(placedWhereFor[i] - col) == abs(row - i)) return false;
        }
        return true;
    }

    // Recursive backtracking function
    void queen(int row, int n) {
        if (row == n) {
            // Store the current valid configuration
            combs.push_back(board);
            return;
        }
        for (int col = 0; col < n; col++) {
            // If placing a queen at (row, col) is valid
            if (place(row, col)) {
                board[row][col] = 'Q';          // Place the queen
                placedWhereFor[row] = col;      // Record the column
                queen(row + 1, n);              // Recur to the next row
                board[row][col] = '.';          // Backtrack
            }
        }
    }
    
    // Solves the N-Queens problem
    vector<vector<string>> solveNQueens(int n) {
        // Initialize the board with empty cells ('.')
        board = vector<string>(n, string(n, '.'));
        // Start the recursive backtracking process
        queen(0, n);
        return combs;
    }
};
