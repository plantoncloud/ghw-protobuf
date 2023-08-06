# GitHub Actions for Protobuf Definitions

These GitHub Actions workflows are for automating the release of Buffer Schema Registry (BSR) tags via the Planton Cloud. Two workflows are currently set up: one for releasing draft tags, and one for releasing full tags.

These workflows are set up in two different files:

- Draft release workflow: `.github/workflows/buf.release.draft.bsr.yaml`
- Full release workflow: `.github/workflows/buf.release.tag.bsr.yaml`

## Workflow Steps

1. **Checkout Code**: This step checks out your repository so that the workflow can access its content.

2. **Install Planton CLI**: This step installs the Planton CLI on the runner. This is required to interact with Planton Cloud.

3. **Login to Planton Cloud**: The Planton CLI is used to login to Planton Cloud. The `PLANTON_CLOUD_CLIENT_ID` and `PLANTON_CLOUD_CLIENT_SECRET` are required for this step and should be provided as secrets.

4. **Export Buf Credentials**: The Planton CLI is used to get the Buf credentials from the Artifact Store of Planton Cloud using the provided `PLANTON_CLOUD_ARTIFACT_STORE_ID`. The Buf username and token are then set as environment variables to be used in the next step.

5. **Setup Buf CLI**: The Buf CLI is set up using the previously set environment variables: `BUF_USERNAME` and `BUF_TOKEN`. 

6. **Buf Push Tag**: The final step is to push the tag to Buf using the input `BUF_TAG`.

## Usage

These workflows are designed to be called by other workflows in your repository. The workflows accept two inputs and require two secrets:

- Inputs:
  - `PLANTON_CLOUD_ARTIFACT_STORE_ID`: The ID of your Artifact Store in Planton Cloud where your Buf credentials are stored.
  - `BUF_TAG`: The semantic version of the Buf BSR tag you wish to release.

- Secrets:
  - `PLANTON_CLOUD_CLIENT_ID`: Your Planton Cloud client ID. This should be stored as a secret in your GitHub repository.
  - `PLANTON_CLOUD_CLIENT_SECRET`: Your Planton Cloud client secret. This should also be stored as a secret in your GitHub repository.

To call these workflows from another workflow in your repository, you can use the `workflow_call` event. Please consult the GitHub Actions documentation for further details.

## Contributing

If you have suggestions for how this GitHub Action could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

## License

This project is licensed under the [MIT License](LICENSE).
