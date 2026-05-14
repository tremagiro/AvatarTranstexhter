# AvatarTranstexhter
今後、Youtubeなどで活動していく中で使用予定の"物理的な"アバターを製作しています。本リポジトリはこの物理的なアバターのソースコードリポジトリをまとめたものとなります。
# システム概要図
Raspberry Pi Pico 2Wを中心に各デバイス制御用のマイコンやディスプレイを接続して構築しています。 またWebアプリを通して本体の動作や姿勢などのパラメータを設定することができます。
![](/アバタートランステクター_トレマギロ_システム概要図.png)
# リンク先の紹介
## [main_firmware](/main_firmware/)
- [AvatarTranstexhter_main](/main_firmware/AvatarTranstexhter_main/)（RaspberryPi Pico 2 W）
    - アバターロボットのメイン制御を担うファームウェアです。 WebSocketからコマンドを受け取り、I2Cやを介して、全身のアクチュエーターを動かします。
- [tremagiro-ui](/main_firmware/AvatarTranstexhter_main/tremagiro-ui/)
    - ブラウザからアバターロボットの各種パラメーターを設定してモーションを作成することができます。
## [sub_firmware](/sub_firmware/)
- [stepper_zero](/sub_firmware/stepper_zero/)（RP2040 Zero）
    - アバターロボットのバックパックや両サイドの外装を上下させるステッピングモーターの制御を担うマイコンボードです。 基本的にはメイン制御ボードからの信号を受けてステッピングモーターを動作させますが、メンテナンス時には本体に備え付けられたボタンを使い、ボード単体でも動作させることができます。
## [library](/library/)
- [avatarTranstexhter_json_core](/library/avatarTranstexhter_json_cor/)(RaspberryPi Pico 2 W)
    - 本体のパラメーター設定の際に使用する処理をまとめたライブラリです。
- [AvatarTranstexhter_wire_core](/library/AvatarTranstexhter_wire_core/)
    - 各制御ボードで使用するI2C周りの処理をまとめたライブラリです。
