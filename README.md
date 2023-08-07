## GitHub Workflows for Protobuf Projects

### **1. Build and Push Workflow**

#### Purpose:

This workflow is responsible for building your source code and pushing it to the specified artifact store.

#### Key Components:

- **Checkout**: Retrieves the codebase from the repository.
- **Install Planton CLI**: A utility tool for interfacing with the Planton Cloud services.
- **Login to Planton Cloud**: Authenticates the CLI with the cloud platform.
- **Export Buf Credentials**: Fetches credentials for interacting with Buf services.
- **Setup Buf CLI**: Prepares the Buf CLI tool for further usage.
- **Push to Buf**: This step pushes the relevant artifacts to Buf for further processing or storage.

### **2. Release Draft Workflow**

#### Purpose:

This workflow focuses on pushing a draft release of the artifacts, primarily for stages before an official release.

#### Key Components:
- **Checkout**: Retrieves the codebase from the repository.
- **Install Planton CLI**: Used for interacting with Planton Cloud.
- **Login to Planton Cloud**: Authenticates the CLI against Planton Cloud.
- **Export Buf Credentials**: Extracts and sets up Buf service credentials.
- **Setup Buf CLI**: Initializes the Buf CLI for further interactions.
- **Push Draft to Buf**: Pushes a draft version of the artifacts to Buf.

### **3. Release Tag Workflow**

#### Purpose:

Handles the official release of artifacts, tagging them for clear versioning and traceability.

#### Key Components:

- **Checkout**: Gets the repository code.
- **Install Planton CLI**: Ensures the CLI tool for Planton Cloud is present.
- **Login to Planton Cloud**: Securely logs into Planton Cloud.
- **Export Buf Credentials**: Retrieves and sets up necessary credentials for Buf.
- **Setup Buf CLI**: Readies the Buf CLI.
- **Push Tag to Buf**: Pushes the final, tagged version of the artifacts to Buf for release.

### **Usage Notes**:

To use these workflows, make sure you've set up the necessary secrets (`PLANTON_CLOUD_CLIENT_ID` and `PLANTON_CLOUD_CLIENT_SECRET`) in your GitHub repository. This ensures secure authentication with the Planton Cloud.

For workflows that require additional inputs, ensure those are provided during the workflow call.

## Support

If you encounter any issues or require further assistance, please file an issue in this GitHub repository.

## Contributing

If you have suggestions for how this GitHub Action could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

## License

This project is licensed under the [MIT License](LICENSE).
