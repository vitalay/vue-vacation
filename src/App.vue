<template>
  <input type="text" v-model="userName" placeholder="Name" />
  <input type="password" v-model="userPassword" placeholder="Password" />
  <input type="text" v-model="userEmail" placeholder="Email" />
  <button @click="sendData">Нажми</button>
  <p className="error"> {{ error }}</p>

  <p>{{ users }}</p>
</template>

<script>
export default {
  data() {
    return {

      users: [],
      error: "",
      userName: "",
      userPassword: "",
      userEmail: "",
    };
  },
  methods: {
    sendData() {

      if (this.userName === "" || this.userPassword === "" || this.userEmail === "") {
        this.error = "Заполните все поля";
        return;
      }

      this.users.push({
        name: this.userName,
        password: this.userPassword,
        email: this.userEmail,
      });
    },
  },
};
</script>

<style scoped>
button {
  display: inline-block;
  padding: 5px 15px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #fff;
  background-color: #04aa6d;
  border: none;
  border-radius: 15px;
  box-shadow: 0 4px #999;
}
button:hover {
  background-color: #3e8e41;
}

button:active {
  background-color: #3e8e41;
  box-shadow: 0 5px #666;
  transform: translateY(4px);
}

input {
  width: 150px;
  font-size: 13px;
  padding: 6px 0 4px 10px;
  border: 1px solid #cecece;
  background: #f6f6f6;
  border-radius: 8px;
}
</style>
