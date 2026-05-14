# AvatarTranstexhter
今後、Youtubeなどで活動していく中で使用予定の"物理的な"アバターを製作しています。本リポジトリはこの物理的なアバターのソースコードリポジトリをまとめたものとなります。
# システム概要図
Raspberry Pi Pico 2Wを中心に各デバイス制御用のマイコンやディスプレイを接続して構築しています。 またWebアプリを通して本体の動作や姿勢などのパラメータを設定することができます。
![](/アバタートランステクター_トレマギロ_システム概要図.png)
# リンク先の紹介
## メインファームウェア
- [AvatarTranstexhter_main](https://github.com/tremagiro/AvatarTranstexhter_main/tree/public)（RaspberryPi Pico 2 W）
    - アバターロボットのメイン制御を担うファームウェアです。 WebSocketからコマンドを受け取り、I2Cやを介して、全身のアクチュエーターを動かします。
- [tremagiro-ui](https://github.com/tremagiro/AvatarTranstexhter_main/tree/public/tremagiro-ui)
    - ブラウザからアバターロボットの各種パラメーターを設定してモーションを作成することができます。
## サブファームウェア
- [stepper_zero](https://github.com/tremagiro/stepper_zero)（RP2040 Zero）
    - アバターロボットのバックパックや両サイドの外装を上下させるステッピングモーターの制御を担うマイコンボードです。 基本的にはメイン制御ボードからの信号を受けてステッピングモーターを動作させますが、メンテナンス時には本体に備え付けられたボタンを使い、ボード単体でも動作させることができます。
## オリジナルライブラリ
- [avatarTranstexhter_json_core](https://github.com/tremagiro/avatarTranstexhter_json_cor)(RaspberryPi Pico 2 W)
    - 本体のパラメーター設定の際に使用する処理をまとめたライブラリです。
- [AvatarTranstexhter_wire_core](https://github.com/tremagiro/AvatarTranstexhter_wire_core)
    - 各制御ボードで使用するI2C周りの処理をまとめたライブラリです。
