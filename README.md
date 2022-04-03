# War Times-NFT-Project
# XRP Network Specifically

<b>Description</b> <br>

Building out an NFT on the XRP network is a goal as the main Ethereum Network is flooded with work. While the XRP network is developing and maturing, 
learning more about NFTs and Blockchain help with hands on experience. 

This project will help solidify understanding and knowledge of how to not only build an NFT catalog, but also understand blockchain that has been all the 
hype the last few years with my current work. 

This project will allow me the ability to take pictures that I have from years of working abroad and that a historical for those military and war enthusiasts. 
NFT's are an intriguing way to share art that might otherwise just be sitting on a thumbdrive or buried in an archive somewhere. Some events that happen and 
the media keeps it buried and only those that lived through it are away, yet has huge impacts on lives and foriegn policy. 

This project will encompass Python but will contain artwork from first hand exposure and unedited pictures converted to NFT's for the world to share and relive 
at their will. 

  <b>Project Title (work in progress):</b> <br>
WAR TIMES

<b>Technologies Used</b>
Python 3.7 + 

XRP- Ledger Connection
xrpl-py (https://pypi.org/project/xrpl-py/) 

Rippled Core Server (Optional, recommended to test locally)
rippled (https://xrpl.org/install-rippled.html) 
* I ran my server on Microsoft Hyper-V. Ensure you set up enough space for updates, as I ran out of space with 40GB allocated and need to reinstall and increase the space allocation.*
 
<b>Network Client</b>
xrpl.clients (XRP Library to create network client to connect to the XRP Ledger)

<b>Keys and Wallets</b>
xrpl.wallet (module used to create a wallet from a given seef or via a Testnet Faucet)
xrpl.keypairs (module used to generate seeds and derive keypairs and addresses from the seed values. 
______________________
<b>How To:</b> <br>

Download and Intstall XRPL-Py: <br>
<b>xrpl-py</b> (https://pypi.org/project/xrpl-py/) <br>
using: <br>
pip3 install xrpl-py  <br>
sudp apt install xrpl-py <br>

*This library supports Python 3.7 and later.*

1.) Connect to XRP Ledger <br>
    * Make queries adn submit transactions, establishment of connections to XRP Ledger is needed and to do so utilize the xrp.clients.module from xrpl-py.<br>
    
    # Define the network client
      from xrpl.clients import JsonRpcClient 
      JSON_RPC_URL = "https://s.altnet.rippletest.net:51234/"
      client = JsonRpcClient(JSON_RPC_URL)
   
2.) Generate Wallet
    * To store key values and execute transactions on the XRP Ledger, a wallet is needed. To create a wallet, a set of keys and an address that's capable of being funded with XRP to meet the account reserve. <br>
    * The address is the Account Identifier and the utilization of Private keys to sign transactions are used to verify your transactions on the XRP ledger. 
    * To create a wallet on the Testnet you would utilize the generate_faucet_wallet method: 
    
      # Create a Wallet using the testnet faucet: 
      # https://xrpl.org/xrp-testnet-faucet.html
      from xrpl.wallet import generate_faucet_wallet
      test_wallet = generate_faucet_wallet(client. debug=True)
      
  * Wallet Instance should return the following: <br>

        # print output
        public_key:: 022FA613294CD13FFEA759D0185007DBE763331910509EF8F1635B4F84FA08AEE3
        private_key:: -HIDDEN-
        classic_address: "Your personal wallet address"
        
3.) Sign Transaction <br>
    * To sign a transaction: <br>
         
         # Sign the Transaction
         from xrpl.transaction import safe_sign_and_autofill_transaction
         my_tx_payment_signed = safe_sign_and_autofill_transaction(my_tx_payment, test_wallet, client)
         
4.) Send Transactions <br>
    * To send a transaction: <br>
      
        # Submit and send the transaction
        from xrpl.transaction import send_reliable_submission
        tx_response = send_reliable_submission(my_tx_payment_signed, client)
        
  
______________________

*To Be Updated
