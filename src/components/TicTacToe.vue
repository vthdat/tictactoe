<template>
    <div class="board">
        <div v-for="(n, i) in 3">
          <div v-for="(n, j) in 3">
            <cell @click="newClicked(i,j)" :value="board[i][j]"></cell>
          </div>
        </div>
        <button id="reset"> Reset </button>
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
      flag: 1
    } },


    methods:{
      newClicked(i, j){
        if (this.board[i][j] != ''){
          return;
        }
        if (this.flag){
          this.board[i][j] = 'x';
          this.flag = 0;
        }else
        {
          this.board[i][j] = 'o';
          this.flag = 1;
        };

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