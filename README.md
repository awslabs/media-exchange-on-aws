<<<<<<< HEAD
## My Project

TODO: Fill this README out!

Be sure to:

* Change the title in this README
* Edit your repository description on GitHub

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This project is licensed under the Apache-2.0 License.

=======
## Introduction
Traditional file transfer services for Media supply chain are expensive, can add unnecessary hours to a workflow making quick-turn challenging, and not optimized for in-cloud media ecosystems. AWS Customers and ISV Partners can now take advantage of utilizing AWS as a common media storage foundation to create direct hand-offs within the ecosystem eliminating 3rd party delivery mechanisms and the associated time, cost and security concerns. This new Solution, called Media Exchange, AWS Customers and ISV Partners can ensure optimal quality, sustain a consistent understanding of the asset state and confirm asset receipt. The goal of this project is to re-examine media supply-chain with cloud-optimizations in mind, and define a MVP solution that can be deployed with CloudFormation templates. When the solution is deployed in a customer account, a de-facto exchange standard is established with other Media Exchange users.

## Current State  
The traditional file transfer model presents a few key challenges including (a) egress, transfer licensing and transfer costs add up (In case of managed offerings, a per gigabyte transfer cost), (b) content is potentially exposed to a security breach equated to the weakest link in the supply chain, (c) there is often lack of visibility to receipt verification, and (d) file corruption can happen during transfer creating file corruption issues to mitigate. Traditional file transfer services require that you manage a fleet of servers and agents to transfer assets. The sender and receiver must utilize the same software to be able to exchange assets. In a complex distribution model, your network of senders or receivers may use different software protocols requiring an investment on your side in multiple protocols to support multiple partners.  The establishment of a new transfer exchange between Publisher and Subscriber under the existing system can be time consuming and add layers of paperwork and approvals. Moreover, only some of the file transfer service
es offer a cloud-based offering that can deliver assets to object stores in cloud which helps with one-to-many transfers over the on-prem offerings. In today’s complex distribution model, staff must manage content egress, schedule transfers, send or monitor notifications and follow up for verification of receipt across different interfaces. AWS Media Exchange is Solution to address these problems.

## What is Media Exchange
The Media Exchange Solution puts a shared object store (S3 bucket) between publishers and subscribers in a separate, secure AWS account. The sender copies the assets into this shared storage area and creates permissions so that the receivers can pull the content from the S3 bucket. In this Solution, the publishers copy to the S3 bucket and the subscribers pull from there. The assets never leave the S3 data plane in this process, thereby (a) there are no per/GB data egress and transfer costs, (b) this eliminates that egress, schedule and delivery time dependencies, (c) is very fast and (d) there are no servers to manage. The assets are secure by default, encrypted at rest and in transit. Optionally, the assets are encrypted by keys managed by AWS Key Management Service. In the standard deployment model, Media Exchange is deployed in its own account. Assets are stored in this account only for the purposes for transfer and allows a very limited set of permissions to Publishers and Subscribers. Moreover, Media Exchange account works like a temporary custodian but does not have read/write permissions to the assets shared through it. Publishers and Subscribers are on-boarded with CloudFormation templates. Each publisher gets their own S3 bucket to share assets from and each subscriber gets a unique prefix (folder). The publishers share content by copying assets under these named prefixes. A subscriber can only view assets under their assigned prefix and import assets that are shared to them. Publishers and subscribers can only perform these operations from their respective AWS accounts that they have on-boarded with into Media Exchange. A primary benefit of this process is that there are no credentials to share between Publishers and Subscribers. All operations on the assets are tracked via AWS and S3 logs. The assets in the Media Exchange account are lifecycle deleted after a Publisher-defined period.
This is a seamless addition to the current workflow for your customers who use S3 as part of their Media Supply Chain. This Solution is a new offering that is a separate secure AWS account linked to your existing AWS Account. This Solution can also integrate with native AWS file transfer offerings like data sync, snow* devices to help transfer assets between physical locations for customers who do not currently integrate S3 into the media supply chain. You can use native AWS APIs and tools to move content across large geographical distances by leveraging AWS global infrastructure. decoupled transfer process is intrinsically more robust as the assets never leave the S3 data plane The quality risk is much lower in Media Exchange than having to transfer over the internet.
>>>>>>> 2dd7b08 (Splitting the README.md)
