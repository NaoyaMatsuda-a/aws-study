# aws-study
AWS環境構築（超初級）

# AWS Hands-on Web Server構築

## プロジェクト概要
AWSを使用して、インターネット公開されたシンプルなWebサーバー環境を構築しました。
VPC、サブネット、インターネットゲートウェイ（IGW）、EC2インスタンス、セキュリティグループを組み合わせ、インフラの基本構成を理解することを目的としています。

---

## 使用したAWSサービス
- VPC
- サブネット（パブリックサブネット）
- インターネットゲートウェイ（IGW）
- ルートテーブル
- セキュリティグループ
- EC2（Amazon Linux 2、Apacheインストール）

---

## 構成図
![image](https://github.com/user-attachments/assets/cf93dc04-bbb5-47f5-b0f3-089ca896fe22)



---

## 作業手順概要
1. VPC作成（CIDR: 10.0.0.0/16）
2. パブリックサブネット作成（CIDR: 10.0.1.0/24）
3. インターネットゲートウェイ作成・VPCへアタッチ
4. ルートテーブル作成・パブリックサブネットと関連付け
5. セキュリティグループ作成（SSH:22番、HTTP:80番開放）
6. EC2インスタンス作成（Amazon Linux 2）
7. ユーザーデータでApacheインストール＋起動
8. ブラウザからパブリックIPにアクセスし、Webページ表示を確認

---

## ssh接続画面
![スクリーンショット 2025-04-29 012026](https://github.com/user-attachments/assets/e4b9350e-601c-4b2a-9066-94012be0cd1b)
![スクリーンショット 2025-04-29 012049](https://github.com/user-attachments/assets/aa7dc343-7d26-4582-97c8-5dedc0d2ebbc)


---

## WEBページ表示確認画面
![スクリーンショット 2025-04-29 012139](https://github.com/user-attachments/assets/47bd5b34-977d-4e5e-a403-c98df284f1d3)


---

## 学び・気づき
- パブリックサブネットに正しくルートテーブルを関連付けないと、インターネット接続できない。
- セキュリティグループ設定を忘れると、SSH接続やHTTPアクセスができない。
- 起動時ユーザーデータを活用することで、インスタンス初回起動時に自動でApacheをインストール・起動できる。

---

## 今後の課題・チャレンジ
- ALB（Application Load Balancer）とAuto Scaling Groupの連携による可用性向上に挑戦したい。
- Route53を使用した独自ドメインによるアクセスにもチャレンジしたい。
- Infrastructure as Code（Terraform、CloudFormation）にも取り組みたい。

---
