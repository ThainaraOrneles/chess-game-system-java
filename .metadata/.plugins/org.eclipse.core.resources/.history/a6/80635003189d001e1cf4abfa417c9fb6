package boardgame;

public class Board {
	
	private int rows;
	private int columns;
	private Piece [][] pieces;
	
	public Board(int rows, int columns) {		
		if(rows < 1 || columns < 1) {
			throw new BoardException("Error creating board: there must be at least 1 row and 1 column");
		}		
		this.rows = rows;
		this.columns = columns;
		pieces = new Piece[rows][columns];
		
	}

	public int getRows() {
		return rows;
	}

	public int getColumns() {
		return columns;
	}		
	
	public Piece piece(int row, int column) {
		if(!positionExists(row, column)) {
			throw new BoardException("Position not on the board");
		}
		return pieces[row][column];
	}
	
	public Piece piece(Position position) {
		if(!positionExists(position)) {
			throw new BoardException("Position not on the board");
		}
		return pieces[position.getRow()][position.getColumn()];
	}
	
	public void placePiece(Piece piece, Position position) {
		/*
		 * Esta matriz de peças é a que está declarada no meu tabuleiro
		 */
		if(thereIsAPiece(position)) {
			throw new BoardException("There is already a piece on position " + position);
		}
		pieces[position.getRow()][position.getColumn()] = piece;
		piece.position = position;
	}
	
	private boolean positionExists(int row, int column) {
		/**
		 * A posição existe quando uma dada linha e uma coluna está
		 * contida no tabuleiro. Ou seja, a linha, deverá seguir a seguinte 
		 * lógica, 
		 * a linha tem que ser maior ou igual a zero && e a linha tem que ser menor 
		 * que a altura do tabuleiro && a coluna tem que ser maior que zero && coluna tem 
		 * que ser menor que a quantidade de colunas no tabuleiro.
		 * 
		 **/
		return row >= 0 && row < rows && column >= 0 && column < columns;
	}
	
	public boolean positionExists(Position position) {
		return positionExists(position.getRow(), position.getColumn());
	}
	
	public boolean thereIsAPiece(Position position) {
		if(!positionExists(position)) {
			throw new BoardException("Position not on the board");
		}
		return piece(position) != null;
	}
}
