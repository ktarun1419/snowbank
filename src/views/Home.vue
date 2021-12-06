<template>
  <div class="home">
    <div class="navbar">
        <img style="float:left; margin-left:100px;margin-top:20px;" width="200px" src="../assets/logosnowbank.png" height="100%">
  <a href="https://magicrabit23.gitbook.io/snowfarm-dao-whitepaper/" style="float:right; margin-right:80px;color:#333; font-size:15px;margin-top:15px;">Docs</a>
  <a  href="" style="float:right;margin-right:5px; color:#333;font-size:15px;margin-top:15px;">Twitter</a>
  <a href="https://discord.gg/MJ8hhYQxtK" style="float:right;margin-right:5px;color:#333;font-size:15px;margin-top:15px;">Discord</a>
</div>
    <!-- <img alt="Vue logo" src="../assets/home.png" width="100%" style="margin-top:100px;" v-on:click="routerchange"> -->
    <div>
      <img src="./home2.png" alt="" width="100%" height="60%">
       <button style=" padding: 12px 48px;background-color:black; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; color:white; float:left; margin-left:10%; margin-bottom:10% " v-on:click="routerchange">Enter App</button>
       <img src="./home.png" alt="" width="100%" height="60%">
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  methods:{
    routerchange(){
      console.log('lolo')
      this.$router.push('/app')
    }
  }
  
}
</script>
<style lang="scss">
.start{
  width:100%;
  background-image: url(home.png);
  background-repeat: no-repeat;
  background-size:contain;
  height: 100%;

}
.navbar {
  overflow: hidden;
  background-color:#fff;
  position: fixed; /* Set the navbar to fixed position */
  top: 0; /* Position the navbar at the top of the page */
  width: 100%; /* Full width */
  margin-bottom: 30px;
}
/* Links inside the navbar */
.navbar a {
  display: inline-block;
  display: block;
  color: #333;
  padding: 14px 16px;
  text-decoration: none;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
}
/* Change background on mouse-over */
.navbar a:hover {
  background:#b94242;
  color:white;
}
</style>
