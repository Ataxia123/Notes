To convert algebraic notation into FEN (Forsyth-Edwards Notation), you can follow these steps:

1. Start with an empty chessboard and a FEN string template.
2. Split the algebraic notation into individual moves, removing any additional annotations like "+", "#", or "=".
3. For each move, identify the piece type and the target square. If the move is a capture, identify the captured piece as well.
4. Determine the correct piece notation based on the piece type and player color (e.g., "P" for White pawn, "p" for Black pawn, "K" for White king, "k" for Black king).
5. If the move is a pawn promotion, append the promotion piece notation to the target square (e.g., "e8=Q" becomes "e8Q").
6. Update the chessboard state by placing the piece on the target square and removing any captured piece if applicable.
7. For each move, update the FEN string by representing the chessboard state using the following rules:
   - Represent each rank from the 8th rank to the 1st rank, starting from the file "a" to "h".
   - Use numbers to represent the count of consecutive empty squares. For example, if there are four empty squares before a piece, represent them as "4".
   - Use the piece notation to represent each piece on the board.
   - Use "/" to separate each rank.
8. Determine the current player's turn and update the FEN string accordingly (e.g., "w" for White's turn, "b" for Black's turn).
9. Determine the castling rights based on the availability of the kingside and queenside castling for both players, and update the FEN string accordingly (e.g., "KQkq" if all castling rights are available).
10. Determine the en-passant square, if applicable, and update the FEN string accordingly (e.g., "e3" if en-passant is possible on the "e3" square).
11. Determine the halfmove clock (the number of halfmoves since the last capture or pawn move) and the fullmove number (the current move number), and update the FEN string accordingly.
12. The final FEN string represents the current position after all the moves have been processed.

Remember to consult the official FEN notation rules for any special cases or exceptions that may arise during the conversion process.