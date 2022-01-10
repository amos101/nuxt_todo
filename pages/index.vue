<template>
  <section class="container">
    <h1>Todo App</h1>
    <p><input type="text" name="content" v-model="content" placeholder="タスクを入力してください"/></p>
    <div>
      <td><button class="button button--green" @click="insert">追加</button></td>

    </div>
    <div class="Filter">
      <button class="button button--gray is-active">全て</button>
      <button class="button button--gray">作業前</button>
      <button class="button button--gray">作業中</button>
      <button class="button button--gray">完了</button>
    </div>
    <table class="Lists">
      <thead>
        <tr>
          <th>タスク</th>
          <th>登録日時</th>
          <th>状態</th>
          <th> </th>
        </tr>
      </thead>
      <tr v-for="(todo, index) in todos" :key="index">
        <td>{{ todo.content }}</td>
        <td>({{ todo.created }})</td>
        <td><button class="button">{{ todo.state }}</button></td>
        <td><button class="button button--delete" @click="remove(item)">削除</button></td>
      </tr>
    </table>
  </section>
</template>

<script>
import {mapState} from 'vuex';

export default {
  data: function() {
    return {
      content: ''
    }
  },
  computed: {
    ...mapState(['todos'])
  },
  methods: {
    insert: function() {
      if(this.content != ''){
        this.$store.commit('insert', {content: this.content});
        this.content = '';
      }
    }
  },
  remove: function(todo) {
    this.$store.commit('remove', todo)
  }
}
</script>