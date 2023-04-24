## AWS第5回課題の提出  
  
### ①pumaでのサンプルアプリケーションのデプロイ  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E8%AA%B2%E9%A1%8C(puma).png?raw=true)  

### ②unicornでのサンプルアプリケーションのデプロイ  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E8%AA%B2%E9%A1%8C(unicorn).png?raw=true)  
  
### ③ALBの作成  
1.ターゲットグループの作成  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/Target%20groups.png?raw=true)  
  
2.ALBの作成  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/ALB.png?raw=true)  

### ④S3の作成  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/S3.png?raw=true)  
今回はS3をアプリケーションのバックアップとして使用。  
AWS CLIをインストールし、EC2インスタンスとS3を接続。  
変更を加えたファイルをS3にアップロードしたりS3からEC2にファイルをインストールし以前の状態に戻せるように設定。  

### ⑤AWS構造図の作成  
![](https://github.com/SuzukiNaoto0422/AWS_5_repository-/blob/main/picture/AWS%E6%A7%8B%E9%80%A0%E5%9B%B3.png?raw=true)  
