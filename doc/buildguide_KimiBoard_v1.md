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
キーソケットを3つはんだ付けします

![20251204_045619](https://github.com/user-attachments/assets/4dd736ba-0eea-47d7-bff6-5eae02cdd742)
![20251204_045826](https://github.com/user-attachments/assets/bd9aa412-ebcb-4ef6-aa2a-357264b8b4a2)
![20251204_045904](https://github.com/user-attachments/assets/91089304-018f-459c-85b5-9f31c395875e)
![20251204_045913](https://github.com/user-attachments/assets/770bebe6-b895-4324-932c-d783b6be72b8)
![20251204_050619](https://github.com/user-attachments/assets/eaec6146-9690-4295-94b3-351278b58b2c)

### 3-2.スライドスイッチ
スライドスイッチを1つはんだ付けします

![20251204_043239](https://github.com/user-attachments/assets/eb657b90-026c-419c-8b74-ccbb2dab905d)
![20251204_042533](https://github.com/user-attachments/assets/31c228e3-ea42-40ef-a26e-bd884bbf7523)
![20251204_042517](https://github.com/user-attachments/assets/49fd0bc2-3d7b-4690-b3ab-253d8e04e0f3)
![20251204_042456](https://github.com/user-attachments/assets/5f8bc259-873c-4dc5-a42c-152c65884129)
![20251204_042122](https://github.com/user-attachments/assets/debb269a-be9c-43ea-b1f9-a77439dc0e26)


### 3-3.タクトスイッチ
3タクトスイッチを1つはんだ付けします

![20251204_043957](https://github.com/user-attachments/assets/b3267ae2-648f-409d-a89f-37c1ddb516e8)
![20251204_043927](https://github.com/user-attachments/assets/5cd65b36-0ff3-4c0e-9b23-46205da38677)
![20251204_043455](https://github.com/user-attachments/assets/36570c9f-ccdc-491e-9e29-496919b33e69)
![20251204_043440](https://github.com/user-attachments/assets/594ce01a-bbf6-4a90-9785-cbd02106e391)
![20251204_043432](https://github.com/user-attachments/assets/91734d59-9e60-41f2-8cf8-606c7048304a)
![20251204_043335](https://github.com/user-attachments/assets/f8d274a6-a589-453b-9ed6-42ba289c2142)


### 3-4.マイコン
マイコンを1つはんだ付けします

![20251204_032625](https://github.com/user-attachments/assets/afc9cf7b-45d5-439a-ada2-962b2b3cb044)
![20251204_032114](https://github.com/user-attachments/assets/77238cc1-9b4f-456d-bc7e-e25a2f93c970)
![20251204_030956](https://github.com/user-attachments/assets/82a7ef0f-a788-40a0-96f9-2d7c2851da28)
![20251204_030114](https://github.com/user-attachments/assets/319b0dc3-94f4-4d81-86fb-854da3c42b0f)
![20251204_030018](https://github.com/user-attachments/assets/83e3d48e-3c04-4d1d-873b-e499bd0f1493)
![20251204_024823](https://github.com/user-attachments/assets/12b81ad7-62b3-4d75-9560-116297ba64db)
![20251204_024551](https://github.com/user-attachments/assets/15fb2e9a-cfff-47f1-9b0b-0dbeeb684ea6)
![20251204_024319](https://github.com/user-attachments/assets/16df9981-0b19-435c-9436-553076589acf)
![20251204_023559](https://github.com/user-attachments/assets/f363e3ea-0397-45d4-a1c8-485b6e2d9499)
![20251204_023532](https://github.com/user-attachments/assets/d773a9f1-76ae-4ffb-9b47-16792f31206d)


### 3-5.センサー
センサーを1つはんだ付けします

![20251204_041535](https://github.com/user-attachments/assets/802c4cee-7312-47b2-8eb7-01ad0cb17b44)
![20251204_041502](https://github.com/user-attachments/assets/06bc0add-48ab-4f8a-8b9c-46f8bb0a798a)
![20251204_040342](https://github.com/user-attachments/assets/f8fb5e2b-48a3-454c-8f0d-f1a57c0c82b4)
![20251204_035856](https://github.com/user-attachments/assets/0d8fa83a-6930-4865-a58b-320c7fc52cf5)
![20251204_035850](https://github.com/user-attachments/assets/a39ef7c2-6b47-4611-aaf8-4ad4b6704f83)
![20251204_035749](https://github.com/user-attachments/assets/5469dad6-e102-46ca-8b6e-a75f1dfdb9b9)
![20251204_035731](https://github.com/user-attachments/assets/2b0bfe63-cd92-407f-8bb8-7e8534f5b01c)
![20251204_035717](https://github.com/user-attachments/assets/4965b7ee-b8f4-4fb9-b8fe-9686f464117c)
![20251204_035614](https://github.com/user-attachments/assets/182826f2-ddfd-43b9-9bb3-5b3f61c0322e)
![20251204_035403](https://github.com/user-attachments/assets/565bedcc-551d-4fe4-9009-afb00ad36c6f)
![20251204_035316](https://github.com/user-attachments/assets/9690b924-c9e8-47d0-bbb6-66b28a42ae08)
![20251204_033135](https://github.com/user-attachments/assets/d51bcf76-2276-4740-be2a-e7a9e985bb02)
![20251204_033007](https://github.com/user-attachments/assets/422b9ea7-f32d-44db-8008-83cc8f689a7d)


### 3-6.バッテリーソケット
バッテリーソケットを1つはんだ付けします

![20251204_045158](https://github.com/user-attachments/assets/e9d6972e-b6dd-4fc5-872e-0bd1e43ed07e)
![20251204_044817](https://github.com/user-attachments/assets/766485be-9566-4155-9f61-ec730694aadf)
![20251204_044601](https://github.com/user-attachments/assets/c53b58c8-7e27-4831-b3e7-6a2e7a6bc60b)
![20251204_044541](https://github.com/user-attachments/assets/d2c72c39-b4cd-4845-88e1-5f222412cffe)


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
