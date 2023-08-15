# LensShare

Lens Share is the official implementation of the [LIP-3](https://github.com/lens-protocol/LIPs/blob/main/LIPs/lip-3.md).

The number of apps flourishing within the Lens ecosystem has highlighted a need for URL sharing across platforms in a manner that's app-agnostic.

Users should be free to engage with their app of choice. However, there can be situations where the users content might not be accessible on their preferred Lens app. That's why we've looked into augmenting the user experience.

The solution? A standardized link-sharing strategy and an app-agnostic interface. This promises smoother integration across apps within the Lens ecosystem, all the while preserving the credit to the original app.

Lens Share is composed of 3 elements:

* a standard URL format;
* a Lens apps registry where builders can add their app to;
* a UI capable of showing the most appropriate apps options based on content and user's device/browser.

### Lens Share Link

The Lens Share Link is the standard URL format for Lens Publications and Lens Profiles.

#### Publication Lens Share Link

The Publication URL format is:

```
https://share.lens.xyz/p/<id>[?by=<appId>]
```

Where:

* `<id>` is the publication ID.
* `<appId>` is an optional parameter that reflect the Lens App ID of the app used to generate the Lens Share Link. This is used to give priority to the app that generated the Lens Share Link when the user opens the Lens Share Link.

Some examples:

* `https://share.lens.xyz/p/0x01`
* `https://share.lens.xyz/p/0x01?by=lenster`
* `https://share.lens.xyz/p/0x01?by=orb`

#### Profile Lens Share Link

The Profile URL format is:

```
https://share.lens.xyz/u/<handle>[?by=<appId>]
```

Where:

* `<handle>` is the profile handle inclusive of the `.lens` suffix but without the `@` prefix (e.g. `alice.lens`, `bob.lens`, etc.).
* `<appId>` is an optional parameter that reflect the Lens App ID of the app used to generate the Lens Share Link. This is used to give priority to the app that generated the Lens Share Link when the user opens the Lens Share Link.

Some examples:

* `https://share.lens.xyz/u/lenspedia.lens`
* `https://share.lens.xyz/u/lenspedia.lens?by=lenster`

### For Users

When sharing a Lens Publication or a Lens Profile link on social media adopt the Lens Share Link format to enable your audience to chose the best Lens app for the given content.

### For Builders

#### Adopt the Lens Share URL format

In an healthy ecosystem links adopting the Lens Share URL gives your app the opportunity to be seen on any relevant Lens Share URL. When implementing a share capability in your app, consider using the Lens Share Link format, this is your opportunity to give back to the rest of the ecosystem.

Remember to add the `?by=<app-id>` parameter to the share URLs generated from your app so your app will be the first in the list on your URLs.

#### Add your App Manifest

To have your app listed on the Lens Share UI follow these [instructions](https://github.com/lens-protocol/lens-share#add-your-app-manifest). Use the [App Manifest Schema](https://share.lens.xyz/schemas/1.0.0/app-manifest) to know what are the options and meaning of each field/property.

#### Submit proposals

If you have a great idea to improve Lens Share, feel free to open a GitHub Issue to start the conversation.

\
