### Abstract

This write-up aims to help you locate all the moving parts for
setting up your Firebase Messaging for your web app.


### Prerequisites

* Firebase project
* Firebase registered web app


### Usage

Copy and paste the `<script>` tags from `index.html`
into your own page.

Copy and paste `firebase-messaging-sw.js` into your app's
public folder.

Replace all `XXXX` values with your own.


### Successful Setup

If everything has been set up successfully, you should see:

* a running service worker in your Element Inspector > Application > Service Workers
* a TOKEN console log message.


### Testing

For Ruby you can use [FCM](https://github.com/decision-labs/fcm).

```ruby
require 'fcm'

fcm = FCM.new("my_server_key")
registration_ids = [<USE_THE_TOKEN_FROM_THE_BROWSER_CONSOLE>]
options = {
            "notification": {
              title": "Test Title",
              "body": "Test Body"
            }
          }

fcm.send(registration_ids, options)
```

If you had the browser opened to the project,
you should see "Foreground message received" in the browser console.

If you did not have the browser opened to the project,
you should see "Background message received" either in the console
or in the Service Worker's log, depending on the browser.

