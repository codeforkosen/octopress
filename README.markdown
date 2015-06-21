# Code for KOSEN on Octopress

## ブログ更新方法

codeforkosen.github.ioの方は生成物をoctopressがpushしてるだけのリポジトリ。
更新にはこちらを使うみたい。

[Documentation](http://octopress.org/docs/)


### 準備

* `rbenv install 2.1.1`: このバージョンのRubyが必要らしい
  - Mac OS: http://railsgirls.jp/install/#a-2-homebrewhttpbrewsh
  - Linux: http://qiita.com/kazoo04/items/7056704efee66f323ddb
* `gem install bundler`
* `rbenv rehash`
* `bundle install`


### 記事の作成

[Blogging Basics](http://octopress.org/docs/blogging/)

rakeのタスクで記事のベースを生成できる。
ブログの記事は`source/_posts`に格納されている。

#### 記事のひな形を作成。

```
$ rake new_post["title"]
```

これでひな形ができます。
ちなみにtitleの部分は生成されるmarkdownファイルのファイル名に使用されるので英語で名前をつけるといいと思います。

追記: zshでそのまま実行しようとすると展開されてうまくいかない:scream_cat:のでエスケープしてやるとよかったです `rake new_post\["title"\]`
（http://qiita.com/kwgch/items/445a230b3ae9ec246fcb より）


#### 記事を書く

やること

* 生成したファイルのtitleを変更。
* メンバーとしてプロフィールを用意されている人は下のようにincludeしておく。

    `{% include _member/akashi/shibata.html %}`

* 後は記事を書くだけ。


#### 記事の生成、確認

* `rake generate`
* `rake preview`
* http://localhost:4000 にアクセスして確認


#### 記事の公開

* `rake setup_github_pages`
    * https://github.com/codeforkosen/codeforkosen.github.com
* `rake deploy`

