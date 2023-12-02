# CircleCIとは
コードが正しく動作するかを自動で行ってくれるもの。異なる環境でもコードが動作するかを検証する機能や複数の人が書いたコードが全体として動作するものであるのかをチェックする機能などがある。

# CircleCIが正しく動作するようにリポジトリに組み込む
1. GitHubでリポジトリを作成する。
2. `git clone [リポジトリのURL]`を実行する。
3. `cd [リポジトリ名]`でクローンしたリポジトリに移動する。
4. `git checkout -b [ブランチ名]`を実行する。
5. Windowsのエクスプローラーからクローンしたフォルダを開いて、その中に`.circleci`というファルダを作成し、その`.circleci`フォルダに`config.yml`というファイルを作成し、そのファイルに自動で実行したいコードを記述する。
6. `git add .`を実行する。
7. `git commit -m "任意のメッセージ"`を実行する。
8. `git push origin [ブランチ名]`を実行する。
9. CircleCIにログインする。
10. 左サイドバーの「Projects」をクリックする。
11. 対象のリポジトリの「Set Up Project」をクリックする。
12. 検索欄に対象のブランチ名を記入し、「Set Up Project」をクリックする。
