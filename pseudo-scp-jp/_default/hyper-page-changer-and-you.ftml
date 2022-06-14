[[div_ class="breadcrumbs"]]
[http://scp-jp.wikidot.com/other-link-hub お役立ちリンク集] » [http://scp-jp.wikidot.com/advanced-formatting-and-you 高度なフォーマットとあなた] » [http://scp-jp.wikidot.com/listpages-magic-and-you ListPagesの魔法とあなた] >> 単一ページ遷移構文とあなた
[[/div]]
[[module css]]
.breadcrumbs {
  margin: -1em 0 1em;
  font-size: 85%;
}
:root {
  --title-colour: #333;
}
h1 {
  color: var(--title-colour);
  font-family: Arial,sans-serif;
  font-size: 250%;
  margin: 0;
  text-align: center;
  font-weight: bold;
}
#header h1 {
  font-size: 190%;
}
#page-content > h2 {
  color: var(--title-colour);
  font-family: Arial,sans-serif;
  font-size: 150%;
  margin: 0;
  text-align: center;
  font-weight: bold;
}
#page-content > hr {
  margin: 0;
}
.contents OL {
  counter-reset: item
}
.contents LI {
  display: block
}
.contents LI:before {
  content: counters(item, ".") " ";
  counter-increment: item
}
[[/module]]
[[iftags]]
[[include :scp-jp:listpages-magic-and-you]]
[[/iftags]]

2017年4月、[[*user physicslike]]氏によって開発されたHyper Page Changer --　　-- よく聞く言葉だと単一ページ遷移構文とも言われています。 --　　-- は、今やSCP-JPになくてはならないほどのものになりました。

最近では2か月に一回は単一ページ遷移構文を使用した際に不具合が出た、などの質問が構文チャンネルに上がるほどです。今回は、そんな[*http://scp-jp.wikidot.com/esoteric-syntax 難解Wikidot構文]の中でも最難関の難しさを誇る単一ページ遷移構文の解説をしていこうと思います。
[[size 85%]]
この記事は[*http://scp-jp.wikidot.com/listpages-magic-and-you ListPagesの魔法とあなた]で説明されているLPTがSCP-JPではあまり使われていないためSCP-JPでよく使われる単一ページ遷移構文を説明した記事になります。
[[/size]]
----
[[div class="contents"]]
**Contents:**
# [#toc0 単一ページ遷移構文とは何か?]
 # [#toc1 単一ページ遷移構文とLTPの違い]
 # [#toc2 単一ページ遷移構文の仕組み]
 # [#toc3 ページコンテンツとオフセット]
# [#toc4 単一ページ遷移構文(応用編)]
 # [#toc5 コメントアウトを無くそう]
 # [#toc6 CSSの可能性]
[[/div]]
@@@@
-----
+ 1: 単一ページ遷移構文とは何か?
-----
@@@@
単一ページ遷移構文とはその名の通り、同じページ内で複数の記事を表示させることができる技術です。そんなことができるのかと思われる方もいるかもしれません。一番有名な単一ページ遷移構文が使われている記事は[http://scp-jp.wikidot.com/scp-2000-jp SCP-2000-JP]でしょうか。あの記事も単一ページ遷移構文でページ遷移を繰り返しています。単一ページ遷移構文にはページ自体を変更せずに表示を変更できるというメリットがあるのです。

ListPagesモジュールにはページコンテンツ自体を参照する変数[[footnote]] いろいろな値をとって変わる数量を表している文字を変数という。
--　　-- [*https://kotobank.jp/word/変数-8693 コトバンク]より引用 [[/footnote]]が備わっています。その変数を利用して単一ページ遷移構文は動いています。変数や引数の説明は第二節で行います。
@@@@
-----
++ 1.1: 単一ページ遷移構文とLTPの違い
-----
@@@@
基本的な動き方はLPT[[footnote]] LPTとは[http://scp-jp.wikidot.com/listpages-magic-and-you ListPagesの魔法とあなた]で登場する単語である。
**要約:** LPTとは、SCP (または任意のページ) に複数のページがあるように見せ、1ページずつ閲覧はできるがすべて同じ評価モジュールとなっている記事のことです。LPTは、ページ上のリンクをクリックした後のURLをチェックすることで簡単に識別できます。もしページのURLが"/offset/X"（Xは数字）で終わっていればLPTです。LPTのほとんどは、このような方法で特定することができます。 [[/footnote]]と同じく、ListPagesモジュールで表示する部分を切り替えているだけです。では、LTPとなにが異なるのか。それは表示する部分が同じ記事にあるか、子ページとなっているかという違いです。
@@@@
-----
++ 1.2: 単一ページ遷移構文の仕組み
-----
@@@@
では早速、単一ページ遷移構文の構造を見ていきましょう。これは4ページの内容を示した構文です。
[http://scp-jp.wikidot.com/listpages-magic-and-you ListPagesの魔法とあなた]と同じく、初めて見るパラメータもあると思いますので注意して見てください。
[[>]]
--　　-- [*http://scp-jp.wikidot.com/esoteric-syntax/offset/1/page2_limit/1#toc21 難解Wikidot構文]より引用
[[/>]]
> **全ページ共通部分トップ**
> @@[[module ListPages offset="@URL|0" range="." wrapper="no" separate="no"]]@@
> @@%%content{2}%%@@
> @@[[/module]]@@
> @@[[module ListPages limit="@URL|0" range="." urlAttrPrefix="page2" wrapper="no" separate="no"]]@@
> @@%%content{3}%%@@
> @@[[/module]]@@
> @@[[module ListPages limit="@URL|0" range="." urlAttrPrefix="page3" wrapper="no" separate="no"]]@@
> @@%%content{4}%%@@
> @@[[/module]]@@
> @@[[module ListPages limit="@URL|0" range="." urlAttrPrefix="page4" wrapper="no" separate="no"]]@@
> @@%%content{5}%%@@
> @@[[/module]]@@
> **ページを増やす場合はここにモジュールを追加**
> @@[!--@@
> @@====@@
> **1ページ目の本文**
> @@[http://@@**scp-jp.wikidot.com/pagename**/offset/1/page2_limit/1 **2ページ目へのリンク**]
> @@====@@
> **2ページ目の本文**
> @@[http://@@**scp-jp.wikidot.com/pagename**/offset/1/page3_limit/1 **3ページ目へのリンク**]
> @@====@@
> **3ページ目の本文**
> @@[http://@@**scp-jp.wikidot.com/pagename**/offset/1/page4_limit/1 **4ページ目へのリンク**]
> @@====@@
> **4ページ目の本文**
> @@[http://@@**scp-jp.wikidot.com/pagename** **1ページ目へのリンク**]
> @@====@@
> **ページを追加する場合はこの部分に文章と====を追加**
> @@--]@@
> **全ページ共通部分ボトム**
ここで新しい用語がいくつか出てきましたので、今一度確認しましょう。
: **offset="@URL|0"** : これは、[*http://scp-jp.wikidot.com/listpages-magic-and-you#toc12 ListPagesの魔法とあなた]にある通り，相対位置をURLから取得します．{{@URL|0}}に関しては[[[doc-listpages-module#toc0|]]]に説明があるので読んでください．
: **range="."** : definition
: **wrapper="no"** : definition
: **separate="no"** : definition
: **urlAttrPrefix="pageN"** : definition