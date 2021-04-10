# NeuralNetworkConsole-Titanic-Sample
[Neural Network Console](https://dl.sony.com/ja/)でKaggleのタイタニックを学習するサンプルです。<br>
<img src="https://user-images.githubusercontent.com/37477845/114264025-79a01800-9a23-11eb-858f-a4fe888daf7f.gif" width="60%"><br><br>
本リポジトリには以下の内容を含んでいます。<br>
* Jupyter Notebook：データセット前処理(欠損値、Ordinal Encoding)
* Neural Network Console：学習、構造自動探索
* Neural Network Console：ONNXファイルエクスポート
* Jupyter Notebook：推論


# Requrement(Neural Network Console)
* Neural Network Console 2.0

# Requrement(Python)
* numpy 1.18.5 or later
* pandas 1.1.4 or Later
* onnxruntime 1.5.2 or later 

# Directory
<pre>
│  01_create_dataset.ipynb
│  04_inference.ipynb
│  
├─01.original_data
│  └─titanic
│       gender_submission.csv
│       test.csv
│       train.csv
│          
├─02.data
│      test.csv
│      train.csv
│      validation.csv
│          
├─03.nnc_project
│  │  titanic_sample.sdcproj
│  │  
│  └─titanic_sample.files
│              
├─04.model
│      model_20210410_163453.onnx
│      
└─05.result
        submission.csv
</pre>
<details>
<summary>ディレクトリ内容</summary>

### 01_create_dataset.py
データセット作成用のスクリプトです。<br>
01.original_dataのデータをNeural Network Consoleに読み込める形にします。

### 04_inference.ipynb
モデル推論用のスクリプトです。<br>
Neural Network ConsoleからエクスポートしたONNXファイルを用いて推論を行い、submission.csvを作成します。

### 01.original_data
Kaggle Titanicの[データセット](https://www.kaggle.com/c/titanic/data)です。

### 02.data
01_create_dataset.pyを用いて前処理を行いNeural Network Consoleで読み込める形にしたデータセットです。

### 03.nnc_project
Neural Network Consoleのプロジェクトファイルです。

### 04.model
学習後にエクスポートしたONNXファイルです。

### 05.result
04_inference.ipynbを用いて推論した結果です。
スコア：0.75837
</details>

# Model
モデル構造は以下の通りです。<br>
* 自動探索開始時<br><img src="https://user-images.githubusercontent.com/37477845/114264511-5cb91400-9a26-11eb-97ae-99a983481698.png" width="40%">
* 自動探索実施後に性能が良かったもの<br><img src="https://user-images.githubusercontent.com/37477845/114264502-4ca13480-9a26-11eb-86f9-a1f3080ee28f.png" width="40%">

# Author
高橋かずひと(https://twitter.com/KzhtTkhs)

# License 
Single-Hand-Localization is under [Apache v2 License](LICENSE).
