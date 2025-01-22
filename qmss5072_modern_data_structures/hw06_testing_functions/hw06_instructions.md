# QMSS G5072 Homework 6
### Professor Thomas Brambor

## Tic-Tac-Toe Testing Exercise

In this exercise, you will use `pytest` to create and test functions that manage the state of a Tic-Tac-Toe game. You will implement functions to initialize the game board, make moves, check for a win or a draw, and reset the game.

Below are the definitions of the `initialize_board`, `make_move`, `check_winner`, and `reset_game` functions you'll be working with:

```python
def initialize_board():
    """Creates a 3x3 Tic-Tac-Toe board initialized with empty spaces."""
    return [[' ' for _ in range(3)] for _ in range(3)]

def make_move(board, row, col, player):
    """
    Places the player's symbol ('X' or 'O') on the board at the specified position.
    
    Args:
        board (list): The current game board.
        row (int): The row index (0-based).
        col (int): The column index (0-based).
        player (str): The player's symbol ('X' or 'O').

    Returns:
        bool: True if the move was successful, False otherwise.
    """
    if board[row][col] == ' ':
        board[row][col] = player
        return True
    return False

def check_winner(board):
    """
    Checks the current board for a winner.

    Args:
        board (list): The current game board.

    Returns:
        str: 'X' or 'O' if there is a winner, 'Draw' if it's a draw, or None if the game is ongoing.
    """
    # Check rows, columns, and diagonals
    lines = board + list(zip(*board))  # Rows and columns
    lines.append([board[i][i] for i in range(3)])  # Main diagonal
    lines.append([board[i][2-i] for i in range(3)])  # Anti-diagonal

    for line in lines:
        if all(cell == 'X' for cell in line):
            return 'X'
        if all(cell == 'O' for cell in line):
            return 'O'
    
    # Check for draw
    if all(cell != ' ' for row in board for cell in row):
        return 'Draw'
    
    return None

def reset_game():
    """Resets the game by reinitializing the board."""
    return initialize_board()
```

### 1. Test the `initialize_board`, `make_move`, `check_winner`, and `reset_game` Functions

#### a) Write a test function `test_initialize_board` that verifies the `initialize_board` function creates an empty 3x3 board.

#### b) Write a test function `test_make_move_valid` that checks whether make_move successfully places a player’s symbol on an empty cell. Test this for both players ‘X’ and ‘O’.

_Hint:_ start with a pre-specified board configuration and then add a valid move (using the `make_move()` function), assuring that is done correctly.

#### c) Write a test function `test_make_move_invalid` that ensures `make_move` does not overwrite an occupied cell and returns `False` when attempting to do so.

#### d) Write an integration test `test_game_integration` that performs a series of operations: initializing the board, making multiple moves, checking for a winner, and resetting the game. After each operation, verify the state of the board and the game status (i.e. if there is a winner).

#### e) Add the tests from 1a, 1b, 1c, and 1d to a file called `test_tictactoe.py` in your folder. Run all the tests from your command line using `pytest` (with verbosity setting `-vv`) and include the output in your homework solution.

### 2. Advanced Testing

#### a) Utilize the `@pytest.mark.parametrize` decorator to create a parameterized test function `test_make_move` that tests multiple scenarios of making moves, including edge cases such as invalid row or column indices, and placing a marker in an already occupied spot.

_Hint_: In this test, you’re verifying the behavior of the `make_move` function under different scenarios. To do this, you’ll need to create specific board configurations (i.e., `initial_board`) to test whether the move works as expected.

Think of each test case as setting up a board in a known state and then trying to make a move on that board:

1.	Empty Board: A completely empty board where any valid move should succeed.
2.	Occupied Cell: A board where one cell is already taken. Try to make a move on that cell and check if it returns `False`.
3.	Valid Move: A board where you attempt to place a move on a valid, empty cell.
4.	Out-of-Bounds Moves: Consider moves where row or col is outside the 3x3 grid (e.g., 3, 3 or -1, 0). These should raise an IndexError.

For each test case, start with a specific `initial_board`, then use the `make_move` function with a given `row`, `col`, and `player`. Based on the scenario, check if the move is successful (or not) and if the board is updated correctly.

Here is an example of an `initial_board` configuration: 
```
    [['X', ' ', ' '],
    [' ', ' ', ' '],
    [' ', ' ', ' ']]
```

#### b) Use the pytest `fixture` functionality to create a common setup for a game board that will be used in multiple test functions. Ensure that this fixture initializes a fresh board before each test to maintain test independence.

## Submit Your Homework

- Ensure that your initialize_board, make_move, check_winner, and reset_game functions are correctly implemented and handle all edge cases.

- All test functions should be commented, explaining the logic where necessary.

- Ensure that the `pytest` output is properly captured and included in your submission.

- Your submission should include the `tictactoe.py` and `test_tictactoe.py` files, along with a Jupyter notebook containing the `pytest` output.

Please follow the [instructions](/Exercises/homework_submission_instructions.md) to submit your homework on Github. The homework is due on Wednesday, October 23 at 5pm.
