# Otalk

## What is it?
Otalk is an open source chat client powered by [XMPP](http://xmpp.org), [stanza.io](https://github.com/legastero/stanza.io), and [WebRTC](http://webrtc.org). You can think of it as an open source alternative to Skype.

While we have a version hosted at https://otalk.im, you can still run your own private instance.

## Installing

    git clone https://github.com/andyet/otalk.git
    cd otalk
    npm install
    node server

You can also run your own [XMPP server](https://github.com/andyet/otalk-server).

*Note:* If you're running your own XMPP server, and aren't using something like HAProxy to terminate SSL, then you might get errors in certain browsers trying to establish a WebSocket connection because the XMPP server is requesting an optional client certificate which makes the browser terminate the socket. To resolve that, visit the XMPP over Websocket URL directly (eg, example.com:5281/xmpp-websocket for Prosody) so that a client cert choice can be made. After that, the Otalk client should connect fine.

## What's included?

Otalk comes with support for:

### Message History Syncing

Using Message Archive Management (MAM, [XEP-0313](http://xmpp.org/extension/xep-0313.html)), your conversations can be archived by your server and pulled down by the Otalk client on demand.

### Active Chat Syncing

Ever used multiple IM clients at once, or swapped clients, and end up with disjointed conversations? Using Message Carbons ([XEP-0280](http://xmpp.org/extensions/xep-0280.html) all of your active conversations will be synced to your Otalk client (and vice versa if you other clients support carbons too).

### Reliable Connections

Sometimes you just lose your Internet connection, but with Stream Mangagement [XEP-0198](http://xmpp.org/extensions/xep-0198.html) your current session can be instantly resumed and caught up once you regain connection. Your messages will show as gray until they've been confirmed as received by your server.

### Message Correction

Made a typo in a message? Using Message Correction [XEP-0308](http://xmpp.org/extensions/xep-0308.html) you can just double tap the up arrow to edit and send a corrected version. In other clients that support correction, your last message will be updated in place and marked as edited.

### Timezone Indications

Working with someone in a different timezone? If the other person is using Otalk or another client that supports Entity Time ([XEP-0202](http://xmpp.org/extensions/xep-0202.html)) you'll see a reminder that they're 9 hours away where it's 4am and they're not likely to respond.

### Voice and Video
