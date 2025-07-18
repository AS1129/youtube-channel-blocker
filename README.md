# YouTube Channel Blocker

不要なYouTubeチャンネルを非表示にするシンプルなChrome拡張です。  
A simple Chrome extension to block unwanted YouTube channels.

📖 このREADMEには日本語と英語の説明が含まれています。  
📖 This README includes instructions in both Japanese and English.

⚠️ 警告: 大体の動作は問題ありませんが、レイアウトの崩れのせいか、×ボタンを押したときに違うチャンネルがリストに追加される場合があります。ご注意ください。

→非表示にしたいチャンネル名と実際に入るチャンネル名が違う場合はエラーメッセージ（Error:で始まるポップアップ）を表示して、リストに入れないようにしました。。レイアウトの崩れは都度の対応しようがないので、ブラウザの更新で対応してください。

⚠️ Most features work fine, but due to layout issues, pressing the × button may occasionally add the wrong channel to the list. Please be careful.

→If the channel name you want to block differs from the actual detected channel name, an error message (a popup starting with "Error:") will be displayed and the channel will not be added to the block list.
Layout issues cannot be addressed each time, so please resolve them by refreshing the browser

---

## 日本語

### インストール 🛠️

1. 「youtube-channel-blocker」フォルダを作成し、コードをその中に入れます（.gitignoreは不要です。）    
2. アイコン用に適当なPNG形式の画像を2つ用意し、それぞれ名前を以下のように変更してフォルダ内に置きます：  
   - `icon48.png`  
   - `icon128.png`    
3. ブラウザのURLバーに `chrome://extensions/` と入力し、拡張機能ページを開きます  
4. 右上の「デベロッパーモード」を ON にします  
5. 左上の「パッケージ化されていない拡張機能を読み込む」をクリックし、「youtube-channel-blocker」フォルダを選択します  
6. これで拡張機能が読み込まれ、すぐに使用できます

---

### 使い方（基本編）🔴

- 動画のチャンネル名の横にある赤い×ボタンを押します（チャンネルページや再生している動画からの非表示は未実装）  
- そのチャンネルが投稿した動画が非表示になったら動作確認完了です  
- 非表示にならなかったら、更新やインストールのやり直し、画像やコードの不足がないかを確認してみてください  
- 自分で名前をリストに追加して、「保存」ボタンを押すことでも非表示にできます（※名前が完全一致していること）  
- リストは拡張機能のアイコンをクリックすると確認できます  
- リストから名前を消すと戻せます（ブラウザの更新が必要）  
- 動作しないときはページの更新で直るはずです

---

### 使い方（応用編）✨

個人的な「こんな機能あると良いなあ」で**実装済み**のやつを箇条書き

- **リストのインポート・エクスポート**  
  - エキスポートボタンではjsonファイルとしてリストを出力  
  - インポートボタンではjsonファイルを入力することで、リストを完全に置換  
  - 本家Channel Blockerは時々リストが消える現象があったので、この拡張機能も定期的なバックアップを推奨（この拡張機能でリストが消える現象は現時点では未確認）  
- **拡張機能の動作トグルを実装**  
  - 拡張機能のアイコンから、赤い「Blocker:ON」を押すと「Blocker:OFF」と灰色になって、非表示が無効化  
  - ボタンを押したら更新不要で反映（反映が遅いことがあるので注意）  
- **「直近の１つを削除」ボタンを実装**  
  - 拡張機能のアイコンを押すと表示  
  - ×ボタンを押したときにでてくる「Blocked:チャンネル名」というポップアップとあわせて、誤入力をすぐに挽回可能  
  - トップページで偶に違う動画がリストに入ってしまう現象を確認しているので、その対策  
- **動画タイトルフィルターを実装**  
  - キーワードを1つ設定すると、そのキーワードを含むすべての動画タイトルが非表示  
  - 1つのキーワードの文字数制限は30文字、キーワードセットは最大1000個  
  - 対象は動画タイトルのみ（チャンネル名は対象外）   
  - 3つのキーワードのAND条件（キーワードセット）でも非表示可能  
  - キーワード設定の例：「切り抜き」と「さしすせそ」と「GTA」を1つのキーワードセットに入れた場合 
    - タイトル「私の切り抜き動画集」→表示される  
    - タイトル「GTA切り抜き集」→表示される  
    - タイトル「さしすせそ切り抜き集」→表示される  
    - タイトル「GTAの面白い瞬間【さしすせそ/切り抜き】」→非表示になる

---

### 注意 ⚠️

- 理論上ブロックできる最大件数：約34,000件🧮（YouTubeチャンネル名が最大50文字の場合の計算）
- 大体の不具合はブラウザの更新で直ります（細かい不具合への対処は困難）🔧
- 処理の関係上、一瞬で非表示にするのは困難です（処理が遅い時はサムネが見えることも）🙈  
- 本家と同じく突然リストが消える可能性があるので、リストは定期的にバックアップを推奨します（現時点でその現象は確認出来てませんが）💾  
- 力を入れて更新する気はないですが、ブログやX（Twitter）へのコメントやプルリクエストがあれば、対応するかもしれません 

---

## ライセンス

