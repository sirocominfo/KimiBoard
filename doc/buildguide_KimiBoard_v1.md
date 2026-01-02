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
    - [4-2.ボトムケース](#4-2ボトムケース)
- [5.ファームウェアの書き込み](#5ファームウェアの書き込み)  
    - [5-1.リセットファームウェアの書き込み](#5-1リセットファームウェアの書き込み)
    - [5-2.デフォルトファームウェアの書き込み](#5-2デフォルトファームウェアの書き込み)
- [6.キーマップの編集](#6キーマップの編集)

- [7.動かないときは](#7動かないときは)

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
| ケース                         | 1組 | トップx1 ボトムx2 アンダーカバーx1|
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
| ケース                          | 1組 | トップx1 ボトムx2 アンダーカバーx1|
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
写真のように側面のみつながっていればOKです。  
<img width="1920" height="1080" alt="buildguide-15" src="https://github.com/user-attachments/assets/7206adb2-6974-4d97-9e8b-c746d8f3f85d" />
<img width="1920" height="1080" alt="buildguide-16" src="https://github.com/user-attachments/assets/828d01bc-a2e7-4f96-a124-847fc2a68f16" />


### 3-5.センサー
センサーを1つはんだ付けします

![20251204_033007](https://github.com/user-attachments/assets/422b9ea7-f32d-44db-8008-83cc8f689a7d)
![20251204_033135](https://github.com/user-attachments/assets/d51bcf76-2276-4740-be2a-e7a9e985bb02)
![20251204_035316](https://github.com/user-attachments/assets/9690b924-c9e8-47d0-bbb6-66b28a42ae08)
![20251204_035403](https://github.com/user-attachments/assets/565bedcc-551d-4fe4-9009-afb00ad36c6f)
![20251204_035614](https://github.com/user-attachments/assets/182826f2-ddfd-43b9-9bb3-5b3f61c0322e)
![20251204_035717](https://github.com/user-attachments/assets/4965b7ee-b8f4-4fb9-b8fe-9686f464117c)
![20251204_035731](https://github.com/user-attachments/assets/2b0bfe63-cd92-407f-8bb8-7e8534f5b01c)
![20251204_035749](https://github.com/user-attachments/assets/5469dad6-e102-46ca-8b6e-a75f1dfdb9b9)
![20251204_035850](https://github.com/user-attachments/assets/a39ef7c2-6b47-4611-aaf8-4ad4b6704f83)
![20251204_035856](https://github.com/user-attachments/assets/0d8fa83a-6930-4865-a58b-320c7fc52cf5)
![20251204_040342](https://github.com/user-attachments/assets/f8fb5e2b-48a3-454c-8f0d-f1a57c0c82b4)
![20251204_041502](https://github.com/user-attachments/assets/06bc0add-48ab-4f8a-8b9c-46f8bb0a798a)
![20251204_041535](https://github.com/user-attachments/assets/802c4cee-7312-47b2-8eb7-01ad0cb17b44)

### 3-6.バッテリーソケット
バッテリーソケットを1つはんだ付けします

![20251204_044541](https://github.com/user-attachments/assets/d2c72c39-b4cd-4845-88e1-5f222412cffe)
![20251204_044601](https://github.com/user-attachments/assets/c53b58c8-7e27-4831-b3e7-6a2e7a6bc60b)
![20251204_044817](https://github.com/user-attachments/assets/766485be-9566-4155-9f61-ec730694aadf)
![20251204_045158](https://github.com/user-attachments/assets/e9d6972e-b6dd-4fc5-872e-0bd1e43ed07e)

## 4.組み立て
### 4-1.トップケース
トップケースを取り付けます

### 4-2.ボトムケース
ボトムケースを取り付けます


## 5.ファームウェアの書き込み
### 5-1.リセットファームウェアの書き込み
リセットファームウェアをダウンロードします
[こちら](https://github.com/sirocominfo/zmk-config-KimiBoard)からzipファイルをダウンロードしてください。

### 5-2.デフォルトファームウェアの書き込み
デフォルトファームウェアをダウンロードします
[こちら](https://github.com/sirocominfo/zmk-config-KimiBoard)からzipファイルをダウンロードしてください。


## 6.キーマップの編集  
1.こちら[https://zmk.studio/](https://zmk.studio/)へアクセス  
2.画面中央の「USB」をクリックします  
3.KimiBoard(USB)を選択し「接続」を押します  
4.画面下部のBehaviorからお好きなもの（例:Key Press）を選び下のボックスから設定したいボタン（例:Keyboard A）を選択し右上のセーブボタンで設定完了です。  
