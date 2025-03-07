# Snap-in resources

Snap-in resources are objects specific to each user for a snap-in. These objects can be

* Keyrings
* Inputs
* Event sources

For a snap-in to access these resources, the user must configure **My Settings** of the snap-in config and enable it.
The snap-in can get these resources using the `snap-ins.resources` [beta API](https://docs.devrev.ai/beta-api-spec#/operations/snap-ins-resources) by specifying the  snap-in ID in the `id` field and the user ID in the `user` field.

<Callout intent="note">
  This API can only be called by the service account associated with the snap-in.
</Callout>