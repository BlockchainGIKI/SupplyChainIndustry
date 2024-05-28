# Supply chain

## Prerequisites
- Your system must has virtual machine and ubuntu install in it.
- Make sure your system has prerequisites installed i.e., docker, docker-compose, Golang, and curl. If not please install: https://hyperledger-fabric.readthedocs.io/en/release-2.5/prereqs.html
- Make sure that the version of Golang is 1.21, which is compatible with the docker images used in this project.
- Install the Fabric and fabric samples: https://hyperledger-fabric.readthedocs.io/en/release-2.5/install.html

## Steps:
- Move to channel folder: artifacts/channel and run the create-artifacts.sh script by ./create-artifacts.sh
- Then, move to the sub folder of setup1 and run this command in each folder: docker-compose up -d.
- Next, move to the farmer folder and run the ./createChannel.sh to create the channel and let the farmer peers to join this channel.
- When the channel is created then peers of other stakeholders should also join the channel, which can be done by moving to each folder of setup1 except orderer and run joinChannel.sh command.
- Once the channel is created then install the chaincode on each peer by going to each sub folder of setup1 except orderer and run the script: ./installandapprovechaincode.sh, while ./deploychaincode.sh in the farmer folder. Remember run these functions first of the depolychaincode file in the farmer folder: packageChaincode, installChaincode, queryInstalled, approveForMyOrg1 and checkCommitReadyness.
- Once all the chaincode is installed on all the peers, then run these functions of deploychaincode: commitChaincodeDefination and queryCommitted.
- Finally, run the chaincodeInvokeInit() function and then other functions such as chaincodeInvokeCreateBatch, chaincodeInvokeCreateFarmer, chaincodeInvokeFarmerData1, chaincodeQuery etc to commence the transactions on the channel.
