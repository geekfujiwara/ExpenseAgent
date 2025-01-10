# ExpenseAgent
経費精算のQA・旅費計算・経費申請を支援するエージェントです。

エージェントは経費に関する社内の複雑なルールの質問にも答えつつ、定義している旅費プランから出張の基準金額を取得し、さらに経費申請を代行してくれます。

![image](https://github.com/user-attachments/assets/4159cc0a-49dc-41bd-bc02-557dd00ffd25)


https://github.com/user-attachments/assets/7ec4bcf3-4a9f-4747-8540-3d91c01ef87d

この結果は、モデル駆動型アプリにて、申請内容を確認することができます。

https://github.com/user-attachments/assets/50de97b5-a527-4a07-a527-bc64de2538a1

## エージェントの説明

エージェントの役割は以下のように3つ定義されています。

```
あなたは、出張の経費ルールについて答え、また、申請を行う頃ができるエージェントです。
プランを取得して、出張を申請することができます。以下の役割があります。新入社員にもわかるように、丁寧に、前提知識がなくてもわかるように伝えます。

### 旅行金額の確認
* 旅行プランシステムから出張の出発地と目的地を確認し、金額をユーザーに案内します。

### 出張申請
* 出張申請を行います。申請後、経費申請システムから取得した申請番号をユーザーに返します。

### QA対応
* 内部で持つ出張ルールを検索して、様々なパターンを想定してセクションを分けて回答します。
```

![image](https://github.com/user-attachments/assets/74025e26-cb47-412c-9937-fbc146e1fbc6)

QAに関しては、エージェントには経費ルールのドキュメントがアップロードされております。

![image](https://github.com/user-attachments/assets/1c647323-c0c9-4074-86ce-afd33cf55068)

このルールに関する質問について回答を行うことができます。

## 前提条件

* Power Apps モデル駆動型アプリの利用にはPower Apps Premium ライセンスが必要です。トライアルまたは開発者プランの提供もあります。
* Copilot Studio の利用には、従量課金プランまたはスタンドアローンライセンスが必要です。トライアルも可能です。

## ソリューションのインポート方法

[ソリューションをダウンロード](https://github.com/geekfujiwara/ExpenseAgent/releases/tag/ExpenseAgent)します。

ソリューションからインポートを選択します。

![image](https://github.com/user-attachments/assets/f6c3c511-08f3-4459-90b7-5a111b52ee26)

Zip形式のままファイルをアップロードし、ウイザードに従ってインポートします。

![image](https://github.com/user-attachments/assets/63ff920d-b134-48f5-be41-fa2b04efa414)

このまま進めます。

![image](https://github.com/user-attachments/assets/c6782b8e-e50d-4294-9780-3c5d2ca89359)

Dataverse への接続を行います。エージェントが利用しているPower Automate で利用しています。

![image](https://github.com/user-attachments/assets/a2fc7d3d-0b08-4b51-bcac-c809fbf81a6e)

インポートが完了したらマネージドのタブにあるソリューションを開きます。

![image](https://github.com/user-attachments/assets/ec3fb855-3ca8-4650-84cd-39ab02e91027)

すべてのカスタマイズを公開します。

![image](https://github.com/user-attachments/assets/212b4aa6-8924-4994-8de3-12f916aa5712)

クラウドフローがオンになっているか確認します。オンになっている場合はOKです。

![image](https://github.com/user-attachments/assets/ea1c484c-768f-40a7-8093-18336bfaff00)

インポートが完了しました。

## エージェントの使い方

モデル駆動型アプリを開いておきます。

![image](https://github.com/user-attachments/assets/fed0b018-a966-46a2-babf-82da137c21fc)


まだ何もデータが登録されていません。

旅行のテーブルはエージェントが利用するため、経路ごとの費用を入れておきます。

東京から大阪の費用が15000円として入れておきます。

![image](https://github.com/user-attachments/assets/40f4222d-64ca-4be4-8942-85e2e1be443a)

ソリューションに戻ります。

エージェントを開きます。

![image](https://github.com/user-attachments/assets/9e3b3ff7-2776-4d03-a2f1-580de8a85fdd)

このように質問してみます。

![image](https://github.com/user-attachments/assets/b3c2f78f-3318-4afe-9bb5-6ce0d1ff3ba8)

詳細に回答してくれました。

> [!Note]
> マネージドソリューションでインポートした場合は既存のナレッジを変更できないので、ナレッジを見ることはできませんが、実際にはあるので、それに基づいて回答してくれます。必要に応じてアンマネージドソリューションをインポートしてください。

![image](https://github.com/user-attachments/assets/e9763f67-5bb4-48f0-b496-7abf957682e2)


東京から大阪までの出張費用を質問してみます。

![image](https://github.com/user-attachments/assets/b1aab517-54e7-415b-8f2a-a86696c42466)

自動的にアクションを選択して先ほど登録したレコードをもとに回答をしてくれました。

![image](https://github.com/user-attachments/assets/b16780e7-7c1b-48ce-b811-f50f64bdc120)

このまま、経費を申請してみます。

![image](https://github.com/user-attachments/assets/6104cfe2-a2a3-4e0d-8655-b5aece57428a)

これまでの会話履歴を元に、自動的に金額についても入力してくれました。

![image](https://github.com/user-attachments/assets/534a4b91-5a9b-4e8c-ac98-bb04dbf3489b)

Power Apps を見てみます。経費の申請が行われていることがわかります。

![image](https://github.com/user-attachments/assets/8a52771b-c8e6-48a8-9185-462352e248cc)

この用に利用することができればただしくエージェントをインポートすることができています。

## FAQ

Q: エージェントが英語で回答してくる。どうして？

A: 2025/01/10 時点では自動的にアクションやナレッジを選択するジェネレーティブオーケストレーションが英語にしか対応しておらず、ベースの言語を英語にしています。そのため、エージェントが英語で回答するケースがあります。Copilot Studio のアップデートをご期待ください。緩和するには、指示に日本語で回答することという条件を加えると改善されるケースがあります。

