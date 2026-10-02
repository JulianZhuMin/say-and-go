# Say & Go 講聲即郁

A voice game for toddlers. Say 「飛機」, 「火車」, 「電單車」 or 「消防車」 (also 電單, 摩托車, 摩托, 機車, 鐵馬 for the motorbike and 消防, 救火車, 救火, 滅火車, 嘀嘟車, 嘀嘟 for the fire truck; Simplified 摩托车, 电单车, 机车, 消防车, 救火车; English "plane", "train", "motorcycle", "motorbike", "motor bike", "fire truck", "fire engine", "firetruck") and that vehicle goes across the screen with its own sound (the motorbike revs "vroom vroom" and zooms off; the fire truck flashes its lights, plays a two-tone "dee-daa" siren, stops, then drives off). Tapping a picture only says its name.

Matching is lenient for toddlers: the name can be anywhere in what was heard ("搭咩呀，搭飛機呀", "I want plane"), every recognition alternative and interim result is checked (confidence ignored), and sloppy or half words also count (e.g. 灰機/飛/機 → plane, 火/嘟嘟/choo choo → train, 單車/電車/摩多/bike/vroom → motorbike, 消消/宵防/蕭防/fire → fire truck), plus a simple sounds-alike match on Jyutping/pinyin groups. The longest, most specific word wins (機車 is the motorbike, not the plane; 救火車 is the fire truck, not the train). Words that match nothing are silently ignored. Recognition language: Cantonese first, then Mandarin (cmn-Hans-CN, zh-TW), then English. While the game is listening, a big see-through toy microphone glows in the middle of the screen. After three rides a child's voice says "bye bye".

- Tap **開始 Start**, then allow the microphone.
- iPhone/iPad: use Safari, and turn on Siri and Dictation (Settings → General → Keyboard → Enable Dictation).
- Computer: use Chrome or Edge.
- Speech is turned into text by Apple's or Google's/Microsoft's servers, so you need internet.
- Change the app name in one place: `APP_NAME` near the top of `index.html` (manifest.json is only a fallback copy).
- Add `?lang=zh-HK` or `?lang=yue-Hant-HK` to the address to force a recognition language.

Plain HTML, CSS and JavaScript. No install, no build step.
