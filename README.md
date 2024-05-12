# automated_essay_scoring

## バックグラウンドでの動作
```
cd /notebooks/automated_essay_scoring
# あらかじめ、mutiple_run.sh内に実行したいnotebookを記載する
nohup ./multiple_run.sh &
```

## 動いているかの確認
```
ps aux | grep python
```

## Kill
```
pkill runnb
```

## GitHubからのpull
```
cd /notebooks/automated_essay_scoring/
ssh-keygen -t ed25519 -C "sinchir0"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```

```
以下のリンクで、New SSH Keyを行う,keyの名前はpaperspace_YYMMDD
https://github.com/settings/keys
```

```
git pull origin main
# commitをする場合は以下も追加
git config --global user.email "<YOUR_EMAIL_ADDRESS>"
```

## git add, commit, push

```
git add -u
git config --global user.email "<YOUR_EMAIL_ADDRESS>"
git commit -m "add"
git push origin main
```

## メモリの確認
```
vmstat -t 2
```

### Ref
https://docs.github.com/ja/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## nbconvertで変換した際に、ログに残るかどうか
- printで出力したものは残る
- notebookの一番最後に実行し、Notebookの機能で出力したものは残らない

## kaggle cliの利用方法

### 準備
```
mkdir -p ~/.kaggle/
cp /notebooks/pll_data_detection/kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
```

```
pip install kaggle
```