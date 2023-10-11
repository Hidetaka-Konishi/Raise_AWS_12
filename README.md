# CircleCIとは
コードが正しく動作するかを自動で行ってくれるもの。異なる環境でもコードが動作するかを検証する機能や複数の人が書いたコードが全体として動作するものであるのかをチェックする機能などがある。

# CircleCIが正しく動作するようにリポジトリに組み込む手順
1. GitHubでリポジトリを作成する。
2. `git clone [リポジトリのURL]`を実行する。
3. `cd [リポジトリ名]`でクローンしたリポジトリに移動する。
4. `git checkout -b [ブランチ名]`を実行する。
5. VScodeでクローンしたフォルダを選択し、そこでファイルを作成してコードを記述します。(クローンしたフォルダの中に新しくフォルダを作ってそこでファイルを作成してコードを記述しても良い)
6. `git add .`を実行する。
7. `git commit -m "任意のメッセージ"`を実行する。
8. `git push origin [ブランチ名]`を実行する。
9. 
10. CircleCIにログインする。
11. 左サイドバーの「Projects」をクリックする。
12. 「Create Project」をクリックする。
13. 「Connect to」で「GitHub」を選択します。
14. 「Private SSH Key」の「1」のコマンドをコピーしたものをUbuntuに貼り付けて、`-C`以降の部分は任意の文字列を指定する。コマンドを実行し、`y`を実行、Enterキーを二回押すとSSHキーの情報が表示されるのでコピーして大切に保管しておく。
15. Ubuntuで`cat ~/.ssh/project_key.pub`を実行する。公開SSHキーが表示されるのでコピーする。
16. GitHubから対象のリポジトリを選択して、「Settings」をクリックする。
17. 左サイドバーの「Deploy keys」→「Add deploy key」をクリックする。
18. 「Title」に名前をつけて、「Key」にさっきコピーした公開SSHキーを貼り付け、「Allow write access」にチェックを入れ、「Add key」をクリックする。
19. Ubuntuで`cat /home/motosa1531/.ssh/project_key`を実行する。秘密SSHキーが表示されるのでコピーする。
20. コピーした秘密SSHキーをCircleCIに貼り付けます。
21. CircleCIの「Repository」で対象のリポジトリを選択し、「Select your config.yml file」では「Fast」を選択し、「Create Project」をクリックする。
22. 「Commit and Run」をクリックする。
23. ubuntuで`cd [リポジトリ名]`でクローンしたリポジトリに移動する。
24. `git checkout -b [ブランチ名]`を実行する。
25. `mkdir .circleci`を実行する。
26. VScodeからクローンしたフォルダの`circleci`フォルダを選択し、そこでファイルを作成してコードを記述します。
27. `git add .`を実行する。
28. `git commit -m "任意のメッセージ"`を実行する。
29. `git push origin [ブランチ名]`を実行する。
30. 
