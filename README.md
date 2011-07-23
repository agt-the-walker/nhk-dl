Purpose
-------

I wrote these two scripts to download videos from
[NHK高校講座](http://www.nhk.or.jp/kokokoza/library/index.html), so that I
could play them offline with `mplayer`.

Requirements
------------

* [Ruby](http://www.ruby-lang.org/en/) 1.9.2+
* [mplayer](http://www.mplayerhq.hu/)

The following Ruby [gems](http://rubygems.org/):

* [escape](http://rubygems.org/gems/escape) (I used 0.0.4)
* [mechanize](http://rubygems.org/gems/mechanize) (I used 2.0.1)

Usage
-----

    $ mkdir ~/kokokoza
    $ ./kokokoza-videos >kokokoza-videos.txt
    $ ./nhk-dl ~/kokokoza <kokokoza-videos.txt

    # after a while...
    $ cd ~/kokokoza; find -type f
    ./世界史/01 - 帝国・王国・共和国　〜世界史の中の国家〜.wmv
    ./世界史/02 - オリエントとギリシア.wmv
    ./世界史/03 - ローマ帝国　〜平和とそのかげり〜.wmv
    ./世界史/04 - 古代インド　〜仏教とアショーカ王〜.wmv
    ./世界史/05 - 東南アジア世界の形成　〜海を渡ったラーマーヤナ〜.wmv

Note that `nhk-dl` can easily take several days! For this reason, if it gets
interrupted and you run it again, it will only download missing videos
(providing you specify the same destination directory).
