# Say & Go 講聲即郁

A voice game for toddlers. Say the Cantonese name of one of five vehicles and it goes across the screen with its own sound:

- 「飛機」 plane
- 「地鐵」 MTR train (also 港鐵, 東鐵, 地鐵車, 地鐵站): glides along a viaduct, stops, the doors open with the "do-di" chime and close again
- 「巴士」 bus (also 巴士仔, 雙層巴士, 小巴, 大巴, 公交車, 公車): a red double-decker pulls up at the bus stop, ding-ding, air brakes, beep-beep
- 「電單車」 motorbike (also 電單, 摩托車, 摩托, 機車, 鐵馬): revs "vroom vroom" and zooms off
- 「消防車」 fire truck (also 消防, 救火車, 救火, 滅火車, 嘀嘟車, 嘀嘟): flashes its lights, plays a two-tone "dee-daa" siren, stops, then drives off

Simplified characters work too (飞机, 地铁, 双层巴士, 电单车, 摩托车, 消防车, 救火车 …). Only the Chinese names count; English words are ignored. Tapping a picture only says its name.

Matching is lenient for toddlers: the name can be anywhere in what was heard ("搭咩呀，搭巴士呀"), every recognition alternative and interim result is checked (confidence ignored), and half words, repeats and sound-alikes also count (e.g. 灰機/飛/機 → plane, 地地/地車/低鐵 → MTR, 巴巴/吧士 → bus, 單車/電車/車車/轟轟 → motorbike, 消消/宵防/蕭防 → fire truck). Baby talk is understood as well: common toddler sound changes (f → h/w/b/p, g → d, k → h/t, c → s/t, n ↔ l, dropped final -k/-t/-p, -ng → -n, e.g. 喜機 → 飛機, 東鐵 → 港鐵, 燒防車 → 消防車), applied only to the sounds in the vehicle names and never to everyday words. The longest, most specific word wins (機車 is the motorbike, not the plane; 救火車 is the fire truck). Everyday words that only look alike (手機, 司機, 嘴巴, 尾巴, 地下, 火車 …) and anything that matches nothing are silently ignored. Recognition language: Cantonese first (zh-HK / yue-Hant-HK), then Mandarin (cmn-Hans-CN, zh-TW).

All the game's spoken lines are pre-recorded in one Hong Kong Cantonese child-friendly voice (the question, the five names, the help messages and the goodbye: 「到屋企啦，bye bye！」 then 「Bye bye！」). The phone's own speech voice is only used if a clip can't load. While the game is listening, a big see-through toy microphone glows on the screen. After three rides the game says goodbye.

- Tap **開始 Start**, then allow the microphone.
- iPhone/iPad: use Safari, and turn on Siri and Dictation (Settings → General → Keyboard → Enable Dictation).
- Computer: use Chrome or Edge.
- Speech is turned into text by Apple's or Google's/Microsoft's servers, so you need internet.
- Change the app name in one place: `APP_NAME` near the top of `index.html` (manifest.json is only a fallback copy).
- Add `?lang=zh-HK` or `?lang=yue-Hant-HK` to the address to force a recognition language.

Plain HTML, CSS and JavaScript. No install, no build step.
