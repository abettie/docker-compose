# 日本語対応mysql

## 起動
```
docker-compose up -d
```

## MySQL接続
```
docker exec -it mysqltest mysql -u mysql -p
```

## debian接続
```
docker exec -it mysqltest bash
```

## 停止
```
docker-compose down
```

## ログ確認
```
docker-compose logs
```