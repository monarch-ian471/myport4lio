<template>
  <div class="game-container">
    <div v-if="winner" class="winner-message">
      {{ winner }} Wins!
      <button @click="resetGame">Play Again</button>
    </div>
    <div class="tic-tac-toe-grid">
    <button
      v-for="(cell, index) in cells"
      :key="index"
      class="cell"
      @click="handleClick(index)"
    >
      {{ cell }}
    </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TicTacToe',
  data() {
    return {
      cells: Array(9).fill(''),
      currentPlayer: 'X',
      winner: null,
    };
  },
  methods: {
    handleClick(index) {
      if (this.cells[index] === '' && !this.winner) {
        this.cells[index] = this.currentPlayer;
        if (this.checkWin()) {
          this.winner = this.currentPlayer;
          // Reset game after 0.1s if there's a winner
          setTimeout(() => {
            if (this.winner) {
                this.resetGame();
            }
          }, 100);
        }
        this.currentPlayer = this.currentPlayer === 'X' ? 'O' : 'X';
      }
    },
    checkWin() {
      const winPatterns = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6],
      ];

      for (const pattern of winPatterns) {
        const [a, b, c] = pattern;
        if (
          this.cells[a] &&
          this.cells[a] === this.cells[b] &&
          this.cells[a] === this.cells[c]
        ) {
          return true;
        }
      }
      return false;
    },
    resetGame() {
      this.cells = Array(9).fill('');
      this.currentPlayer = 'X';
      this.winner = null;
    }
  },
  
};
</script>

<style scoped>
.tic-tac-toe-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 1fr);
  width: 300px;
  height: 300px;
  border-collapse: collapse;
}

.cell {
  width: 100px;
  height: 100px;
  border: 1px solid black;
  font-size: 48px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  background-color: #f0f0f0;
}

.cell:hover {
  background-color: #e0e0e0;
}

.winner-message {
  font-size: 24px;
  margin-bottom: 20px;
  text-align: center;
}

.winner-message button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>