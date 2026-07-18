🏗️ Operating Principle
This tool acts as a "CLI Command Builder Assistant". Instead of manually calculating UTXOs, transaction fees (Fee), and change amounts (Change), this tool will automatically draft the complete ⁠cardano-cli⁠ command code for you.
 On Web (Local): You input the parameters, and the tool generates the corresponding ⁠cardano-cli build-raw⁠ command.
 On Offline Machine (CLI): You copy that command and paste it into the Terminal on a computer that has ⁠cardano-cli⁠ installed and contains the secret key to execute it.
📋 Execution Guide

Step 1: Download and use the tool
 Download the ⁠Tool-Cardano.html⁠ file to your personal computer and open it.
 Enter the information: Blockfrost Project ID, YOUR wallet address, source UTXO, receiver wallet address, and the amount.
 Click "Generate Build-Raw Command". A CLI code snippet will appear.
 Copy that code snippet.
 
Step 2: Run the command on the Offline computer
On the computer that has ⁠cardano-cli⁠ installed and contains the ⁠payment.skey⁠ file:
 Open Terminal, paste the code snippet you just copied, and press Enter.
Example of the command you will receive:
cardano-cli transaction build-raw \⁠
⁠--tx-in [TX_ID_1] \⁠
⁠--tx-in [TX_ID_2] \⁠
⁠--tx-out [ADDR]+[AMOUNT] \⁠
⁠--fee [FEE] \⁠
⁠--out-file tx.raw⁠
Once executed, the ⁠tx.raw⁠ file will be created in your directory.

Step 3: Sign and Submit the transaction
After obtaining the ⁠tx.raw⁠ file, proceed with the signing step:
Sign the transaction:
cardano-cli transaction sign --tx-body-file tx.raw --signing-key-file payment.skey --mainnet --out-file tx.signed⁠

Step 4: Push the transaction to the Blockchain (Web Tool)
After generating the signature file on your offline machine, return to the Web Tool:
 Select the "Submit Transaction" feature (or the Signature File Upload section).
 Upload the ⁠tx.signed⁠ file (the signature file you created in the previous step) to the tool.
 Click "Submit/Broadcast Transaction". The tool will use the Blockfrost API to push your signed transaction directly to the Cardano network.
 
🔑 How to get a Blockfrost Project ID
For the tool to be able to retrieve UTXO data and submit transactions, you need a Project ID from Blockfrost. This is a service that provides data infrastructure for Cardano.
Steps to perform:

 Register an account: Visit https://blockfrost.io/ and click "Sign Up" to create an account (using Email or GitHub).
 Create a new Project: After logging in, click the "Create project" button on the Dashboard page. Select the network: Mainnet (to perform real transactions) or Preprod/Preview (if you only want to test).
 Copy the Project ID: After creation, an information panel will appear. In the "Project ID" section, copy the entire long string of characters.
 Use it in the Tool: Return to your Cardano tool and paste the copied string into the "Blockfrost Project ID" box.
If you find this tool helpful for securing your Cardano assets, consider supporting the development:
Cardano (ADA): ⁠addr1q8myf69ztrw89fpv0l6tmgjt2p8kt59xygu0w30nv6rcpdfay2qfwe8zk0vefye4gw0v8nxxrnwpa8mlgzhuaqjqwffs2ru9mv⁠
Every contribution helps keep this project updated, secure, and free for everyone
