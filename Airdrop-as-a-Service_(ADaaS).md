# Airdrop-as-a-Service (ADaaS)

*Airdrop* is DevRev’s solution to migrate data. It allows our customers to bring in their existing data from external systems to DevRev,
export data back to external systems, and keep data in sync between DevRev and the external systems.
You can read more about Airdrop in the [general documentation](https://docs.devrev.ai/import#airdrop-features).

*Airdrop-as-a-Service (ADaaS)* gives snap-in developers the ability to integrate with DevRev’s Airdrop functionality.
It enables developers to create external workers (extractors and loaders) to bring data from various external systems.

<Tip>
  DevRev offers a repository template to help you create ADaaS snap-ins. Refer to 

  [Getting started](getting-started)

   for instructions.
</Tip>

```mermaid
flowchart TD
%%{init: {
    'theme': 'base',
    'themeVariables': {
        'fontFamily': 'Segoe UI',
        'lineColor': '#7d7f7c'
}}}%%
externalSystem[External system]
worker([Worker])
s3interact[s3interact]
airdrop[Airdrop]
s3[(AWS S3)]

	externalSystem <-- Get/create users, issues, ... --> worker
	
	worker <-- Exchange artifact upload/download URLs --> s3interact
	worker <-- Upload/download artifacts --> s3
	worker <-- ADaaS messages and REST API --> airdrop

	
	subgraph DevRev
	s3interact <-- Prepare upload/download URL --> s3
	airdrop <-- Download/upload artifacts --> s3
	end

```

An *extractor* is a function in an ADaaS-capable snap-in responsible for extracting data from an *external system*, such as Jira, Zendesk,
or HubSpot. It uses a standardized communication protocol for talking to Airdrop and a standardized
data structure for all the files it extracts and processes, so that they can be seamlessly imported into DevRev.

## Sync runs

Airdrop functions are executed in the context of *sync runs*, which is a directed operation that spans over many invocations
of an ADaaS snap-in to bring the data to DevRev or load the data to the external system.

A *forward sync* is a sync run from an external system to DevRev. An extractor function in the snap-in is responsible for extracting data from the
external system.

A *reverse sync* is a sync run from DevRev to an external system. It uses a loader function, to create or update data
in the external system.

## Keyrings

*Keyrings* are a DevRev-specific mechanism for managing authentication to external systems.
They are called **Connections** in the DevRev app.

Keyrings provide a secure way to store and manage credentials within your DevRev snap-In.
This eliminates the need to expose sensitive information like passwords
or access tokens directly within your code or configuration files, enhancing overall security. They also provide a valid
token by abstracting OAuth token renewal from the end user.

A keyring is used by a worker to authenticate to the external system in API calls. They include the key (for example,
a PAT or API key), its type, the organization ID for which a key is valid, and in some cases the organization name.

Refer to [Keyrings](/snapin-development/references/keyrings) for more information.