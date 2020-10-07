## README

# Laragram
・Laravelを使った記事投稿アプリケーションです。  
・作成期間 2020/9/26〜2020/10/9（14日間） 
<img src="https://github.com/longmt0225/laravel/blob/main/image.index.png">

# 主な使用言語
<img src="https://github.com/longmt0225/laravel/blob/main/image.php.png" width="100px"> <img src="https://github.com/longmt0225/laravel/blob/main/image.Laravel.jpg" width="100px"> 

# アプリケーション概要
このアプリでは、ユーザーが自由に記事を投稿することができます。投稿するにはユーザー登録が必要です。自分が投稿した記事は更新や削除をすることもできます。  

# 制作背景
「今何をしているか」などを投稿する機能を有するアプリケーションに、メモや備忘録としても使用できる機能が備わっていたら便利だと思ったので、このアプリケーションを制作することにしました。  

# テスト用アカウント
・メールアドレス sample@sample.com  
・パスワード sample01  

# 実装した機能
## 記事一覧機能  
投稿された記事がトップページに一覧で表示されます。  
<img src="https://github.com/longmt0225/laravel/blob/main/image.index.png" width="500px">

## ユーザー登録機能  
ユーザーがアカウントを登録することができます。  
![Animated GIF-downsized](https://user-images.githubusercontent.com/69623233/95037912-a0ddfb80-0707-11eb-862c-1da96af3763b.gif)

## ログアウト機能  
ユーザー登録後にログアウトすることができます。  
![Animated GIF-downsized (1)](https://user-images.githubusercontent.com/69623233/95038268-adaf1f00-0708-11eb-8695-6ea9fc8f01ec.gif)

## ログイン機能
ログアウト後にログインすることができます。  
![Animated GIF-downsized (2)](https://user-images.githubusercontent.com/69623233/95038681-b5bb8e80-0709-11eb-8c75-45c98ceecb50.gif)

## 記事投稿機能
アカウントを登録したユーザーが記事を投稿することができます。  
![Animated GIF-downsized (3)](https://user-images.githubusercontent.com/69623233/95039524-fae0c000-070b-11eb-9b1e-922e3f9b7f54.gif)

## 記事更新機能
自分で投稿した記事を編集して更新することができます。  
![Animated GIF-downsized (4)](https://user-images.githubusercontent.com/69623233/95040102-a63e4480-070d-11eb-9c88-1827faf7b9db.gif)

## 記事削除機能
自分で投稿した記事を削除することができます。  
![Animated GIF-downsized (5)](https://user-images.githubusercontent.com/69623233/95040360-6592fb00-070e-11eb-8aa3-73fd31c886ab.gif)

# 工夫したポイント
・ビューにMDBootstrapというフレームワークを使用することでデザインを美しくしました。  
・利用者が使いやすいようにシンプルなアプリケーションにすることを心掛けました。

# 今後実装したい機能
・画像投稿機能  
・フォロー機能

# URL紹介
https://laragram-29239.herokuapp.com/

# テーブル設計
## ER図  
<img src="https://github.com/longmt0225/laravel/blob/main/image.ERD.png" width="750px">

## users テーブル
| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| name             | string     | null: false, uniqueness: true  |
| email            | string     | null: false, uniqueness: true  |
| password         | string     | null: false                    |
| articles         | references | null: false, foreign_key:true  |
### Association
- has_many :articles, dependent: :destroy

## articles テーブル
| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| title            | string     | null: false                    |
| body             | string     | null: false                    |
| user             | references | null: false, foreign_key:true  |
### Association
- belongs_to :user
