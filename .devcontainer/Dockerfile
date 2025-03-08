# 使用するベースイメージ
FROM mcr.microsoft.com/devcontainers/typescript-node:1-22-bookworm

# 作業ディレクトリの作成
WORKDIR /workspace

# 'forcix' ユーザーを作成
# ユーザー作成
RUN useradd -m -s /bin/bash forcix

# sudoers 設定を分けて実行
RUN echo 'forcix ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers.d/forcix

# 権限を修正
RUN chown -R forcix:forcix /home/forcix

#ドッカーグループがないとエラーが起きるため、記述
RUN groupadd -f docker

# Docker グループに追加
RUN usermod -aG docker,node,npm,nvm forcix