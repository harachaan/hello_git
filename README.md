# youtubeの動画を見てgitの使い方の練習

## readmeファイルはマークダウン方式

`#`は見出し(section)
スペース2つで改行  
コード表示：インラインは`code`, 複数行は行頭に空白4つ(Tabキー)


## git, githubの手順
* github状にプロダクト用のリモートリポジトリを作成
* 作成したリポジトリをクローン  `$ git clone YOUR_REPOSITORY_URL`
* エディタでクローンしたディレクトリを開き，コードを記述（README.txtとか）．作業はすべてローカルリポジトリで実行している状態となる．
* 個別の機能ができたタイミングなどでバージョンを決定する．ここでけっていしたバージョンはgitで記録され，いつでも復元できる．  
    git add .
    git commit -m "commit message"
* githubのリモートリポジトリにpushする．
    git push origin main
