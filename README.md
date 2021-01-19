
A Novel Approach for Supply Chain Management using IoT Hyperledger Fabric Network

## Getting Started

Supply Chain Management limits manufacturing cost, and saves time in its creation cycle. Business standards have got a moment to spare supply chain where retail deals consequently single renewal requests to manufacturers. Retailers would be able to restock as fast as item is sold. One approach, is to additionally enhance this procedure and investigate the information from supply chain accomplices to see where further modifications can be made. With Supply Chain Management getting so muddled, numerous sort of developments have been done to enhance supply chain execution process. Programming strategies spread the extentfrom supplying auspicious and precise supply chain data to checking deals with the goal that manufacturers produce and ship just as a lot of supply items can be sold by lessening unneeded stock, the two manufacturers and retailers can bring down the expenses of creating, dispatching merchandise and enterprises. So there are a lot of researches on how to make the supply chainprocess faster and more efficient. Machine learning, AI techniques and algorithms are designed to make the system more durable and trustworthy. Researchers are seeking the solutions to make supply chain traceable and secure with fast communication measures. Etherum is the mostly used public Blockchain that is used to develop smart systems. Etherum has some developing benefits like tested development architecture and development environment. Ethurum is an open source platform mostly used for cryptocurrencies but developers are also using it for developing smart apps with the combination
This business network defines:
Participants: Supplier Importer Retailer Regulator

Assets: ProductListingContract

Transactions: createProductListing transferListing checkProducts updateExemptedList

## Architecture
![alt text](https://github.com/shanibhai/supplychain/blob/main/images/arch.jpg)

### Prerequisites

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

### Installing

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

## Running the tests

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

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
