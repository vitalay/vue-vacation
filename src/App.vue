<template>
  <input type="text" v-model="userName" placeholder="Name" />
  <input type="password" v-model="userPassword" placeholder="Password" />
  <input type="email" v-model="userEmail" placeholder="Email" />
  
  <button @click="sendData">Нажми</button>
  <p className="error">{{ error }}</p>

  <div v-if="users.length == 0" className = 'user'>
    У вас нет пользователей
  </div>
  <div v-else-if="users.length == 1" className = 'user'>
    У вас 1 пользователь
  </div>
  <div v-else className = 'user'>
    У вас масив имеет больше чем 1 пользователь
  </div>

  <User v-for="(el, index) in users" :key="index" :uuuser="el" :index="index" :deleteUser="deleteUser" />

  
</template>

<script>
import User from './components/User.vue';

export default {
  components: {
    User
  },
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
      if (this.userName == ""){
        this.error = "Заполните все поля";
        return;
      }
      if (this.userPassword == "") {
        this.error = "Заполните все поля";
        return;   

      }
      if (this.userEmail == "") {
        this.error = "Заполните все поля";
        return;
      }
  
      
        this.error = "";
        
      

      this.users.push({
        name: this.userName,
        password: this.userPassword,
        email: this.userEmail,
      });
    },
    deleteUser(index) {
      this.users.splice(index, 1);
    }
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
.user {
  width: 500px;
  margin-top: 20px;
  border: 1px solid silver;
  background: #e3e3e3;
  color: #222;
  padding: 20px;
  border-radius: 5px;
}
  
</style>
