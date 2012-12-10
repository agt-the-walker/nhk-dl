Purpose
-------

I wrote these two scripts to download videos from
[NHK高校講座](http://www.nhk.or.jp/kokokoza/), so that I could play them
offline with `mplayer`. 

Requirements
------------

* [Ruby](http://www.ruby-lang.org/en/) 1.9.2+
* [mimms](http://savannah.nongnu.org/projects/mimms/) (I used 3.2.1)

The following Ruby [gems](http://rubygems.org/):

* [mechanize](http://rubygems.org/gems/mechanize) (I used 2.0.1 and 2.5.1).
Note that Ubuntu 12.04's `libwww-mechanize-ruby1.9.1` is too old (1.0.0-1).

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
    [...]

Note that `nhk-dl` can easily take several days! For this reason, if it gets
interrupted and you run it again, it will only download missing videos
(providing you specify the same destination directory).

Limitations
-----------

`nhk-dl` doesn't download the videos in parallel. If speed is important to you,
please consider
[nhk_download.sh](https://github.com/Christoph-D/Tools/blob/master/nhk_download.sh)
instead.

Error handling could be improved. Right now `nhk-dl` exits as soon as it cannot
download a video successfully. Moreover, it doesn't clean partially downloaded
videos.
