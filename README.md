# どっとコミュ

> Java開発研修（新人向け、4週間@6月）では、Javaに関する基本的な講義を受けつつ、演習形式で本システムを作成する。

# システム方針（エレベータピッチ）
* 後続研修（７～８月）の新人 向けの、
* 日報システム というプロダクトは、
* 日報としての使いやすさを追い求めたWebアプリケーション です。
* これは SNSのように他の人の日報がタイムラインで見られ、コメントをすることができ
* 無理やりベンダーのLMS（学習管理システム）を利用して日報を書くの とは違って、
* 他者とコミュニケーションを円滑に行える仕組み が備わっている。

# システムアーキテクチャ
* FW : Spring Boot(Spring MVC)
* View : JSP
* DB : Oracle

# 機能要件
## 機能一覧

|業務|機能|備考|学習できる技術要素(ﾒｲﾝﾀｰｹﾞｯﾄはJava)
|---|---|---|---
|日報|タイムライン|・ユーザが投稿した日報を新着順に、SNSのタイムライン形式で一覧表示する。<br>・自分が登録した日報をフィルターすることができる。<br>・ホーム画面。|・検索結果をListで取得できる。<br>・SQLでORDER BY句が利用できる。<br>・JSTLのforeach文を用いて一覧表示ができる。
|日報|日報投稿|・日報を投稿する。<br>・研修の満足度、満足度理由を投稿する。|・入力、確認、戻る、完了といった一連の処理を実装できる。<br>・Form精査を実装できる。<br>・SQLでINSERT文が実装できる。<br>・JSPでエラーメッセージを実装できる。
|日報|日報内容|・タイムラインで選択した日報の内容を表示する。<br>・コメント入力、表示機能を備える。<br>・ログインユーザと投稿者が同じでなければ、編集画面には遷移することができないように実装する。|・主キーによる検索ができる。<br>・JSP、Javaにおける条件分岐を実装できる。
|日報|日報編集|・日報を編集する。|・日報投稿とほとんど同じ<br>・SQLでUPDATE文が実装できる。
|日報|日報検索|・投稿日、投稿者、ワード等で日報を検索し、検索条件に当てはまった日報を一覧表示する。|・条件分岐を実装する際に、複数のSQLを組み立てられる。<br>・SQLでLike句を用いて部分一致ができる。
|日報|コメント機能|・日報内容に対して、コメントをする。<br>・コメントは、編集・削除ができる。|・CRUD処理全てを実装できる。

## 機能一覧（内部）

|業務|機能|備考|学習できる技術要素(ﾒｲﾝﾀｰｹﾞｯﾄはJava)
|---|---|---|---
|ユーザ管理|ユーザ登録|・ユーザ名、パスワードを登録する。|・登録処理を実装できる。<br>・パスワード暗号化を実装できる。
|ユーザ管理|ログイン|・登録されたユーザ、パスワードでログインする。|・認証を実装できる。

## 機能一覧（発展）

|業務|機能|備考|学習できる技術要素(ﾒｲﾝﾀｰｹﾞｯﾄはJava)
|---|---|---|---
|日報|通知機能|・コメントがあったことを通知する機能。|・JSPでの条件分岐を実装できる。
|日報|友達機能|・タイムラインに、友達フィルター機能を追加する。|・CRUD処理全てを実装できる。
|ｺﾐｭﾆｹｰｼｮﾝ|チャット|・ユーザ同士が１対１でチャットする。|・非同期処理を実装できる。
|ｺﾐｭﾆｹｰｼｮﾝ|掲示板|・講師に仕事について質問する掲示板。|・CRUD処理を実装できる。
|研修分析|満足度集計結果|・その日時点での満足度集計結果を表示する。<br>・テーマごとの満足度が分かる。|・数値処理を実装できる。
|研修分析|ﾃｷｽﾄﾏｲﾆﾝｸﾞ|・頻出コメントを一覧化する。|・難易度の高いプログラムを実装できる。
|ユーザ管理|認可|・研修分析は、管理者ユーザしか操作閲覧できない。|・認可を実装できる。
