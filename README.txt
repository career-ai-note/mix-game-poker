MIX Game Poker － Vercel公開手順
==================================

このフォルダの中身をそのまま公開すれば動きます（ビルド不要の静的サイトです）。

■ 方法A：コマンドで公開（GitHub不要）
 1. Node.js が入っていなければ https://nodejs.org からインストール
 2. このフォルダでターミナルを開く
 3. npx vercel login      … ブラウザが開くのでVercelにログイン
 4. npx vercel            … 質問はほぼEnterでOK
      - Set up and deploy? → Y
      - Link to existing project? → N
      - Project name → 好きな名前（例：mix-game-poker）
      - In which directory is your code located? → ./
      - Want to modify these settings? → N
    → プレビュー用のURLが表示されます
 5. npx vercel --prod     … 本番公開。https://（プロジェクト名）.vercel.app で見られます

■ 方法B：GitHub経由（以後の更新が楽）
 1. GitHubで新しいリポジトリを作り、「Add file → Upload files」でこのフォルダの中身をアップロード
 2. https://vercel.com/new でそのリポジトリを Import
 3. Framework Preset は「Other」のまま Deploy
    → 以後はGitHubのファイルを差し替えるだけで自動で更新されます

■ 公開したあとにやること
 1. アクセス計測：Vercelのプロジェクト画面 → Analytics → Enable
    （訪問者数・ページ閲覧数が見られます。Cookieは使いません）
 2. index.html の og:image を、フルURLに書き換えて再デプロイ
      <meta property="og:image" content="https://（あなたのURL）/og.png">
    （XやLINEで共有したときに画像を出すため）
 3. privacy.html の「お問い合わせ先」に連絡先を記入
 4. スマホで開いて、共有メニューの「ホーム画面に追加」でアプリのように使えるか確認

■ 注意
 - 記録（収支・段位・実績）は遊んだ人のブラウザに保存されます。
   別の端末や別のブラウザには引き継がれません。
 - ファイル一覧
     index.html            ゲーム本体
     privacy.html          プライバシーポリシー
     og.png                共有時の画像（1200×630）
     icon.svg / icon-*.png / apple-touch-icon.png  アイコン
     manifest.webmanifest  ホーム画面に追加したときの設定
