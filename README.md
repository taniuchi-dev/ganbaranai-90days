# がんばらない90日｜公開アプリ集

「AI駆動・アプリ連続制作の90日公開実験」の公開サイトです。まず第1作の六曜カレンダー（ICS生成ツール）を公開し、以降の作品は `apps/` 以下に追加します。

## ディレクトリ構成

- `index.html` : 公開アプリ集のトップページ
- `apps/rokuyo/index.html` : 第1作。提供された完成済みHTMLを**変更せずに配置**
- `.nojekyll` : GitHub PagesのJekyll処理を無効化
- `README.md` : 管理情報

## 公開URLのイメージ

リポジトリ名を `ganbaranai-90days` とした場合：

- アプリ集: `https://<GitHubアカウント名>.github.io/ganbaranai-90days/`
- 六曜カレンダー: `https://<GitHubアカウント名>.github.io/ganbaranai-90days/apps/rokuyo/`

URLはGitHub Pagesの公開設定完了後に実在するものになります。

## 公開手順

1. GitHubで `ganbaranai-90days` という **Public** リポジトリを新規作成する（同名が未使用の場合）。
2. ZIPを解凍し、**ZIP自体ではなく**中身の `index.html`、`.nojekyll`、`apps/rokuyo/index.html`、`README.md` をリポジトリにコミットする。
3. リポジトリ `Settings` → `Pages` → `Build and deployment` → `Source`: `Deploy from a branch`。
4. `Branch`: `main`、フォルダー: `/(root)` にして `Save`。
5. `Visit site` でトップページと六曜アプリの両方を確認する。
6. X等で案内する前に、公開URLで1か月分と5年分の生成・分割操作を確認する。ICSファイルの実際のインポートも再試験する。

公式: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 公開前の注意

- 提供されたアプリのコードは一切変更していません。フッターに「試作版」と表示されるため、本公開に際してClaude側で表示文言の変更を検討してください。
- 現在のHTMLは、件数が1,461件を超えてもメインの「.icsファイルを保存」ボタンから**分割されない全件ファイルも保存可能**です。Googleカレンダーを使う方には、表示される分割ファイルをそれぞれ保存してもらう説明を徹底してください。
- 1,461件はユーザー環境での実機検証結果であり、Googleが公式に保証した上限ではありません。
- 2024年1月〜2028年12月のサンプルICS（1,827件）は、Googleカレンダーでは取り込み失敗と報告されているため、公開パッケージには含めていません。
- アプリ自体には解析スクリプトはありませんが、GitHub Pagesの配信基盤ではセキュリティ用途などのアクセスログが記録されます。
- 旧暦・六曜の計算と照合の扱いについては、アプリ内の注記に従ってください。
- ソースと公開ページは第三者に見えるため、APIキー、秘密情報、顧客情報を置かないでください。

## 次のアプリの追加

`apps/<アプリ名>/index.html` を追加し、トップページの `公開アプリ` セクションにリンクを加えるだけです。

## 検証記録（2026-11-10）

利用者の実機報告: Google 1,461件成功、1,827件失敗、Outlook 3,652件成功。分割した2ファイルの順次取り込みで重複なし、同一ICS再取り込みでも重複なし。

ChatGPT側で添付ファイルを静的検査した結果: 2024〜2028年のサンプルICSには1,827件の `VEVENT` があり、UIDの重複はありません。**実機環境での追加検証は行っていません**。
