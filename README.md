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
21. 
22. CircleCIにログインする。
23. 左サイドバーの「Projects」をクリックする。
24. 「Create Project」をクリックする。
25. 「Connect to」で「GitHub」を選択します。
26. 「Private SSH Key」の「1」のコマンドをコピーしたものをUbuntuに貼り付けて、`-C`以降の部分は任意の文字列を指定する。コマンドを実行し、`y`を実行、Enterキーを二回押すとSSHキーの情報が表示されるのでコピーして大切に保管しておく。
27. Ubuntuで`cat ~/.ssh/project_key.pub`を実行する。公開SSHキーが表示されるのでコピーする。
28. GitHubから対象のリポジトリを選択して、「Settings」をクリックする。
29. 左サイドバーの「Deploy keys」→「Add deploy key」をクリックする。
30. 「Title」に名前をつけて、「Key」にさっきコピーした公開SSHキーを貼り付け、「Allow write access」にチェックを入れ、「Add key」をクリックする。
31. Ubuntuで`cat /home/motosa1531/.ssh/project_key`を実行する。秘密SSHキーが表示されるのでコピーする。
32. コピーした秘密SSHキーをCircleCIに貼り付けます。
33. CircleCIの「Repository」で対象のリポジトリを選択し、「Select your config.yml file」では「Fast」を選択し、「Create Project」をクリックする。
34. 「Commit and Run」をクリックする。
35. ubuntuで`cd [リポジトリ名]`でクローンしたリポジトリに移動する。
36. `git checkout -b [ブランチ名]`を実行する。
37. `mkdir .circleci`を実行する。
38. VScodeからクローンしたフォルダの`circleci`フォルダを選択し、そこでファイルを作成してコードを記述します。
39. `git add .`を実行する。
40. `git commit -m "任意のメッセージ"`を実行する。
41. `git push origin [ブランチ名]`を実行する。
42. 
