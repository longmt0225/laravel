## README

# Laragram
・Laravelを使った記事投稿アプリケーションです。  
・作成期間 2020/9/26〜2020/10/9（14日間） 
<img src="https://github.com/longmt0225/laravel/blob/main/image.index1.png" width="750px">

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
<img src="https://github.com/longmt0225/laravel/blob/main/image.index1.png" width="500px">

## ユーザー登録機能  
ユーザーがアカウントを登録することができます。  
![Animated GIF-downsized (7)](https://user-images.githubusercontent.com/69623233/95290289-d588b900-08a7-11eb-9491-bda92482d536.gif)

## ログアウト機能  
ユーザー登録後にログアウトすることができます。  
![Animated GIF-downsized (8)](https://user-images.githubusercontent.com/69623233/95290363-0b2da200-08a8-11eb-8931-4a86aac3cc4d.gif)

## ログイン機能
ログアウト後にログインすることができます。  
![Animated GIF-downsized (9)](https://user-images.githubusercontent.com/69623233/95290433-31ebd880-08a8-11eb-8286-1df7e464ebab.gif)

## 記事投稿機能
アカウントを登録したユーザーが記事を投稿することができます。  
![Animated GIF-downsized (10)](https://user-images.githubusercontent.com/69623233/95290516-6364a400-08a8-11eb-9902-f49ff4e4232b.gif)

## 記事更新機能
自分で投稿した記事を編集して更新することができます。  
![Animated GIF-downsized (11)](https://user-images.githubusercontent.com/69623233/95290579-8c853480-08a8-11eb-89cf-b3783d7f2f46.gif)

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
