# GeneAccess: Decentralized Genomic Data Marketplace

GeneAccess is a blockchain-based decentralized marketplace for genomic data. It enables secure, transparent, and efficient exchange of genomic datasets between dataset owners and researchers. By leveraging blockchain technology, GeneAccess ensures data integrity, privacy, and accessibility.

## Key Features

- **Dataset Registration**: Allows dataset owners to register genomic datasets with encrypted data and metadata.
- **Researcher Registration**: Enables researchers to register with verifiable credentials for access to datasets.
- **Access Requests**: Facilitates secure access requests from researchers to dataset owners.
- **Governance**: Supports researcher verification and reputation management through a contract owner.
- **Decentralization**: Operates without intermediaries, ensuring direct interaction between parties.

---

## Contract Structure

### Constants

- **ERR-NOT-AUTHORIZED**: Unauthorized action (`err u1`).
- **ERR-INVALID-DATASET**: Invalid or non-existent dataset (`err u2`).
- **ERR-ALREADY-PROCESSED**: Access request already processed (`err u3`).
- **ERR-PAYMENT-FAILED**: Payment failure (`err u4`).
- **ERR-INVALID-PARAMS**: Invalid input parameters (`err u5`).

### Data Variables

- **`dataset-count`**: Tracks the number of registered datasets.

### Maps

- **`datasets`**: Stores information about datasets (owner, encrypted hash, metadata, price, availability).
- **`dataset-access`**: Tracks access status for datasets by researchers.
- **`researchers`**: Contains researcher profiles (name, institution, credentials, verification status, reputation score).
- **`access-requests`**: Manages access requests with researcher details and approval status.
- **`researcher-contributions`**: Logs contributions made by researchers.

### Governance Variables

- **`contract-owner`**: Defines the owner of the contract with governance privileges.

---

## Functions

### Public Functions

#### Dataset Management

1. **`register-dataset`**: Registers a new dataset with encrypted data and metadata.
   - Parameters: `encrypted-data-hash`, `metadata-hash`, `price`
   - Returns: Dataset ID or error.

#### Researcher Management

2. **`register-researcher`**: Registers a researcher with name, institution, and credentials.
   - Parameters: `name`, `institution`, `credentials`
   - Returns: Success status or error.

#### Access Management

3. **`request-access`**: Requests access to a dataset.
   - Parameters: `dataset-id`
   - Returns: Success status or error.

4. **`approve-access`**: Approves access for a specific request.
   - Parameters: `dataset-id`, `request-id`
   - Returns: Success status or error.

#### Researcher Verification

5. **`verify-researcher`**: Verifies a researcher’s profile.
   - Parameters: `researcher`
   - Returns: Success status or error.

#### Reputation Management

6. **`update-reputation`**: Updates a researcher’s reputation score.
   - Parameters: `researcher`, `score`
   - Returns: Success status or error.

### Read-Only Functions

1. **`get-dataset-details`**: Retrieves details of a dataset.
   - Parameters: `dataset-id`
   - Returns: Dataset information.

2. **`get-researcher-profile`**: Retrieves the profile of a researcher.
   - Parameters: `researcher`
   - Returns: Researcher details.

3. **`get-access-status`**: Checks access status of a researcher for a dataset.
   - Parameters: `dataset-id`, `researcher`
   - Returns: Access status (true/false).

---

## Getting Started

1. Deploy the GeneAccess smart contract on the Stacks blockchain.
2. Initialize the `contract-owner` variable during deployment.
3. Interact with the contract using supported wallets or dApps to register datasets, researchers, and manage access.

---

## Security Considerations

- Data privacy is ensured by storing only encrypted data hashes on-chain.
- The contract owner must verify researchers to maintain the integrity of the marketplace.
- Reputation scores should be managed responsibly to avoid bias or misuse.

---

## Future Enhancements

- Implement support for tokenized payments for datasets.
- Add automated verification processes for researchers.
- Introduce governance voting mechanisms for community participation.

---

## License

GeneAccess is open-source and distributed under the MIT License.

