#include <stdio.h>

void printBoard(char board[3][3]) {
    printf("-------------\n");
    for (int i = 0; i < 3; i++) {
        printf("| %c | %c | %c |\n", board[i][0], board[i][1], board[i][2]);
        printf("-------------\n");
    }
}

int isGameOver(char board[3][3]) {
    for (int i = 0; i < 3; i++) {
        if (board[i][0] == board[i][1] && board[i][1] == board[i][2] && board[i][0] != ' ')
            return 1;  // Row match

        if (board[0][i] == board[1][i] && board[1][i] == board[2][i] && board[0][i] != ' ')
            return 1;  // Column match
    }

    if (board[0][0] == board[1][1] && board[1][1] == board[2][2] && board[0][0] != ' ')
        return 1;  // Diagonal match

    if (board[0][2] == board[1][1] && board[1][1] == board[2][0] && board[0][2] != ' ')
        return 1;  // Diagonal match

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j] == ' ')
                return 0;  // Game still in progress
        }
    }

    return -1;  // It's a tie
}

int main() {
    char board[3][3] = { { ' ', ' ', ' ' }, { ' ', ' ', ' ' }, { ' ', ' ', ' ' } };
    int player = 1;  // Player 1 starts
    int choice;
    int gameState = 0;  // 0: Game in progress, 1: Player 1 wins, 2: Player 2 wins, -1: Tie

    printf("Tic-Tac-Toe Game\n");

    while (gameState == 0) {
        printBoard(board);
        printf("Player %d, enter a number (1-9): ", player);

        do {
            scanf("%d", &choice);

            if (choice < 1 || choice > 9 || board[(choice - 1) / 3][(choice - 1) % 3] != ' ') {
                printf("Invalid move. Try again: ");
            }
        } while (choice < 1 || choice > 9 || board[(choice - 1) / 3][(choice - 1) % 3] != ' ');

        if (player == 1)
            board[(choice - 1) / 3][(choice - 1) % 3] = 'X';
        else
            board[(choice - 1) / 3][(choice - 1) % 3] = 'O';

        gameState = isGameOver(board);

        // Switch players
        if (player == 1)
            player = 2;
        else
            player = 1;
    }

    printBoard(board);

    if (gameState == 1)
        printf("Player 1 wins!\n");
    else if (gameState == 2)
        printf("Player 2 wins!\n");
    else
        printf("It's a tie!\n");

    return 0;
}
