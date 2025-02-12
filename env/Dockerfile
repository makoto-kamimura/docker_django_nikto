# Pythonの公式イメージを使用
FROM python:3.9

# 必要なシステムパッケージをインストール
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    perl \
    curl \
    git \
    && apt-get clean

# 作業ディレクトリ設定
WORKDIR /app

# requirements.txt を先にコピーして依存関係をインストール
COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip \
    && pip install --no-cache-dir -r requirements.txt

# Niktoのセットアップ
RUN git clone https://github.com/sullo/nikto.git /usr/local/nikto \
    && ln -s /usr/local/nikto/program/nikto.pl /usr/local/bin/nikto

# アプリケーションコードをコピー
COPY . .

# ポート公開
EXPOSE 8000

# アプリケーション実行
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "vulnerability_assessment.wsgi:application"]
