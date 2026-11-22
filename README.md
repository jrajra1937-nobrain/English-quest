# English Quest

**A2 → C1** の英語を、理解・演習・発話・作文の4つで鍛えるシンプルなWebアプリ。

- リポジトリ: https://github.com/jrajra1937-nobrain/English-quest
- GitHub Pages URL: https://jrajra1937-nobrain.github.io/English-quest/
- Deutsch Quest は独立して https://github.com/jrajra1937-nobrain/Deutsch-quest に残っています。

## 収録教材

- CEFR A2 / B1 / B2 / C1: 計24レッスン
- 4択問題224問（読解8題を含む）
- スピーキング32課題 / 作文16課題
- 英語発音用のMP3録音ファイル304件（音声マニフェスト`audio-map.json`）
- 日本語の解説・訳、XP・連続学習日数・復習・JSONバックアップ
- iPhoneホーム画面アイコンは青地に白い **E**

## 習得判定

各問題は固有IDで管理。**同じ問題に連続2回正解で習得**。異なる文章・語彙なら同じ文法テーマでも別ID、別の習得カウント。
不正解になった場合は、該当問題IDの連続正解がゼロに戻ります。
読解と文法・語彙の問題も別扱いです。

## GitHub Pages の有効化

初回のみ以下を実行します（GitHub設定の変更権限が必要）。

1. GitHubのこのリポジトリの **Settings** → **Pages** を開く。
2. **Build and deployment** → **Source** に **Deploy from a branch** を選ぶ。
3. **Branch** を `main`、フォルダを `/(root)` にし、**Save**。
4. サイト https://jrajra1937-nobrain.github.io/English-quest/ を確認する。

このアプリは純粋な静的HTMLなので、npmやビルド処理は不要です。

## ディレクトリ

`index.html`, `content.js`, `audio-map.json`, `audio/`, `manifest.webmanifest`, `sw.js`, `icon.svg`, `apple-touch-icon.png`, `tests.html`, `generate_audio.py`.

## 仕様と制限

- 音声ボタンは実在するMP3ファイルがマッピングされているときだけ表示し、再生エラー時には非表示。
- 発話用の文字起こしはブラウザ対応状況に依存し、発音を自動採点するわけではありません。
- 進捗情報は端末内の`localStorage`に保存され、端末間の自動同期はありません。移行はJSONで行ってください。
- 4択の正答率は会話力全体を保証するものではありません。
- `sw.js`はリポジトリのルートをスコープにし、他のQuestのキャッシュを削除しません。
