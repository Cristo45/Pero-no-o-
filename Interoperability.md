Work-In-Progress notes about the state of interoperability (and lack thereof) of wysiwidi sink and desktop_source with some other devices and stacks.

### Wysiwidi as sink

Source Device  | Software stack | Wi-Fi P2P | RTSP | Stream | Notes
-------------- | -------------- | --------- | ---- | ------ | -----
Nexus 5 | Android 5.0.1 | [[images/yes.png]] | [[images/yes.png]] | [[images/yes.png]] | Playback is not perfect, but works
Some tablet | Windows 8.1 | [[images/question.png]] | [[images/no.png]] |  [[images/no.png]] | See 1) and issue #70.


### Wysiwidi as source

Sink device  | Software stack | Wi-Fi P2P | RTSP | Stream | Notes
------------ | -------------- | --------- | ---- | ------ | -----
Microsoft Wireless Display |  | [[images/question.png]] | [[images/yes.png]] | [[images/yes.png]] |  See 1).
Netgear Push2TV | Intel SDK? | [[images/yes.png]] | [[images/yes.png]] | [[images/yes.png]] | 
Actiontec SBWD100A |  | [[images/yes.png]] | [[images/yes.png]] | [[images/question.png]] | output is clipped and scaled
LG TV |  | [[images/yes.png]] | [[images/yes.png]] | [[images/yes.png]] |

1) Windows won't show miracast sinks in the UI unless device type is in their whitelist. Likewise Microsoft Wireless Display will only respond to devices of specific device type. "television" (category 7, subcategory 1) is known to work for sinks and "smartphone" (category 10, subcategory 5) is known to work for sources. Connman sets these values based on hostnamed chassis type but does not yet support "television" type.
