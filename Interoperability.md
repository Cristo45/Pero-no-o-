Work-In-Progress notes about the state of interoperability (and lack thereof) of wysiwidi sink and desktop_source with some other devices and stacks.

### Wysiwidi as sink

Device  | Software stack | WiFi P2P | RTSP | Stream | Notes
------- | -------------- | -------- | ---- | ------ | -----
Nexus 5 | Android 5.0.1 | [[images/yes.png]] | [[images/yes.png]] | [[images/question.png]] | See 1)
Some tablet | Windows 8.1 | [[images/question.png]] | [[images/no.png]] |  [[images/no.png]] | See 2)


### Wysiwidi as source

Device  | Software stack | WiFi P2P | RTSP | Stream | Notes
------- | -------------- | -------- | ---- | ------ | -----
Netgear Push2TV | Intel SDK? | [[images/yes.png]] | [[images/question.png]] | [[images/no.png]] | Playback fails. Format negotiation problem?
Actiontec SBWD100A |  | [[images/yes.png]] | [[images/no.png]] | [[images/no.png]] | RTSP negotiation fails: issue #69
LG TV |  | [[images/yes.png]] | [[images/question.png]] | [[images/no.png]] | Playback fails. Format negotiation problem?


1) Streaming from Android works acceptably with two caveats:
   * GStreamer tsdemux need a patch https://bugzilla.gnome.org/show_bug.cgi?id=743363
   * We must use a jitterbuffer element (currently requires a hack)

2) Windows won't show miracast sinks in the UI unless their device type is "television": this is not yet possible with Connman. After hacking that, RTSP connection succeeds at least sometimes: see issue #70 for failure to negotiate.  
