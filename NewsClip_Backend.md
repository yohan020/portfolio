# 🚀 概要
本リポジトリは、**NewsClipサービスのバックエンドサーバー**であり、
Go言語（Ginフレームワーク）をベースに構築されたRESTful APIサーバーです。

- 📰 NAVERニュースAPIを活用したニュース収集
- 🤖 OpenAI APIによるニュース要約機能
- 💬 コミュニティ・コメント・通知システム
- 🔐 JWTベースの認証および権限管理
- 🗄 PostgreSQLデータベース連携

フロントエンド（Flutter）アプリと通信し、リアルタイムでのデータ提供およびユーザーアクティビティの処理を行います。

[Repository](https://github.com/KIT-OpenSource-GAEBALBADAK/NewsClip-Backend.git)

---

## ⚙️ 開発環境

| 項目 | 内容 |
|------|------|
| Go Version | **1.24.9** |
| Framework | **Gin Web Framework** |
| Database | **PostgreSQL 15+** |
| ORM | **GORM v2** |
| Auth | **JWT (github.com/golang-jwt/jwt/v5)** |
| API連携 | **Naver News API**, **OpenAI API** |
| 環境管理 | `.env`ファイルベース (godotenv使用) |
| デプロイ環境 | Ubuntu 24.04 LTS (Nginx Reverse Proxy + Certbot SSL) |

---

## 📂 ディレクトリ構成

```
backend/
├── cmd/
│   └── main.go                     # サーバー実行のエントリーポイント
│
├── config/
│   ├── config.go                   # 環境変数のロードおよび初期設定
│   └── database.go                 # PostgreSQL接続設定
│
├── internal/
│   ├── app/                        # コアアプリケーションロジック
│   │   ├── controllers/            # HTTPハンドラ (Ginコントローラー)
│   │   │   ├── auth_controller.go
│   │   │   ├── news_controller.go
│   │   │   ├── shorts_controller.go
│   │   │   ├── community_controller.go
│   │   │   ├── comment_controller.go
│   │   │   └── admin_controller.go
│   │   │   │
│   │   ├── services/               # ビジネスロジック
│   │   │   ├── auth_service.go
│   │   │   ├── news_service.go
│   │   │   ├── post_service.go
│   │   │   ├── short_service.go
│   │   │   ├── comment_service.go
│   │   │   └── notification_service.go
│   │   │   │
│   │   ├── repositories/           # データベースアクセス層
│   │   │   ├── user_repository.go
│   │   │   ├── news_repository.go
│   │   │   ├── post_repository.go
│   │   │   └── comment_repository.go
│   │   │   │
│   │   ├── models/                 # DBモデル構造体 (GORMベース)
│   │   │   ├── user.go
│   │   │   ├── news.go
│   │   │   ├── post.go
│   │   │   ├── short.go
│   │   │   ├── comment.go
│   │   │   └── report.go
│   │   │   │
│   │   ├── middlewares/            # 認証 / ロギング / CORS / エラーハンドリング
│   │   │   ├── auth_middleware.go
│   │   │   ├── cors_middleware.go
│   │   │   └── logging_middleware.go
│   │   │   │
│   │   ├── routes/                 # ルーティング定義
│   │   │   └── router.go
│   │   │   │
│   │   └── utils/                  # 共通ユーティリティ
│   │       ├── jwt.go
│   │       ├── password.go
│   │       └── response.go
│   │
│   ├── migrations/                 # DBマイグレーションSQLファイル
│   │   ├── 001_create_users.sql
│   │   ├── 002_create_news.sql
│   │   └── ...
│   │
│   └── seeds/                      # 初期データ (例: 管理者アカウント)
│       └── seed_admin.go
│
├── pkg/                            # 外部パッケージおよびHelperモジュール
│   ├── openai/                     # OpenAI API要約モジュール
│   └── navernews/                  # NAVERニュースAPIクライアント
│
├── test/                           # 単体テストコード
│   ├── auth_test.go
│   ├── news_test.go
│   └── post_test.go
│
├── .env                            # 環境変数 (DB_URL, JWT_SECRETなど)
├── go.mod
├── go.sum
└── README.md
```

---

## 🔑 環境変数 (.env 例)

```env
# Server
PORT=8080
GIN_MODE=release

# Database
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=yourpassword
DB_NAME=newsclip

# JWT
JWT_SECRET=super_secret_key

# External APIs
NAVER_CLIENT_ID=your_client_id
NAVER_CLIENT_SECRET=your_client_secret
OPENAI_API_KEY=your_openai_api_key
```

---

## 🧠 サーバーの実行方法

### 1️⃣ 依存関係のインストール
```bash
go mod tidy
```

### 2️⃣ 環境変数の設定
```bash
cp .env.example .env
```

### 3️⃣ サーバーの起動
```bash
go run cmd/main.go
```

### 4️⃣ 動作確認
```bash
curl http://localhost:8080/v1/ping
# {"message":"pong"}
```

---

## 🧩 主な機能

| モジュール | 機能 |
|------|------|
| **Auth** | 会員登録、ログイン、JWT認証 |
| **News** | NAVERニュースAPI連携、ニュースの高評価/ブックマーク |
| **Shorts** | OpenAIによる要約、リール形式のニュースフィード |
| **Community** | 投稿・コメントのCRUD、専門家/一般ユーザーの区分 |
| **Notification** | キーワードベースのプッシュ通知 |
| **Admin** | 通報処理、ユーザー利用停止、権限変更 |

---

## 🧪 テストの実行

```bash
go test ./test/...
```

---

## 🌐 デプロイ情報

| 項目 | 内容 |
|------|------|
| サーバー IP | 40.81.180.143 |
| Base URL | https://newsclip.duckdns.org/v1 |
| Reverse Proxy | Nginx + Certbot SSL |
| Database | PostgreSQL (Docker または ローカル) |
