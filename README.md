# CircleCIとは
コードが正しく動作するかを自動で行ってくれるもの。異なる環境でもコードが動作するかを検証する機能や複数の人が書いたコードが全体として動作するものであるのかをチェックする機能などがある。

# CircleCIが正しく動作するようにリポジトリに組み込む手順
1. GitHubでリポジトリを作成する。
2. `git clone [リポジトリのURL]`を実行する。
3. `cd [リポジトリ名]`でクローンしたリポジトリに移動する。
4. `git checkout -b [ブランチ名]`を実行する。
5. クローンしたフォルダにコードが正しく動作するか検証したいプログラムファイルをドラッグアンドドロップします。
6. `git add .`を実行する。
7. `git commit -m "任意のメッセージ"`を実行する。
8. `git push origin [ブランチ名]`を実行する。
9. CircleCIにログインする。
10. 左サイドバーの「Projects」をクリックする。
11. 「Create Project」をクリックする。
12. 「Connect to」で「GitHub」を選択します。
13. 「Private SSH Key」の「1」のコマンドをコピーしたものをUbuntuに貼り付けて、`-C`以降の部分は任意の文字列を指定する。コマンドを実行し、`y`を実行、Enterキーを二回押すとSSHキーの情報が表示されるのでコピーして大切に保管しておく。
14. Ubuntuで`cat ~/.ssh/project_key.pub`を実行する。公開SSHキーが表示されるのでコピーする。
15. GitHubから対象のリポジトリを選択して、「Settings」をクリックする。
16. 左サイドバーの「Deploy keys」→「Add deploy key」をクリックする。
17. 「Title」に名前をつけて、「Key」にさっきコピーした公開SSHキーを貼り付け、「Allow write access」にチェックを入れ、「Add key」をクリックする。
18. Ubuntuで`cat /home/motosa1531/.ssh/project_key`を実行する。秘密SSHキーが表示されるのでコピーする。
19. コピーした秘密SSHキーをCircleCIに貼り付けます。
20. CircleCIの「Repository」で対象のリポジトリを選択し、「Select your config.yml file」では「Fast」を選択し、「Create Project」をクリックする。
21. 検証する条件が書かれたコードを貼り付けて、「Commit and Run」をクリックする。