このソフトウェアは [MITライセンス](LICENSE) のもとで配布されています。  
詳細については同梱の LICENSE ファイルをご確認ください。

## 免責事項

このソフトウェアは現状のまま提供され、いかなる保証もありません。  
使用によって生じたいかなる損害や問題についても、作者は一切の責任を負いません。  
すべての使用は利用者自身の責任において行われるものとします。

## 実装予定（やるとは言わない）  

- チャンネルページや動画再生ページに×ボタン追加  
- ~~動画タイトルからキーワード非表示~~ 追加済み
- ~~×ボタンで非表示にしたチャンネル名を一時的にポップアップ（間違い防止。１つだけ戻すボタンも追加したい。）~~ 追加済み・5秒で消える  
- ~~拡張機能の詳細設定を追加~~ 簡易版を追加済み
- ×ボタンのUIやポップアップの改善

---

## 連絡 📬

📘 ブログ（記事に飛ぶ）: [https://physx.hatenablog.com/entry/2025/07/13/174229](https://physx.hatenablog.com/entry/2025/07/13/174229)  
🐦 X (Twitter): [https://x.com/aki009113](https://x.com/aki009113)

---


## English

### Installation 🛠️

1. Create a folder named `youtube-channel-blocker` and place all the code inside it.  
2. Prepare two PNG images for the icons, rename them as follows, and place them in the folder:  
   - `icon48.png`  
   - `icon128.png`  
3. Open your browser and navigate to `chrome://extensions/` in the URL bar.  
4. Enable "Developer mode" using the toggle at the top right.  
5. Click "Load unpacked" (top left) and select the `youtube-channel-blocker` folder.  
6. The extension will be loaded and ready to use immediately.

---
---

### How to use (Basic) 🔴

- Press the red × button next to the channel name on video thumbnails (blocking from channel pages or currently playing videos is not yet implemented).  
- If videos from that channel disappear, the extension is working properly.  
- If videos are not hidden, try updating or reinstalling the extension and check for missing images or code.  
- You can also manually add channel names to the list and press the "Save" button to block them (the names must match exactly).  
- The list can be viewed by clicking the extension icon.  
- Removing names from the list will unblock them (a browser refresh is required).  
- If the extension doesn’t work, refreshing the page should fix it.
---

### How to use (Advanced) ✨

Features personally implemented as “would be nice to have”:

- Import and export the list  
  - The export button outputs the list as a JSON file.  
  - The import button completely replaces the list using a JSON file.  
  - The official Channel Blocker sometimes loses the list, so regular backups are recommended (this extension has not shown this issue so far).  
- Implemented a toggle to enable/disable the extension  
  - Click the extension icon and press the red "Blocker:ON" button to switch to gray "Blocker:OFF," disabling the blocking feature.  
  - No page refresh is needed to apply changes (though it might take a few seconds).  
- Added a "Remove Last" button  
  - This appears when clicking the extension icon.  
  - Combined with the “Blocked: channel name” popup shown after pressing ×, this allows quick undo of mistakes.  
  - Helps counter rare cases where wrong videos get added to the list on the homepage.

- Implemented Video Title Filter  
  - Videos can be hidden based on AND conditions of three keywords (keyword sets).  
  - Each keyword is limited to 30 characters, and up to 1000 keyword sets can be registered.  
  - This filter applies only to video titles and does not affect channel names (for example, if "clip" is a keyword, channels with names containing "clip" will still be shown).  
  - If only one keyword is used, all video titles containing that keyword will be hidden (e.g., if the keyword is "clip," all titles containing "clip" will be hidden).  
  - For example, if a keyword set contains "clip," "sashisuseso," and "GTA":  
    - Title "My clip video collection" → displayed  
    - Title "GTA clip collection" → displayed  
    - Title "Funny GTA moments [sashisuseso/clip]" → hidden  

---

### Notes ⚠️

- The maximum theoretical number of blockable channels is about 34,000 🧮  
- Most issues can be fixed by refreshing the browser 🔧  
- Immediate hiding is difficult; thumbnails may briefly appear 🙈  
- Like the official version, the block list may disappear suddenly; regular backups are recommended 💾  
- Development is not active, but comments or pull requests might be addressed ✍️  

---

## License

This software is distributed under the [MIT License](LICENSE).  
For details, please see the included LICENSE file.

## Disclaimer

This software is provided "as is", without any warranty of any kind.  
The author shall not be held liable for any damages or issues arising from the use of this software.  
All use is at the user's own risk.

## Planned Features (Not Promised)  

- Add × button to channel pages and video playback pages  
- ~~Hide keywords from video titles~~ Added
- ~~Temporarily show the blocked channel name in a popup after clicking × (to avoid mistakes; add an undo button for the last action)~~ Added・disappears in 5 seconds  
- ~~Add advanced settings to the extension~~ Added (Simple Version)
- Improve the UI of the × button and popup

---

## Contact 📬

📘 Blog (Go to article): [https://physx.hatenablog.com/entry/2025/07/13/174229](https://physx.hatenablog.com/entry/2025/07/13/174229)  
🐦 X (Twitter): [https://x.com/aki009113](https://x.com/aki009113)
