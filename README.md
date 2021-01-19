
### A Novel Approach for Supply Chain Management using IoT Hyperledger Fabric Network

## Getting Started

Supply Chain Management limits manufacturing cost, and saves time in its creation cycle. Business standards have got a moment to spare supply chain where retail deals consequently single renewal requests to manufacturers. Retailers would be able to restock as fast as item is sold. One approach, is to additionally enhance this procedure and investigate the information from supply chain accomplices to see where further modifications can be made. With Supply Chain Management getting so muddled, numerous sort of developments have been done to enhance supply chain execution process. Programming strategies spread the extentfrom supplying auspicious and precise supply chain data to checking deals with the goal that manufacturers produce and ship just as a lot of supply items can be sold by lessening unneeded stock, the two manufacturers and retailers can bring down the expenses of creating, dispatching merchandise and enterprises. So there are a lot of researches on how to make the supply chainprocess faster and more efficient. Machine learning, AI techniques and algorithms are designed to make the system more durable and trustworthy. Researchers are seeking the solutions to make supply chain traceable and secure with fast communication measures. Etherum is the mostly used public Blockchain that is used to develop smart systems. Etherum has some developing benefits like tested development architecture and development environment. Ethurum is an open source platform mostly used for cryptocurrencies but developers are also using it for developing smart apps with the combination
This business network defines:
Participants: Supplier Importer Retailer Regulator

Assets: ProductListingContract

Transactions: createProductListing transferListing checkProducts updateExemptedList

## Architecture
![alt text](https://github.com/shanibhai/supplychain/blob/main/images/arch.jpg)

## Prerequisites

* IBM Cloud Account
* IBM Cloud CLI
* Docker
* Docker Compose - v1.8 or higher
* NPM - v5.6.0 or higher
* nvm - v8.11.3 (use to download and set what node version you are using)
* Node.js - node v8.11.3 ** don't install in SUDO mode
* Git client - v 2.9.x or higher
* Python - 2.7.x
```

```

## Installing

A step by step series of examples that tell you how to get a development env running

```
* Installing Hyperledger Composer Development Tools
* Configure and start Hyperledger Fabric network
* Generate the Business Network Archive (BNA)
* Deploy the Business Network Archive using Composer Playground
* Deploy the Business Network Archive on Hyperledger Composer running locally
```

* Check installation prerequisites and clone the repo
* Create and Access IBM Cloud Kubernetes Cluster
* Deploy Hyperledger Fabric
* Deploy Hyperledger Fabric SDK for Node.js
* Deploy Node-RED

## Step by step deployment

### 1. Installing Hyperledger Composer Development Tools
#### Note: You may need to run these commands in superuser sudo mode. sudo allows a permitted user to execute a command as the superuser or another user, as specified by the security policy. Additionally, you will be installing the latest version of composer-cli (0.19.5). If you have an older version installed, go ahead and remove it by using the command:

```
npm uninstall -g composer-cli
```
* The composer-cli contains all the command line operations for developing business networks. To install composer-cli run the following command:
```
npm install -g composer-cli@0.19.5
```
* The generator-hyperledger-composer is a Yeoman plugin that creates bespoke (e.g. customized) applications for your business network. Yeoman is an open source client-side development stack, consisting of tools and frameworks intended to help developers build web applications. To install generator-hyperledger-composer run the following command:
```
npm install -g generator-hyperledger-composer@0.19.5
```
* The composer-rest-server uses the Hyperledger Composer LoopBack Connector to connect to a business network, extract the models and then present a page containing the REST APIs that have been generated for the model. To install composer-rest-server run the following command:
```
npm install -g composer-rest-server@0.19.5
```
* When combining Yeoman with the generator-hyperledger-composer component, it can interpret business networks and generate applications based on them. To install Yeoman run the following command:
```
npm install -g yo@2.0.0
```
### 2. Configure and start Hyperledger Fabric network
First download the docker files for Fabric in preparation for creating a Composer profile. Hyperledger Composer uses Connection Profiles to connect to a runtime. A Connection Profile is a JSON document that lives in the user's home directory (or may come from an environment variable) and is referenced by name when using the Composer APIs or the Command Line tools. Using connection profiles ensures that code and scripts are easily portable from one runtime instance to another.

The PeerAdmin card is a special ID card used to administer the local Hyperledger Fabric. In a development installation, such as the one on your computer, the PeerAdmin ID card is created when you install the local Hyperledger Fabric.

First, clone the contents of this repo locally and cd into the project folder by running these commands:
```
git clone https://github.com/shanibhai/supplychain.git
cd supplychain
```
Create a directory fabric-dev-servers and, get the .tar.gz file that contains the tools to install Hyperledger Fabric:
```
mkdir ./fabric-dev-servers && cd ./fabric-dev-servers
```
```
curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz
tar -xvf fabric-dev-servers.tar.gz
```
Then, start the Fabric and create a PeerAdmin card using the following commands:
```
./downloadFabric.sh
./startFabric.sh
./createPeerAdminCard.sh
```
For stopping the fabric, but you donnot need to stop here:
```
./stopFabric.sh
./teardownFabric.sh
```
### 3. Generate the Business Network Archive (BNA)
To check that the structure of the files is valid, you can now generate a Business Network Archive (BNA) file for your business network definition. The BNA file is the deployable unit -- a file that can be deployed to the Composer runtime for execution.

Use the following command to generate the network archive:
```
npm install
```
You should see the following output:
```
Creating Business Network Archive

Looking for package.json of Business Network Definition
	Input directory: /Users/ishan/Documents/git-demo/supplychain

Found:
	Description: Sample food supplier verification network
	Name: food-supply
	Identifier: food-supply@0.0.1

Written Business Network Definition Archive file to
	Output file: ./dist/food-supply.bna

Command succeeded
```
The composer archive create command has created a file called food-supply.bna in the dist folder.

You can test the business network definition against the embedded runtime that stores the state of 'the blockchain' in-memory in a Node.js process. From your project working directory, open the file test/foodTest.js and run the following command:

```
npm test
```
You should see the following output :
```
> food-supply@0.0.1 test /Users/ishan/Documents/demo/supplychain
> mocha --recursive

  #composer.food.supply
    ✓ Transfer ProductListing to Importer (67ms)
    ✓ Exempt Check for ProductListing (98ms)
    ✓ Transfer ProductListing to Retailer (95ms)

  3 passing (2s)
  ```
  
 ### 4. Deploy the Business Network Archive using Composer Playground

Open Composer Playground. If you have previously used Playground, be sure to clear your browser local storage by running localStorage.clear() in your browser Console, or to use the option presented to you by [Composer Playground](http://composer-playground.mybluemix.net/).

Next, click the Deploy a new business network button.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/deploy-new-network-1.png)

and drop the food-supply.bna file (downloaded above) in the Drop here to upload or browse area.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/deploy-new-network-2.png)

