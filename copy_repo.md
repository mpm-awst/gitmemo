# githubにあるリポジトリを個人のリポジトリにコピーして利用する
参考URL：https://qiita.com/ossan_pg/items/6e63ba0ae6e08a056a2f

以下はminizincを個人のリポジトリにコピーする例

* GitHub上にコピー先のリポジトリを作成する
  * リポジトリのトップの右にあるNewをクリックする
    ![image](https://user-images.githubusercontent.com/59195410/117522691-b1cd5300-afef-11eb-87ba-6e53ee1d72de.png)
  * リポジトリの作成
    ![image](https://user-images.githubusercontent.com/59195410/117526309-45f2e680-afff-11eb-845b-32d6e82b9593.png)
* リポジトリをコピーする
  ```
  $ git clone --bare https://github.com/MiniZinc/libminizinc.git
  $ cd ./libminizinc.git
  $ git push --mirror https://github.com/XXXXX/libminizinc.git  # XXXXX はアカウント名
  $ cd ..
  $ git clone https://github.com/XXXXX/libminizinc.git
  ```
* 不要になったミラーリポジトリを削除する
  ```
  $ rm -rf libminizinc.git
  ```
* コピー元の追随
  ```
  $ cd ./libminizinc
  $ git remote add upstream https://github.com/MiniZinc/libminizinc.git
  
