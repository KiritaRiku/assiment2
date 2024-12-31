# assiment2


# 概要
ロボットシステム学2024年課題２
- このリポジトリは2024年度の千葉工業大学のロボットシステム学の講義で
githubについての学習を目的として制作、公開をしています。


# ノード

- timer.pyには、*'timer_pub'*というノードがあります。
- *'timer_pub'*は次の５つの機能を持ちます。
	- *'timer_cb'*を実行して1秒ごとに現在の時刻を受け取り、プログラムを動かしてから経過した時間を求める。
	- *'progress_ber'*を呼び、5分経過するまでの残りの時間の割合をバーで表示する。
	- 3分経過で、「3分経過しました!」とログを出力する。
	- 5分経過で、「5分経過しました！」とログを出力し、ノードを停止する。
	- 結果を*'time_infomation'*というトピックに送る。


# トピック
- *`time_information'* (*'std_msgs/String'*)
  - 現在時刻、経過した時間、バーの情報を送る。


# 実行例
- launchファイルを使いノードを動かすと次のような実行が可能です
```bash
$ ros2 launch mypkg timer.launch.py
[INFO] [1735610028.297004307] [timer_pub]: 現在時刻: Tue Dec 31 10:53:48 JST 2024
経過時刻: 1.0秒
残り時間: [                              ]
[INFO] [1735610029.270158268] [timer_pub]: 現在時刻: Tue Dec 31 10:53:49 JST 2024
経過時刻: 2.0秒
残り時間: [                              ]
...
[INFO] [1735610207.266474322] [timer_pub]: 3分経過しました!
[INFO] [1735610207.266805461] [timer_pub]: 現在時刻: Tue Dec 31 10:56:47 JST 2024
経過時刻: 180.0秒
残り時間: [------------------            ]
...
[INFO] [1735610327.268615329] [timer_pub]: 5分経過しました！
[INFO] [1735610327.268887203] [timer_pub]: 5分経過したので、ノードを停止します
```

# 必要なソフトウェア
- python
- コンテナ
	- 講師がUbuntu 22.04 LTSにROS 2をセットアップしたものを使用する
	- https://hub.docker.com/repository/docker/ryuichiueda/ubuntu22.04-ros2


# テスト環境

- ubuntu-22.04 LTS

# 参考

- https://taida-eng.com/%e9%80%86%e5%bc%95%e3%81%8d%e3%82%bd%e3%83%bc%e3%82%b9%e3%82%b3%e3%83%bc%e3%83%89/python%e9%80%86%e5%bc%95%e3%81%8d%ef%bc%9a%e5%87%a6%e7%90%86%e5%be%85%e3%81%a1%e3%81%ae%e9%96%93%e3%81%ab%e9%80%b2%e6%8d%97%e8%a1%a8%e7%a4%ba%e3%81%97%e3%81%9f%e3%81%84%e3%83%97%e3%83%ad%e3%82%b0/

- https://takuya-1st.hatenablog.jp/entry/2016/04/11/044313#google_vignette

- https://wa3.i-3-i.info/word11252.html


# ライセンス

- このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可iされます．
- © 2024 Riku Kirita
- このパッケージのコードの一部は，下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
	- https://ryuichiueda.github.io/slides_marp/robosys2024/lesson8.html#4
	- https://ryuichiueda.github.io/slides_marp/robosys2024/lesson10.html#8