Finally, click Deploy to deploy the BNA.

Once imported, click Connect now on the admin card. You should see the following:

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/composerplayground.png)

To test your Business Network Definition, first click on the Test tab:

In the Supplier participant registry, create a new participant. Make sure you click on the Supplier tab on the far left-hand side first and click on Create New Participant button.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/createparticipant.png)

Enter the following information to create the supplier.

```
{
  "$class": "composer.food.supply.Supplier",
  "supplierId": "supplierA",
  "countryId": "UK",
  "orgId": "ACME"
}
```
Similarly create retailer, regulator and importer participants by selecting the respective tabs and provide the information as follows:
```
{
  "$class": "composer.food.supply.Retailer",
  "retailerId": "retailerA",
  "products": []
}
```
```
{
  "$class": "composer.food.supply.Regulator",
  "regulatorId": "regulatorA",
  "location": "SF",
  "exemptedOrgIds": ["ACME","XYZ CORP"],
  "exemptedProductIds": ["prodA","prodB"]
}
```
```
 {
  "$class": "composer.food.supply.Importer",
  "importerId": "importerA"
}
```
Now we are ready to add Access Control. Do this by first clicking the admin tab followed by ID Registry to issue new IDs to the participants and to add these IDs to the wallet. Please follow the instructions as shown in the images below:

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/admintab.png)

Click on Issue New ID button to create new IDs.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/generateNewId.png)

Repeat the above step to also create IDs for the importer, regulator and retailer. Once you completed the creation of the four IDs, select the Supplier id from the list and click Use now.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/selectid.png)

Next, click on the test tab to perform createProductListing and transferListing transactions. Click the Submit Transaction button and select the createProductListing transaction from the dropdown to create a product listing for the list of products. The products array element contains information about the productid and quantity separated by ,.

```
 {
  "$class": "composer.food.supply.createProductListing",
  "listingtId": "pl1",
  "products": ["prodA,5","prodB,2"],
  "user": "resource:composer.food.supply.Supplier#supplierA"
}
```
After executing the transaction successfully, a productListing will be created in ProductListingContract registry.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/productListing.png)

Similarly, submit a transferListing transaction to transfer the productListing to the Importer.

```
{
  "$class": "composer.food.supply.transferListing",
  "ownerType": "supplier",
  "newOwner": "resource:composer.food.supply.Importer#importerA",
  "productListing": "resource:composer.food.supply.ProductListingContract#pl1"
}
```
Now importerA will be the owner of ProductListingContract and the status will be EXEMPTCHECKREQ. Also, the productListing will be removed from the Supplier view. Now select the Importer ID from the ID Registry and submit a checkProducts transaction to perform the exempt check for the products.

```
{
  "$class": "composer.food.supply.checkProducts",
  "regulator": "resource:composer.food.supply.Regulator#regulatorA",
  "productListing": "resource:composer.food.supply.ProductListingContract#pl1"
}
```
A successful execution of the transaction will change the status of productListing to CHECKCOMPLETED. Now perform a transferListing transaction to transfer the products to retailer.

```
{
  "$class": "composer.food.supply.transferListing",
  "ownerType": "importer",
  "newOwner": "resource:composer.food.supply.Retailer#retailerA",
  "productListing": "resource:composer.food.supply.ProductListingContract#pl1"
}
```
The transaction will the change the owner of ProductListingContract and update the list of products in Retailer registry. Select the Retailer id from the ID Registry and view the updated registries.

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/retailerPL.png)

![alt text](https://github.com/shanibhai/supplychain/blob/main/images/retailer.png)

```
You can also use the default System user to perform all the actions as we have a rule in permissions.acl to permit all access System user.
```

## Author

* **Muhammad Rehan** - *Initial work* - [AirianzTech](https://airianztech.com)


## License

This project is licensed under the APACHE License 2.0 - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* BEST OF LUCK *
