<template>
   
  <div class="navbar d-flex">
       <h1>Welcome to your Dashboard</h1>
       <button id="logout">Logout</button>
   </div>
   <div class="d-flex userdetails">
       <div class="dashboard">
           <div>Username: <span id="loggedusername"></span></div>
           <div>Email: <span id="loggedemail"></span></div>
           <div>Account Number: <span id="logggedaccountno"></span></div>
   
       </div>

   </div>

<div class="balanceheading">
   <h4>Balance detail </h4>
</div>
   <div class="bankdetails">
       <div>
           <h2>Balance</h2>
           <p>$ <span id="balance">{{balance}}</span></p>
       </div>
       <div>
           <h2>Deposit</h2>
           <p>$ <span id="deposit">{{deposit}}</span></p>
       </div>
       <div>
           <h2>Withdraw</h2>
           <p>$ <span id="withdraw">{{ withdraw }}</span></p>
       </div>
   </div>
   <div class="balanceheading">
       <h4>Deposit & withdrawal </h4>
   </div>
   <div class="bankentry">
       <div>
           <h3>Enter amount to deposit</h3>
           <input type="number" v-model="depositin" placeholder="e.g 100" id="deposit-input" required>
           <button @click="this.depositnow()" id="deposit-btn">Deposit</button>
       </div>

       <div>
           <h3>Enter amount to withdraw</h3>
           <input type="number" placeholder="e.g 100" id="withdraw-input" required>
           <button id="withdraw-btn">Withdraw</button>
       </div>
   </div>
</template>

<script>
export default {
 name: "HomeView",
 data() {
   return {
  depositin:0,
  balance:0,
  deposit:0,
  withdraw:0

   }


 },
 created: function () {
  
 },

 beforeUnmount: function () {

 },
 methods: {
   depositnow(){
      
   if(this.depositin=== 0){
       alert("please an amount to deposit");
   } else{
       this.balance=this.balance+this.depositin;
       this.deposit=this.deposit+this.depositin
       this.depositin= '';
       alert("Amount is desposited");
   }
   }
 }
}
</script>

