# Say & Go 嗌到我就出發

A voice game for toddlers. Say the Cantonese name of one of eight vehicles and it goes across the screen with its own sound:

- 「飛機」 plane
- 「地鐵」 or 「火車」 MTR train (only phrases containing 地鐵 or 火車, e.g. 地鐵車, 地鐵站, 火車仔; tapping its picture says 「地鐵」): a two-car silver train with a red stripe glides along a viaduct, stops, the doors open with the "do-di" chime and close again
- 「巴士」 bus (only phrases containing 巴士, e.g. 巴士仔, 雙層巴士): a red double-decker pulls up at the bus stop, ding-ding, air brakes, beep-beep
- 「電單車」 motorbike (also 電單, 摩托車, 摩托, 機車, 鐵馬): revs "vroom vroom" and zooms off
- 「消防車」 fire truck (also 消防, 救火車, 救火, 滅火車, 嘀嘟車, 嘀嘟): flashes its lights, plays a two-tone "dee-daa" siren, stops, then drives off
- 「渡輪」 or 「船」 ferry: a green-and-white harbour ferry sails across the water
- 「救傷車」 ambulance
- 「的士」 taxi

Simplified characters work too (飞机, 地铁, 双层巴士, 电单车, 摩托车, 消防车, 救火车 …). The child is expected to answer in Chinese (recognition is Chinese-only). English Latin aliases are still accepted if dictation writes them as whole Latin words (case-insensitive; spaces ignored), e.g. plane / aeroplane / airplane, MTR / train / subway / metro, bus / double decker, motorbike / motorcycle / motor bike, fire truck / fire engine / firetruck, ferry / star ferry, ambulance, taxi / cab (and plurals). Tile/intro English display: airplane, train, Bus, Motorbike, Fire truck, Ferry, ambulance, taxi. "business" and "trainer" never count. English is not used on the vowel-matching path. Tapping a picture only says its Cantonese name.

Matching is lenient for toddlers: the name can be anywhere in what was heard ("搭咩呀，搭巴士呀"), every recognition alternative and interim result is checked (confidence ignored), and half words, repeats and sound-alikes also count (e.g. 灰機/飛/機 → plane, 單車/電車/車車/轟轟 → motorbike, 消消/宵防/蕭防 → fire truck). The MTR and the bus are strict: they start only when 地鐵 or 火車 / 巴士 is actually heard (救火車 is still the fire truck), so 港鐵, 東鐵, 地地, 小巴, 公車, 巴巴 or 爸爸 never start them. Baby talk is understood as well: common toddler sound changes (f → h/w/b/p, g → d, k → h/t, c → s/t, n ↔ l, dropped final -k/-t/-p, -ng → -n, e.g. 喜機 → 飛機, 燒防車 → 消防車), applied only to the sounds in the plane, motorbike and fire-truck names and never to everyday words. The longest, most specific word wins (機車 is the motorbike, not the plane; 救火車 is the fire truck). Everyday words that only look alike (手機, 司機, 嘴巴, 尾巴, 地下 …) and anything that matches nothing are silently ignored. Recognition language: Chinese only — Cantonese first (zh-HK / yue-Hant-HK), then Mandarin (cmn-Hans-CN, zh-CN, zh-TW). No English recognition pass; the child answers in Chinese.

Vowel matching for toddler voices (second path, used only when no name was found): children's voices are high and their consonants are often unclear, so every character the recogniser wrote is turned into its Cantonese finals (the vowel + ending, tones ignored; characters with several readings try all of them). If consecutive characters have the same finals as a name, syllable by syllable, it counts even when the consonants differ or are missing: 飛機 fei-gei, 地鐵 dei-tit, 火車 fo-ce, 巴士 baa-si, 電單車 din-daan-ce, 消防車 siu-fong-ce (for the 3-syllable names the last two are enough: 番車, 黃車). So 記鐵 / 利鐵 → MTR, 媽士 / 吧士 → bus, 小防車 → fire truck, 美美 → plane, while 白士, 爸爸, 巴巴, 小巴, 公車, 港鐵 and 東鐵 still do nothing. More matching syllables win, then more real characters. Family words (爸爸, 媽媽, 哥哥, 姐姐 …), 多謝, 坐車 and 俾 / 畀 are never used for vowel matching. The character → final table covers common Traditional and Simplified characters and was generated from [rime-cantonese](https://github.com/rime/rime-cantonese) (CC BY 4.0).

All the game's spoken lines are pre-recorded (Hong Kong Cantonese child-friendly voice for Chinese, en-US voice for English: the per-vehicle questions, the eight names, the help messages and the goodbye: 「到屋企啦，bye bye！」 then 「Bye bye！」). The phone's own speech voice is only used if a clip can't load. While the game is listening, a big see-through toy microphone glows on the screen. After the child has named all eight vehicles the game says goodbye.

- Tap **開始 Start**, then allow the microphone.
- iPhone/iPad: use Safari, and turn on Siri and Dictation (Settings → General → Keyboard → Enable Dictation).
- Computer: use Chrome or Edge.
- Speech is turned into text by Apple's or Google's/Microsoft's servers, so you need internet.
- Change the app name in one place: `APP_NAME` near the top of `index.html` (manifest.json is only a fallback copy).
- Add `?lang=zh-HK` or `?lang=yue-Hant-HK` to the address to force a recognition language.

Plain HTML, CSS and JavaScript. No install, no build step.


## One-sentence free choice (2026-10-05g)

After a slow one-by-one bilingual intro (random order; each figure alone, highlighted, says Cantonese then English; ~1 s pause between vehicles; **no questions during intro**), each round:

1. Shows up to three random vehicles the child has **not yet named** in one row. `choices[0]` is the **left** card, `choices[1]` the **centre**, `choices[2]` the **right** (the array order *is* the on-screen order).
2. Asks **one Cantonese sentence** that lists those Chinese names left → right:
   - three: 「你想坐{左}、{中}，定係{右}？」
   - two: 「你想坐{甲}，定係{乙}？」
   - one: 「你想坐{甲}？」
   Spoken with the same pre-recorded HiuGaai clips as the intro (`phrase-want` + `name-*` + `phrase-or`). VoiceOver announces the same Chinese sentence.
3. While the sentence plays, as each vehicle **name** is spoken that figure highlights, then clears when the name ends; the next name lights the next figure. After the question ends / while listening, **no** highlights — all three stay the same neutral state.
4. **Any** of the three on-screen vehicles (correct Chinese name or alias) starts that vehicle’s trip and counts as named-by-child. Names outside the three are ignored. ~7 s silence / wrong → next round (no teach-back).
5. Tap a card during the 7 s: it says its zh + en name (highlighted), no trip, does not count; the 7 s restart.
6. Named vehicles never appear in later trios. The game ends when the child has named all eight.

Speech recognition is **Chinese-only** (zh-HK / yue-Hant-HK, then Mandarin zh-CN / zh-TW). Aliases: ferry accepts 「渡輪」 and 「船」; MTR accepts 「地鐵」 and 「火車」.

Locked English display names (tiles / intro): airplane, train, Bus, Motorbike, Fire truck, Ferry, ambulance, taxi.
