# youtubeの動画を見てgitの使い方の練習

originはリモートサーバー(GitHub)のこと．
`$ git log`を使ったら`$ q`で脱出できる 


## readmeファイルはマークダウン方式

`#`は見出し(section)
スペース2つで改行  
コード表示：インラインは`code`, 複数行は行頭に空白4つ(Tabキー)


## git, githubの手順
* すべての工程で作業リポジトリに注意する！
### ゼロからプロダクトを作り始める場合
* github状にプロダクト用のリモートリポジトリを作成
* 作成したリポジトリをクローン  `$ git clone YOUR_REPOSITORY_URL`
* エディタでクローンしたディレクトリを開き，コードを記述（README.txtとか）．作業はすべてローカルリポジトリで実行している状態となる．
* 個別の機能ができたタイミングなどでバージョンを決定する．ここでけっていしたバージョンはgitで記録され，いつでも復元できる．  
    $ git add .
    $ git commit -m "commit message"
* githubのリモートリポジトリにpushする．
    $ git push origin main

### リポジトリを作成する前にコードを書いていた場合
* GitHub上にプロダクト用のリモートリポジトリを作成する．URLはそのまま
* 手元のプロダクトのディレクトリでローカルリポジトリを作成する．
    $ git init
* リモートリポジトリとローカルリポジトリを連携させる．
    $ git remote add origin YOUR_REPOSITORY_URL

### branchを用いた開発
## 各branchの役割
* main：本番用のソースコードを管理．このbranchのコードは必ず万全で動く状態にしておく必要がある．
* develop：開発用のソースコードを管理する．各開発者が開発した内容をまとめて動作検証などを行う．
* feature：各追加機能や，バグ修正等を行うためのbranch. 各機能ごとにbranchを作成し，機能が完成したらdevelop branchに統合する．
## branchを用いた開発の流れ
1. まずmain branch を用意する．(リポジトリ作成時に自動で作成される)
2. develop branchを作成し，main branchから切り替える．
3. develop branch でコードを書き，開発を進める．
4. 区切りが着いたらコミットを実行し，pushする．
5. main branch に対して，「プルリクエスト」を作成する．
6. 作成されたプルリクエストを「マージ」し，develop branchで開発した内容を「main」branchに反映させる．

* branchの作成，切り替え
    $ git branch develop
    $ git switch develop
現在捜査しているbranchの確認は下記でできる
    $ git branch
* コードのpush
develop branchになっていることを確認し，適当にファイルを編集した後，
    $ git add .
    $ igt commit -m "update md file"
    $ git push origin develop
* プルリクエストとマージ
1. GitHub のリポジトリのページを開き「Pull requests」タブをクリックする．
2. New pull request ボタンをクリックする．
3. branch を選択する部分が「main <- develop」と設定する．画面上で切り替えるとファイルの差分が表示される．
4. branch の設定ができていることを確認したら Create pull request ボタンをクリックする．
5. メッセージを入力する画面に切り替わるので，任意の内容を入力して Create pull request を再度クリックする．
6. プルリクエストを管理する画面に切り替わる．プルリクエストした内容に問題がなければ Merge pull request → Confirm merge の順にボタンをクリックする．
7. プルリクエストとマージが完了したら Code タブをクリックして，develop branch で記述したコードが main branch でも反映されていることを確認する．

### 動作確認のために追加した行

