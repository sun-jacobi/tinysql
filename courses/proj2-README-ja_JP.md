# Parser

## 概要

Parserの章では、TinySQLがどのようにコードをASTに変換するのかについて解説する

## SQL処理の流れ

データベースでは、SQLを通じてデータを操作する。しかし、sql自体はただのテキストで、データがSQLを処理する前に、SQL 文を受け取り、その有効性を確認するなどの必要がある。これは実は、プログラミング言語のコンパイルと似ている。

Parserを紹介する前には、SQL文がTinySQLでどのように処理されるかについて解説する。

![SQL](imgs/proj2-1.png)

上の図は、TinySQLでSQL文がどのように処理されるかを示しています。左から見ると、ユーザーMySQL Clientを使用してTinySQLと接続を確立するときには、図の中のProtocol Layerが使われている。TinySQLがSQL 文を正常に受け取って、処理を試みる。 これが、図の中のSQL Core Layerの部分である。この章で扱う内容は、一番上にあるParserのことだ。

## Parser 

