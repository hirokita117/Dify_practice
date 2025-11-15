# Dify_practice
Dify の練習

# Dify の立ち上げ（ローカル）
2025年11月現在、下記の方法が一番簡単

```sh
git clone https://github.com/langgenius/dify.git

cd dify

cd docker

cp .env.example .env

docker compose up -d
```

## Gemini を LLM として使う設定

ref: https://qiita.com/b-wind/items/f45afb8a0cb4a43a1f60

### Gemini API キーの取得（Google AI Studio）

1. ブラウザで **Google AI Studio** にアクセス
2. 「Get API Key」→「APIキーを作成」
3. 生成された API キーをコピーして安全な場所に保存

### Dify 側のモデルプロバイダーに Gemini を登録

ローカル Dify にログインし、右上のアイコン → **設定** → **モデルプロバイダー** へ。

1. 「Gemini」にカーソルを合わせて「インストール」をクリック
2. インストール後、「セットアップ」をクリック
3. 表示された画面の「API Key」欄に、先ほど AI Studio で取得した API キーを貼り付けて保存

### Dify の「システムモデル」を Gemini にする

次に Dify 全体で使うデフォルトモデルを設定します。

1. 同じく設定画面から **「システムモデル設定」** を開く
2. 「システム推論モデル」をクリック
3. 一覧から使いたい Gemini モデルを選ぶ

   * 例：`Gemini 2.0 Flash-Lite` や `Gemini 1.5 Pro` など（環境や用途によって選択）
4. 保存

これで、チャットボット等を作ったときにデフォルトで Gemini が使われるようになります。
