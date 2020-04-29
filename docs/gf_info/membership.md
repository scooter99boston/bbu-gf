The concepts outlined herein provide an informational synopsis for the operation of the Bedrock Business Utility and participation in the Bedrock Business Directed Fund Project. The executable [BBU Participation Agreement](../gf_legal/contracts/bbu_participation_agreement.docx) (the "Participation Agreement"), specifically ```Exhibit B``` and ```Exhibit C```, supersedes this content.

## Membership requirements

### Utility Infrastructure
The Utility is an instance of a [ToIP Layer One Public Utility](https://github.com/hyperledger/aries-rfcs/tree/master/concepts/0289-toip-stack#layer-one-public-utilities-for-decentralized-identifiers-dids) based on [Hyperledger Indy](https://www.hyperledger.org/projects/hyperledger-indy) ("Indy"). In order to establish an operational budget for the Utility, several  infrastructure assumptions must be considered.

1. Budgetary requirements dictate how much revenue is required to keep the Utility sustainable.
2. Distributed ledger technologies, like Indy, leverage consensus algorithms that come with an optimal consensus threshold. This threshold value dictates the number of validator nodes required to operate the Utility. To meet the needs of a decentralized ledger, each validator node must be operated by an independent and unique participant. Therefore, a quantity requirement associated with one or more classes of members will be tied to the number of required validator nodes. Validator nodes may also be referred to as *utility infrastructure nodes* or *Stewards* from a historical [Sovrin Foundation](http://sovrin.org) context.

A balance between budget requirements and technology limitations will define the number of validator nodes required to operate the Utility. Initially this will be set at twenty-five (25) utility infrastructure nodes. The set of active nodes on the network will be periodically pulled from a pool of available nodes.

### Validator Node Pool
In order to efficiently operate the ledger associated with the Utility, a combination of production, test, and development environments are necessary. The BoD is responsible for defining the requirements associated with the validator pool. It is important to note that such BoD decisions will be influence by both technical performance restrictions as well as budgetary demands.

| Framework Facet | Required Quantity | Comment |
| --- | --- | --- |
| BoD Seats | 5 | Minimum Governing Members. BoD seats can increase but MUST not exceed 15 |
| Minimum Production Pool Size  | 25 | Considers production and BoD factors. |
| Minimum Test Pool Size  | 4 | Ledger used by Utility Service Provider and Technical Project contributors.  |
| Minimum Development Pool Size | 3 | Ledger used by Utility Service Provider and Technical Project contributors.||
| Minimum Total Pool Size | 32 | Considers requirements across all environments. |

## Membership Types

Building on our [Glossary](./glossary.md), participants in the Consortium are referred to as *Trust Community Members*. These business entities agreed to participate in the *Trust Community* known as the Bedrock Consortium. Participation in the Consortium is possible via formal legal contracts or membership agreements.

### Annual Membership

Private sector entities (businesses) can join and renew membership on an annual basis under three possible membership types:

| Membership Type | Validator Node Hosting Required | Authorized Endorser Privileges (Ledger Writes) |
| --- | --- | --- |
| Governing Member | Yes | Yes - Unlimited |
| Operational Member | Yes | Yes - Unlimited |
| Subscriber | No | Yes - Limited |

1. Governing Member:
    * **Description**: Members that are willing to contribute to the infrastructure, management, and financial needs of the Utility. Minimally, this requires the member to contribute a *Validator Node* to the operation of the Ledger.
    * **Ledger Roles**:
        1. *Validator Node*: Must host one or more utility infrastructure nodes as defined in ```Exhibit C``` of the Participation Agreement.
        2. *Transaction Endorser*: APPROVED for the endorsement for *Transaction Author* write requests.
    * **Restrictions**:
        1. Membership is limited to the number of Board of Director seats available.
        2. A FIFO waiting list is maintained by BoD to allow for new members to fill voids left by exiting members.
        3. Must sign the required ```Network Agreements``` as set forth in the Participation Agreement.
    * **Benefits**:
        1. A single representative on the Board of Directors.
        2. Appointment of representatives to any Committee within the Directed Fund.
        3. Approval, pending signed ```Network Agreements```, to act as a Transaction Endorser.
        4. Write Transactions as a Transaction Endorser as defined in ```Exhibit C``` of the Participation Agreement.

2. Operational Member
    * **Description**: Members that are willing to contribute to the infrastructure, management, and financial needs of the Network. Minimally, this requires the member to contribute a *Validator Node* to the operation of the Ledger.
    * **Ledger Roles**:
        1. *Validator Node*: Must host one or more utility infrastructure nodes as defined in ```Exhibit C``` of the Participation Agreement.
        2. *Transaction Endorser*: APPROVED for the endorsement for *Transaction Author* write requests.
    * **Restrictions**:
        1. Must sign the required ```Network Agreements``` as set forth in the Participation Agreement.
        2. Membership is limited to the number of nodes required to maintain optimal consensus performance. The optimal limit here must take into consideration a balance with decentralization requirements. The BoD will annually determine the number of nodes required to meet both consensus, decentralization, and budgetary requirements.
    * **Benefits**:
        1. Appointment of representatives to any Committee within the Directed Fund.
        2. Approval, pending signed ```Network Agreements```, to act as a Transaction Endorser.
        3. Write Transactions as a Transaction Endorser as defined in ```Exhibit C``` of the Participation Agreement.
        4. Members with continuous participation, can reserve a position to be invited as a Founding Steward via a FIFO waiting list.

3. Subscriber
    * **Description**: Members that are willing to be responsible for the endorsement of transactions to the ledger.
    * **Ledger Roles**:
        1. *Transaction Endorser*: APPROVED for the endorsement for *Transaction Author* write requests.
    * **Restrictions**:
        1. Must sign the required ```Network Agreements``` as set forth in the Participation Agreement.
    * **Benefits**:
        1. Appointment of representatives to any Committee within the Directed Fund.
        2. Approval, pending signed ```Network Agreements```, to act as a Transaction Endorser.
        3. Write Transactions as a Transaction Endorser as defined in ```Exhibit C``` of the Participation Agreement.

### Non-Membership Roles

1. Transaction Author
    * **Description**: Any entity (member or non-member) that is the submitter of a write transaction.
    **Ledger Roles**:
        1. *Transaction Author*: Interacts with a *Transaction Endorser* for the processing of write requests.
    * **Restrictions**:
        1. Only the transaction types outlined in the Utilities [ledger access policies](../gf_controlled/ledger_access_policies.md) and [ledger data policies](../gf_controlled/ledger_data_policies.md) are permitted.
        2. MUST sign the ```Network Agreements``` as defined in the Participation Agreement.
    * **Benefits**:
        1. Ability to use ledger for decentralized identity interactions.  

2. Associate
    * **Description**: A category of membership that is limited to Associate Members of the Linux Foundation. This membership category is limited to participation in Committees within the Technical Project.
