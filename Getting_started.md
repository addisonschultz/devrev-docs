# Getting started

## Before you begin

* If you have not created a development organization on DevRev before, create a dedicated
  [DevRev organization for development purposes](https://app.devrev.ai/) where you will be publishing your ADaaS snap-in.
* Install required tools and packages:
  * [devrev-cli](https://developer.devrev.ai/snapin-development/references/cli-install) (version 4.7 or higher)
  * [jq](https://stedolan.github.io/jq)
  * [golang](https://go.dev/doc/install)
  * [nodejs](https://nodejs.org/en/download/package-manager) (version 18.x.x+ or higher)

## Setting up the snap-in

1. Create a new repo from the [ADaaS template repo](https://github.com/devrev/adaas-template). Select *Use this template* and
   then *Create a new repository*.
2. Copy `.env.example` to `.env` and fill in the required variables.
3. Configure a keyring for the external system in the `manifest.yaml`.
   Refer to [Keyrings](/snapin-development/references/manifest#developer-keyrings) for instructions.
4. Deploy a draft version of your snap-in to your dev org using `make deploy`.
5. Install the snap-in in your DevRev at **Settings** > **Snap-ins** > **Install snap-in**.
6. Define the connection at **Settings** > **Imports** > **Connections**.
7. Create an import at **Settings** > **Imports** > **Import**.

## Observability

* To observe logs from your snap-in in your development environment:
  ```
  devrev snap_in_package logs | jq
  ```
* To open logs in your favorite editor:
  ```
  devrev snap_in_package logs | code -
  ```

For more information, refer to [Debugging](/snapin-development/debugging).