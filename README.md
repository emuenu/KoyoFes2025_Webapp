2025年こうよう祭の情報工学科学科展示用に作成したWebアプリ及びデータベースのシステム  
AWSにより配信し、Unityで作成したゲームと連携して使用した  

・React Frontend(AWS Amplify)  
・Flask Backend API(AWS EC2)  
・MySQL Database(Amazon RDS)  

FlaskのAPIをデプロイしたEC2は Nginx + Gunicorn によりWebサーバを起動  
AmplifyとEC2の通信ではDuck DNSによりドメインを取得しSSL証明書を取得しhttps化した  

## データベースのテーブル一覧

users: 各ユーザの情報を記録（ユーザIDとユーザ名を記録）  
plays: プレイ履歴（全体でのプレイ履歴をユーザと紐づけて順に記録）  
played_fishes: 釣れた魚の記録管理（各プレイでどの魚をいくつ釣ったかを順に記録）  
fishlists: 存在する魚のリスト（各オブジェクトの名前と製作者名を記録）  

・ユーザは複数回ゲームをプレイすることを想定  
・各プレイごとに総得点と釣った魚を記録  
・魚の製作者名は重複を許容  
