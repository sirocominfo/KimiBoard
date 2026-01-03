# KimiBoardのビルドガイド

- [1.部品について](#1部品について)
  - [1-1. キット内容](#1-1キット内容)
  - [1-2. 別途ご用意いただくもの](#1-2別途ご用意いただくもの)
- [2.準備](#2準備)
  - [2-1. 工具（必須）](#2-1工具必須)
  - [2-2. 工具（あるとよいもの）](#2-2工具あるとよいもの)
- [3.はんだ付け](#3はんだ付け)
    - [3-1.キーソケット](#3-1キーソケット)
    - [3-2.スライドスイッチ](#3-2スライドスイッチ)
    - [3-3.タクトスイッチ](#3-3タクトスイッチ)
    - [3-4.マイコン](#3-4マイコン)
    - [3-5.センサー](#3-5センサー)
    - [3-6.バッテリーソケット](#3-6バッテリーソケット)
- [4.組み立て](#4組み立て)
    - [4-1.トップケース](#4-1トップケース)
    - [4-2.ファームウェアの書き込み](#4-2ファームウェアの書き込み)
    - [4-3.リセットファームウェアの書き込み](#4-3リセットファームウェアの書き込み)
    - [4-4.デフォルトファームウェアの書き込み](#4-4デフォルトファームウェアの書き込み)
    - [4-5.ボトムケース](#4-5ボトムケース)
- [5.キーマップの編集](#5キーマップの編集)

- [6.動かないときは](#6動かないときは)

## 0.KimiBoardについて 
>[!WARNING]
>**・ロープロファイルのキーボードには対応しておりません。**  
>**・スペースキーのキースイッチを取り外して使用しますが、取り付けるキーボードによっては支え用パーツやLEDなども取り外す必要がございます。**  
>**・スペースバー埋め込みパーツは全てのキーボードに対応しているわけではありません。**  
>**・商品ページのサイズ詳細などを元に、お手元のキーボードのサイズを測り事前にご確認の上ご購入をお願いします。**


## 1.部品について  
### 1-1.キット内容

>[!WARNING]
> ※購入されたキットにより内容物が異なります。  
>
> **・組み立て済みセット**  
> → 別途ご用意いただくものはございません。
>
> **・組み立てキット**  
> → いくつかご用意していただくパーツがございます。

### 【組み立て済みセット】  
####  同梱物

| 名前 | 数 | 備考 |
|:-|---:|:-|
| 基板                           | 1個 | 全パーツはんだ済み |
| マイコン                       | 1個 | xiao nRF52840（基板へはんだ済み）|
| ケース                         | 1組 | トップx1 ボトムx2 ボトムカバーx1|
| キーボード埋め込み用パーツ       | 1個 | 左側パーツx1 埋め込み用底面部パーツ（7mm用 x3 8mm用 x3 9mm用 x3）|
| 20mm POMボール                 | 1個 | 白or黒|
| トラックボール読み取りセンサー   | 1個 | PMW3610（基板へはんだ済み）|
| 読み取りセンサー用レンズ         | 1個 | PMW3610と同梱|
| キーソケット                    | 3個 | Kailh ChocV2 互換用ホットスワップソケット（基板へはんだ済み） |
| キースイッチ                    | 3個 | Lofree:GHOST(リニア) |
| キーキャップ                     | 3個 | 3Dプリント品|
| スライドスイッチ                 | 1個 | 電源スイッチ用（基板へはんだ済み）|
| タクトスイッチ                   | 1個 | リセットスイッチ用（基板へはんだ済み）|
| リポバッテリー                   | 1個 | Li-Po 502025 3.7V 200mAh |
| 2ピンコネクター（メス）           | 1本 | JST 1.25mmピッチ 2ピンコネクター メス（基板へはんだ済み） |
| 滑り止め用シール                 | 1枚 | GLIPLUS（適宜好みのサイズにカットして使用してください）|  

### 【組み立てキット】  
####  同梱物

| 名前 | 数 | 備考 |
|:-|---:|:-|
| 基板                            | 1個 | はんだ付けが必要です|
| ケース                          | 1組 | トップx1 ボトムx2 ボトムカバーx1|
| キーボード埋め込み用パーツ        | 1個 | 左側パーツx1 埋め込み用底面部パーツ（7mm用 x3 8mm用 x3 9mm用 x3）|
| キーソケット                     | 3個 | Kailh ChocV2 互換用ホットスワップソケット |
| 20mm POMボール                  | 1個 | 白or黒|
| トラックボール読み取りセンサー    | 1個 | PMW3610|
| 読み取りセンサー用レンズ          | 1個 | PMW3610と同梱 |
| スライドスイッチ                 | 1個 | 電源スイッチ用|
| タクトスイッチ                   | 1個 | リセットスイッチ用|
| 2ピンコネクター（メス）           | 1本 | JST 1.25mmピッチ 2ピンコネクター メス |
| 滑り止め用シール                 | 1枚 | GLIPLUS（適宜好みのサイズにカットして使用してください）|  

#### 1-2.別途ご用意いただくもの  

| 名前 | 数 | 備考 |
|:-|---:|:-|
| マイコン                        | 1個 | xiao nRF52840|
| キースイッチ                    | 3個 | Choc V2 |
| キーキャップ                    | 3個 | ロープロファイル用 |
| リポバッテリー                  | 1個 | 502025 （JST 1.25mmピッチ 2ピンコネクター オス）|

## 2.準備
### 2-1.工具（必須）
| 名前 | 備考 |
|:-|:-|
| はんだごて                      | 温度調整可能なものがおすすめです|
| はんだ                         | |
| ピンセット                      | センサーレンズの脚接着用|
| ニッパー                        | 一部スイッチの脚を切る際に必要（そのままだとケースに収まらない為）|
| マスキングテープ                 | スイッチ類をはんだ付けする際の仮止め用|

### 2-2.工具（あるとよいもの）
| 名前 | 備考 |
|:-|:-|
| フラックス                      | はんだが乗りやすくなります|
| はんだ吸い取り線                 | はんだ付けの失敗時の補修に使用|
| テスター                        | 問題が起きた際に原因の切り分けに使用|


## 3.はんだ付け
### 3-1.キーソケット
キーソケットを3つはんだ付けします。  
片方のパッドに予備はんだをするのがおすすめです。

<img width="1920" height="1080" alt="buildguide-00" src="https://github.com/user-attachments/assets/3c0145ae-50e3-45d7-9820-850d167d36aa" />
<img width="1920" height="1080" alt="buildguide-02" src="https://github.com/user-attachments/assets/cfffb79c-b6a6-47e4-b041-c7a18bab8317" />

### 3-2.スライドスイッチ
スライドスイッチを1つはんだ付けします。  
マスキングテープで止めてからはんだ付けをしてください。  
  
はんだ後に3枚目の〇で囲った部分のようにニッパーで足を短くカットしてください。  
（そのままだとケースに収まらない為）

<img width="1920" height="1080" alt="buildguide-03" src="https://github.com/user-attachments/assets/deb769a1-dc13-40ef-8849-aca5f6248d31" />
<img width="1920" height="1080" alt="buildguide-04" src="https://github.com/user-attachments/assets/68d369d9-bfe8-4ed9-a242-470d206c8399" />
<img width="1920" height="1080" alt="buildguide-05" src="https://github.com/user-attachments/assets/d5ab1b13-2b95-4aea-8500-81f55eee2087" />

### 3-3.タクトスイッチ
3タクトスイッチを1つはんだ付けします  
こちらも、はんだ後に3枚目の〇で囲った部分のようにニッパーで足を短くカットしてください。  
（そのままだとケースに収まらない為）

<img width="1920" height="1080" alt="buildguide-06" src="https://github.com/user-attachments/assets/7428178e-7671-4c35-83aa-57db616387e0" />
<img width="1920" height="1080" alt="buildguide-07" src="https://github.com/user-attachments/assets/18bbf0c2-8eec-4cfd-b9cb-65eaf948d11a" />
<img width="1920" height="1080" alt="buildguide-08" src="https://github.com/user-attachments/assets/b463c8c4-b135-4a0b-b178-a5e678f459c4" />

### 3-4.マイコン
マイコンを1つはんだ付けします。  
基板上のスルーホールに切り欠きが残っている場合がございますが、取らずにはんだ作業を行ってください。（製造の過程で残ってしまう場合があるようですが無理に切り取ると断線する恐れがあります。）  

<img width="1920" height="1080" alt="buildguide-09" src="https://github.com/user-attachments/assets/191d90d0-6881-4ff2-940f-31f5e4c6220e" />

マイコンにピンヘッダを差し込みます。  
隙間がないように奥まで差し込んでください。  

<img width="1920" height="1080" alt="buildguide-10" src="https://github.com/user-attachments/assets/8fcfd346-7bb4-48fa-a84f-9010418d71f1" />

そのまま基板へピンヘッダを差し込みます。  
奥まで隙間の無いように差し込んでください。  
スルーホールからマイコンの4つのパッドが見えていることを確認してください。  
見えていなければ逆に差し込んでしまっているので、位置を確認して差し込みなおしてください。  

<img width="1920" height="1080" alt="buildguide-11" src="https://github.com/user-attachments/assets/ed38dcf3-af8f-40fc-9ebb-101412635345" />

スルーホールからはんだを流し込みパッドと繋ぎます。  
左右のはんだが接触しないように気を付けてはんだ付けをしてください。  
もし、接触してしまった場合ははんだ吸い取り線を使ってやり直します。  
修復は十分可能ですので、丁寧に吸い取ってやり直します。  

<img width="1920" height="1080" alt="buildguide-12" src="https://github.com/user-attachments/assets/c0a4dd6d-0d5e-4b7f-89e5-98de401772b2" />
<img width="1920" height="1080" alt="buildguide-13" src="https://github.com/user-attachments/assets/0c74de76-e771-43a4-b5c3-7272dde075a0" />

ピンヘッダを取り外します。  
パッドのはんだのみで接着されている状態なので、マイコンと基板を押さえながらゆっくり取り外してください。  
<img width="1920" height="1080" alt="buildguide-14" src="https://github.com/user-attachments/assets/981731e3-8d6d-4dcb-993a-955d2e9b0cb8" />

基板とマイコンの側面をはんだ付けします。  
写真のように側面のみ繋がっていればOKです。  
<img width="1920" height="1080" alt="buildguide-15" src="https://github.com/user-attachments/assets/7206adb2-6974-4d97-9e8b-c746d8f3f85d" />
<img width="1920" height="1080" alt="buildguide-16" src="https://github.com/user-attachments/assets/828d01bc-a2e7-4f96-a124-847fc2a68f16" />


### 3-5.センサー
センサーを1つはんだ付けします  

>[!WARNING]
> ※ここの作業のみはんだごての温度と作業時間に注意ががございます。    
>
> **・最大260℃までの温度**  
> **・7秒以内でのはんだづけ**
>  
> が推奨されています。  

写真の方向でセンサーを差し込みます。  

<img width="1920" height="1080" alt="buildguide-17" src="https://github.com/user-attachments/assets/6e9a6aa7-f32e-4691-bc20-a8dde811d99b" />

裏側からマスキングテープで固定します。  

<img width="1920" height="1080" alt="buildguide-18" src="https://github.com/user-attachments/assets/d1980b4a-abb5-4960-b7ee-2f0cfbe2b328" />

左右合わせて16か所はんだ付けします。  
温度に注意しながらゆっくり作業してください。  

<img width="1920" height="1080" alt="buildguide-19" src="https://github.com/user-attachments/assets/5dc921b6-10ca-4922-bf0f-22127328ca64" />

はんだ付けが完了しましたら、センサーの保護シールを剝がします。  
ここで剥がし忘れて次の作業に移ってしまうとセンサーが全く反応しなくなってしまうので、剥がし忘れないようにしてください。  

<img width="1920" height="1080" alt="buildguide-20" src="https://github.com/user-attachments/assets/07b07cb3-872e-40d8-bb67-a5657657fa88" />
<img width="1920" height="1080" alt="buildguide-21" src="https://github.com/user-attachments/assets/a4a4c612-ccbc-45a0-b800-5eb17773b4fa" />

シールを剥がしましたら、センサーにレンズを取り付けます。  
向きがありますので、写真の方向で取り付けてください。  

<img width="1920" height="1080" alt="buildguide-22" src="https://github.com/user-attachments/assets/dc1999a6-63f8-46e7-85f0-d4b2f072a378" />

裏側に飛び出しているレンズの脚を溶かして固定します。  
ピンセットの上からはんだごてを押し当てて熱で脚を溶かします。  
少しこて先にはんだを乗せると熱が伝わりやすくなります。  
（この作業をしないとケースに基板が収まらなくなってしまいます。）  

<img width="1920" height="1080" alt="buildguide-23" src="https://github.com/user-attachments/assets/4a0a591f-c6f9-485f-9519-3932e2c7e4f7" />
<img width="1920" height="1080" alt="buildguide-24" src="https://github.com/user-attachments/assets/02d8409f-f3bb-4434-9fe0-16f5f2f27269" />
<img width="1920" height="1080" alt="buildguide-25" src="https://github.com/user-attachments/assets/5a41bffb-fa63-4059-b317-b96c201da748" />
<img width="1920" height="1080" alt="buildguide-26" src="https://github.com/user-attachments/assets/c88733e2-67f5-4fd5-aef9-e7073c3324b6" />
<img width="1920" height="1080" alt="buildguide-27" src="https://github.com/user-attachments/assets/8f34f524-3602-49d8-bd1d-a41fc808fa4e" />

写真のように脚が溶け広がっていればOKです。  

<img width="1920" height="1080" alt="buildguide-28" src="https://github.com/user-attachments/assets/179c2c1a-f774-4da6-b400-4a0c8e76a5a9" />
<img width="1920" height="1080" alt="buildguide-29" src="https://github.com/user-attachments/assets/26ba86dc-c77f-4348-96ce-36cd918516d5" />

### 3-6.バッテリーソケット
バッテリーソケットを1つはんだ付けします。  
写真の位置で赤黒のケーブルを通します。  
撚り線の先端を指で少しねじると通しやすくなります。  

<img width="1920" height="1080" alt="buildguide-30" src="https://github.com/user-attachments/assets/c0118acd-6774-4485-bfd9-53f50486b6ac" />

裏側からきちんと撚り線が飛び出していることを確認し、マスキングテープで固定しはんだ付けを行います。  

<img width="1920" height="1080" alt="buildguide-31" src="https://github.com/user-attachments/assets/5a7d9950-07b4-456b-ac62-c96890889c04" />
<img width="1920" height="1080" alt="buildguide-32" src="https://github.com/user-attachments/assets/0f7bd657-f141-42e6-bad3-52fe308d0f39" />

はんだ箇所がセンサーの高さより飛び出している場合は先端を少しカットしてください。

<img width="1920" height="1080" alt="buildguide-33" src="https://github.com/user-attachments/assets/a5cb6151-683e-4456-82e8-88ba39d2486d" />

以上ではんだ作業は終了です。  

## 4.組み立てとFWの書き込み
### 4-1.トップケース
トップケースに基板を取り付けます。  

<img width="1920" height="1080" alt="buildguide-34" src="https://github.com/user-attachments/assets/ae5f1115-822a-43b1-8a32-985eaea6418c" />

バッテリーソケットのケーブルを挟んでしまわないように注意しながら取り付けてください。  

<img width="1920" height="1080" alt="buildguide-35" src="https://github.com/user-attachments/assets/113c3ee9-f570-447f-af83-6036836d7f6f" />

キースイッチを3つ取り付けます。  

この状態ファームウェアを書き込み、テストを行います。  
PCと本体をケーブルで繋ぎます。  
USB端子側の基板を裏側から素早く2度押します。  
（「カチカチッ」とボタンの感触があります。）  
PCがリムーバルディスクとして認識するので、そこに次のuf2ファイルを書き込みます。  

<img width="1920" height="1080" alt="buildguide-36" src="https://github.com/user-attachments/assets/139d9f7c-3528-46eb-838f-c8ff835d2229" />

### 4-2.ファームウェアの書き込み

[こちら](https://github.com/sirocominfo/zmk-config-KimiBoard/actions/runs/20669572134/artifacts/5011659015)からzipファイルをダウンロードしてください。  

### 4-3.リセットファームウェアの書き込み
settings_reset-seeeduino_xiao_ble-zmk.uf2
を書き込みます。  

書き込み終了後にエラーが出ますが、正常に書き込まれているので無視してしまってかまいません。  

もう一度USB端子側の基板を裏側から素早く2度押しPCに認識させます。

### 4-4.デフォルトファームウェアの書き込み
kimiboard rgbled_adapter-seeeduino_xiao_ble-zmk.uf2
を書き込みます。  
ここでも書き込み終了後にエラーが出ますが、正常に書き込まれているので無視してしまってかまいません。  

これで動作させる準備が整いましたので、各キーやトラックボールの動作テストを行ってください。  
動作に問題がなければそのまま次の工程へ進み、組み立てを完了してください。

### 4-5.ボトムケース
左右のボトムケースを取り付けます。  
ボトムカバーを押さえながらスライドして取り付けます。  

<img width="1920" height="1080" alt="buildguide-37" src="https://github.com/user-attachments/assets/b9ee2c70-fa9c-41e3-a3fd-87f929f422eb" />
<img width="1920" height="1080" alt="buildguide-38" src="https://github.com/user-attachments/assets/9bb91e62-cb25-44ef-8b38-8fa7c0fbf3c6" />
<img width="1920" height="1080" alt="buildguide-39" src="https://github.com/user-attachments/assets/f778c67b-693e-4392-b0cd-2188079c8163" />
<img width="1920" height="1080" alt="buildguide-40" src="https://github.com/user-attachments/assets/ec1e7924-8409-4e3a-bf5f-c8edefab07da" />

リポバッテリーを取り付ける場合はケーブルの収納に少しコツがいります。  
写真のような形にケーブルを収納してケースに取り付けてください。  
なお、リポバッテリーの取り扱いには十分に注意してください。  
取り扱いの不備によって発生した事故や損害については、責任を負いかねます。  

<img width="1920" height="1080" alt="buildguide-41" src="https://github.com/user-attachments/assets/b5d68156-1135-46ff-a6c8-25772219e671" />
<img width="1920" height="1080" alt="buildguide-42" src="https://github.com/user-attachments/assets/4eb5ef98-8f48-4a31-bf59-2b68bda91dfb" />
<img width="1920" height="1080" alt="buildguide-43" src="https://github.com/user-attachments/assets/2c4e55f5-fc2a-4730-8845-964b99c33303" />
<img width="1920" height="1080" alt="buildguide-44" src="https://github.com/user-attachments/assets/f5f9040c-1272-4bc8-911f-91e16cdd2490" />
<img width="1920" height="1080" alt="buildguide-45" src="https://github.com/user-attachments/assets/89b3d0c8-4f57-4377-bbd0-70e5ee162edd" />
<img width="1920" height="1080" alt="buildguide-46" src="https://github.com/user-attachments/assets/ed98eccf-4425-4317-b5c1-382f6be75fed" />
<img width="1920" height="1080" alt="buildguide-47" src="https://github.com/user-attachments/assets/2684f01d-8193-477c-b983-b8eec30f58b1" />

## 5.キーマップの編集  
1.こちら[https://zmk.studio/](https://zmk.studio/)へアクセス  
2.画面中央の「USB」をクリックします  
3.KimiBoard(USB)を選択し「接続」を押します  
4.画面下部のBehaviorからお好きなもの（例:Key Press）を選び下のボックスから設定したいボタン（例:Keyboard A）を選択し右上のセーブボタンで設定完了です。  
