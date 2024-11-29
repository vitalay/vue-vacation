<template>
  <div class="user">
    <button @click="deleteUser(index)">Удалить</button>
    <h3>{{ uuuser.name }}</h3>
    <p>
      {{ uuuser.email }} - <b>{{ uuuser.password }}</b>
    </p>
  </div>
</template>

<script>
export default {
  props: {
    uuuser: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    },
    deleteUser: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style scoped>
button {
  border: 0;
  border-radius: 5px;
  outline: none;
  padding: 10px 15px;
  background: #d66c75;
  color: #7f1629;
  font-weight: bold;
  cursor: pointer;
  transition: transform 500ms ease;
  float: right;
}
button:hover {
  transform: translateY(-5px);
}
</style>
