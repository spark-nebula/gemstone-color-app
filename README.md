# 宝石カラー

iPhone・iPadのSafariで使える宝石カラーアプリです。外部ライブラリやアカウント、ビルドは不要です。

## パソコンで確認する

1. このフォルダーをターミナルで開きます。
2. `python3 -m http.server 8000 --bind 0.0.0.0` を実行します（Python 3が必要です）。
3. ブラウザで `http://localhost:8000` を開きます。
4. 最初は赤い宝石です。「色を変える」を押すと、青 → 緑 → 赤の順に繰り返し変わります。
5. 再読み込みすると赤に戻ります。

終了するときはターミナルで Ctrl+C を押します。

## iPhone・iPadで確認する

1. 自分のパソコンで上のサーバーを起動したままにします。
2. パソコンとiPhone・iPadを同じWi-Fiにつなぎます。
3. パソコンのネットワーク設定でWi-FiのIPアドレスを調べます（例：192.168.1.10）。
4. iPhone・iPadのSafariで `http://192.168.1.10:8000` を開きます。IPアドレスは実際の値に置き換えてください。
5. ボタンを数回タップして青・緑・赤に変わることを確認します。縦向き・横向きでも操作できます。

開けない場合は、同じWi-Fiか、サーバーが起動しているか、パソコンのファイアウォールが接続を許可しているか確認してください。

クラウド環境のlocalhostにはiPhoneから直接接続できません。クラウドで作成した場合はファイルを自分のパソコンにダウンロードして上の手順を行うか、静的サイトとして公開したURLをSafariで開いてください。

## ファイル

`index.html` に画面・デザイン・色の切り替え処理がまとまっています。

## パソコンを使わず、iPadから公開する（GitHub Pages）

公開されるのは宝石アプリのページです。URLを知っている人はアクセスできます。

1. Codexの変更をGitHubリポジトリへ反映します。画面にPR作成機能がある場合はPRを作成し、GitHubでmainへマージしてください。`index.html` と `.github/workflows/pages.yml` がmainにあることを確認します。
2. Safariで https://github.com/spark-nebula/gemstone-color-app/settings/pages を開きます。
3. 「Build and deployment」の「Source」で **GitHub Actions** を選びます。
4. リポジトリの「Actions」タブで **Publish gemstone app** を選び、「Run workflow」からmainを指定して実行します。すでに自動実行されて成功していれば再実行は不要です。
5. 実行が緑色のチェックになったら、Settings → Pagesに表示される公開URLを開きます。初回は数分かかることがあります。
6. そのURLをiPhoneにも送れば、同じアプリを開けます。

標準設定でのURL候補は https://spark-nebula.github.io/gemstone-color-app/ です。公開完了前には使えません。正確なURLはPages設定画面で確認してください。

Settingsが見つからない場合はSafariの「デスクトップ用Webサイトを表示」を試してください。Pages設定を変更するにはリポジトリの管理権限が必要です。非公開リポジトリではGitHubプランによってPagesが使えない場合があります。公開のためだけにリポジトリを公開へ変更する必要はありません。
