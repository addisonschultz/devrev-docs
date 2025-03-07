# Push notifications

This section describes the process of setting up push notifications within the DevRev SDK. By completing this setup, users of your mobile app's support chat will receive notifications whenever a DevRev customer experience engineer responds.

## Prerequisites

* **Apple Developer Program access**: Required for setting up iOS push notifications.
* **Google Developer Account and Firebase project**: Necessary for configuring Android push notifications.
* **Access to credentials and files**: Ensure you have your Bundle ID, Team ID, and APNs/FCM keys readily available.
* **Admin access to DevRev PLuG settings**: Required to configure PLuG notifications within DevRev.
* **Mobile SDK integration**: Ensure that the DevRev SDK is integrated with your Android or iOS app and tested to facilitate notifications.

## Configure push notifications

1. Accessing PLuG Settings

   a. Go to **Settings** > **Support** > **PLuG settings** > **Mobile push notifications**.

   b. Click **+ Configure app** > and select either **iOS App** or **Android App** based on your target platform.

<Callout intent="note">
  If you are configuring an iOS app, proceed to step 2. For an Android app, skip to step 3.
</Callout>

2. iOS app configuration

   a. After selecting **iOS App**, fill out the configuration form:

   * **App name**: Enter your iOS app's name.
   * **Bundle ID**: Provide your app's unique identifier in reverse domain notation, such as, `com.example.app`. Refer to [Apple's documentation](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) to confirm your bundle ID.
   * **Apple Team ID**: Enter the 10-character Apple Team ID assigned to your organization. Details are available in [Apple's Team ID documentation](https://developer.apple.com/help/account/manage-your-team/locate-your-team-id/).
   * **Key ID**: Enter the Key ID for your APNs Auth Key. See [Apple's Key ID documentation](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns) for further instructions.
   * **Upload APNs Auth Key**: Upload the `.p8` APNs Auth Key file (maximum size: 10 MB).
   * **Sandbox Environment**: Check this for development environments to enable notifications in debug builds.

   b. Click **Save App** to complete the iOS setup.

3. Android app configuration

   a. Select **Android App** and complete the configuration form:

   * **App name**: Enter your Android app's name.
   * **Bundle ID**: Provide your app's unique identifier in reverse domain notation, such as, `com.example.app`. Refer to [Google’s documentation](https://developer.android.com/studio/build/application-id) to confirm your bundle ID.
   * **Upload Service Account Key**: Upload a Service Account Key JSON file (up to 10 MB) generated via Google Cloud for Firebase Cloud Messaging (FCM). Create this key following [Google’s documentation](https://firebase.google.com/docs/).

   b. Click **Save App** to complete the Android setup.

4. Click **Save and Publish** to activate push notifications in your DevRev SDK.

Upon completing these steps, push notifications are operational in the DevRev SDK. Users engaged in your app's support chat receive real-time notifications when a DevRev customer experience engineer responds, ensuring effective and timely communication.

For additional support or inquiries, refer to the latest [Apple developer documentation](https://developer.apple.com/) and [Android developer documentation](https://developer.android.com/) as guidelines may change.