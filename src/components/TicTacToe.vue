<template>
  <div class="board">
    <div v-for="(n, i) in 3">
      <div v-for="(n, j) in 3">
        <cell @click="newClicked(i,j)" :value="board[i][j]"></cell>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() { return {
      board: [
          ['', '', ''],
          ['', '', ''],
          ['', '', '']
        ],
      turn: 0
    } },


    methods:{
      newClicked(i, j){
        if (this.board[i][j] != ''){
          return;
        }
        if ((this.turn % 2) == 0){
          this.board[i][j] = 'x';
        }else
        {
          this.board[i][j] = 'o';
        };

        this.turn++;
        this.$forceUpdate();
      }
    }


  }
</script>

<style>
  .board {
    display: flex;
    flex-wrap: wrap;
    width: 500px;
    height: 500px;
    align-self: center;
  }
</style>