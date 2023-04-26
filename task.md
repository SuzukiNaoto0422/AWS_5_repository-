# AWS第5回課題の提出  
  
## ①pumaでのサンプルアプリケーションのデプロイ  
![puma実行](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E8%AA%B2%E9%A1%8C(puma).png?raw=true)  

## ②unicornでのサンプルアプリケーションのデプロイ  
![unicorn実行](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E8%AA%B2%E9%A1%8C(unicorn).png?raw=true)  
  
## ③ALBの作成  
1.ターゲットグループの作成  
![ターゲットグループ](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/Target%20groups.png?raw=true)  
  
2.ALBの作成  
![ALB](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/ALB.png?raw=true)  

## ④S3の作成  
![S3](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/S3.png?raw=true)  
今回はS3をアプリケーションのバックアップとして使用。  
AWS CLIをインストールし、EC2インスタンスとS3を接続。  
変更を加えたファイルをS3にアップロードしたりS3からEC2にファイルをインストールし以前の状態に戻せるように設定。  
  
### 具体的な動作について  
①AWS CLIのインストール  
以下のコマンドを実行
```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```  

②バージョンを確認する
```
aws --version
```  

③S3の作成

④EC2でS3の中身を確認
```
# aws s3 ls s3://バゲット名でAWS S3バケット内のオブジェクトの一覧を取得
aws s3 ls s3://bucket-tutorial-raisetech
```

⑤S3にサンプルアプリケーションをアップロード
```
# bucket-tutorial-raisetechの名のバケットにアップロード 
# クローンしたraisetech-live8-sample-appにcdしてから実行
aws s3 cp /home/ec2-user/raisetech-live8-sample-app s3://bucket-tutorial-raisetech/raisetech-live8-sample-app/ --recursive
```  
コマンドのまとめ
```
# EC2インスタンスからS3にデータをアップロード
aws s3 cp を使用
aws s3 cp /home/ec2-user/raisetech-live8-sample-app s3://bucket-tutorial-raisetech/raisetech-live8-sample-app/ --recursive   
→　/home/ec2-user/raisetech-live8-sample-appにあるファイルやディレクトリをS3バケットbucket-tutorial-raisetechのraisetech-live8-sample-app/というキーの下に再帰的にアップロード  

# EC2インスタンスからS3にデータを上書きしたい場合
aws s3 cp /home/ec2-user/raisetech-live8-sample-app s3://bucket-tutorial-raisetech/raisetech-live8-sample-app/ --recursive --no-guess-mime-type


# EC2インスタンスからS3上のオブジェクトを削除
aws s3 rm を使用
aws s3 rm s3://bucket-tutorial-raisetech/raisetech-live8-sample-app/ --recursive
→　AWS S3上のbucket-tutorial-raisetechというS3バケット内のraisetech-live8-sample-appというディレクトリとその中に含まれるファイルを全て削除するコマンド

# S3からEC2インスタンスにダウンロード  
aws s3 cp を使用  
aws s3 cp s3://bucket-tutorial-raisetech/raisetech-live8-sample-app /home/ec2-user/raisetech-live8-sample-app --recursive
→　S3のmy-bucketバケット内のraisetech-live8-sample-appディレクトリをEC2の/home/ec2-user/ディレクトリにダウンロード  
※--recursive：指定したパスがディレクトリの場合、そのディレクトリ以下の全てのファイルをダウンロードするためのオプション
```  


## ⑤AWS構造図の作成  
![AWS構造図](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E6%A7%8B%E9%80%A0%E5%9B%B3.png?raw=true)  
