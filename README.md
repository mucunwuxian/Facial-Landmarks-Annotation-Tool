# FLAT - Facial Landmarks Annotation Tool

KeyPointをAnnotationするToolのForkです。

![Screenshot](screenshot/01.png)

<br/>
<br/>

## 環境構築方法

### 1. コンパイル

リポジトリ直下で、以下コマンドを実施します。

```
cmake CMakeLists.txt
make
```

コマンド実施すると、warningなんかがチョイチョイ出つつも、`flat`という名前のUnix実行ファイルが作成されます。

<br/>

### 2. ツール起動

手順1.にて作成した`flat`をダブルクリックなりで実行します。
すると、以下のようなWindowが起動されます。

![Screenshot](screenshot/02.png)

<br/>
<br/>

## ツール使用方法

### 1. datasetを作成する

ツールを起動したら、左上のdataset作成ボタンを押して、datasetタブを作成します。

![Screenshot](screenshot/03.png)

datasetは、複数枚の画像において、共通のkeypointを共有するannotation群のことです。

<br/>

### 2. datasetに所属する画像を選択する

datasetタブを作成したら、imageListの追加ボタンを押します。
imageListの追加ボタンを押すと、datasetに所属する画像を選択すべく、ダイアログが起動されます。

![Screenshot](screenshot/04.png)

エクスプローラー上で、datasetに所属させたい画像を選択し、「Open」ボタンを押します。

![Screenshot](screenshot/05.png)

すると、imageList上に選択された画像がラインナップされます。
メイン画面上には、その内の1枚が表示されます。

![Screenshot](screenshot/06.png)

<br/>

### 3. keypointを追加する

画像を選択したら、いよいよkeypointを追加していきます。
マウスのカーソルを、keypointを追加したい位置まで運び、右クリックを押します。
右クリックメニューの中から、「Add」を選択します。

![Screenshot](screenshot/07.png)

そうすると、keypointが追加されます。

![Screenshot](screenshot/08.png)

このキーポイントは、マウスのドラッグで動かすことができます。

![Screenshot](screenshot/09.png)

同様にして、keypointを増やしていきます。

![Screenshot](screenshot/10.png)

<br/>

### 4. keypointを連結する

keypointが増えてくると、それぞれの意味を追跡しづらくなってきます。
その対策として、keypoint間の関係性を示す連結線を追加しましょう。
必ずも必要なものではないですが、沢山の画像でannotationを行った際に、ジワジワありがたくなってくるオペレーションです。

<br/>

連結線を繋ぐには、先ず、対象の2点を選択します。

![Screenshot](screenshot/11.png)

次に、上部メニューにある「Link」ボタンを押します。
これで、点が線で連結されます。

![Screenshot](screenshot/12.png)

<br/>

### 5. keypoint情報を保存する

keypointが配置できたら、その情報を保存します。
上部メニューにある保存のボタンを押します。
そうすると、ファイル保存用のダイアログが起動されます。

![Screenshot](screenshot/13.png)

ファイル名を入力し、「Save」ボタンを押します。

![Screenshot](screenshot/14.png)

そうすると、ファイルにkeypoint情報が出力されます。

![Screenshot](screenshot/15.png)

<br/>

### 6. 別画像にて、keypointを編集する

別の画像で、keypointを編集するために、メニューにある「List」ボタンを押します。
すると、keypoint横にインデックス番号が表示されます。

![Screenshot](screenshot/16.png)

その状態で、imageListにある別画像を選択します。
そうすると、keypointの数や、連結線の概念はそのままに、別画像に切り替わります。

![Screenshot](screenshot/17.png)

別画像においても、同様にkeypointの位置を調整します。

![Screenshot](screenshot/18.png)

これを対象画像全てに対して実施して、keypoint情報を保存すれば、annotation作業完了です。

<br/>

# keypoint情報を、pythonで取り込む

# 対象画像に対して前処理を実施する

# 備考

  - datasetに対して、後から画像を足すと、どうもバグるっぽい…（予め対象はバシッと決めとかなきゃダメか…）


