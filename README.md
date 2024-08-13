# Swami_5
Download and install Node.js.(https://nodejs.org/en/download/prebuilt-installer)
: Download and install Ganache (Ethereum Simulator).(https://archive.trufflesuite.com/ganache/)
Click on ‘QUICKSTART’ Step 4: Note down the RPC Server URL.
Create a new file with the following code and save it as ‘ethermine.js’. 
	Note: Replace the URL in Line 3 with your RPC server URL.
const {Web3}= require('web3');

const web3=new Web3(new Web3.providers.HttpProvider('http://127.0.0.1:7545'));

async function mine(){
  const accounts=await web3.eth.getAccounts();
  const coinbaseacc1=accounts[0];
  const coinbaseacc2=accounts[1];
  console.log('Mining ether on Ganache with coinbase address: ${coinbaseacc1}');

  while (true){
    try{
      await web3.eth.sendTransaction({
        from: coinbaseacc1,
        to: coinbaseacc2,
        value: 50,
      });
      console.log('Mined a new block!');
    } catch(err){
      console.error(err);
    }
  }
 }
 
 mine();
Step 6: Open Command Prompt. Install Web3 using ‘npm install web3’
Step 7: Run the JavaScript File using ‘node ethermine.js’
Step 8: Open Ganache and check the output.

