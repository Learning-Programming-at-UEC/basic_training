電気通信大学　プログラミング教室
# 3rd Step の 基礎トレ　説明と確認　2019年6月版

## 趣旨の説明

| 項目 | 説明 |
| ----------- | ------------ |
| ねらい | 脱初心者 |
| 方法 | 写経しながらコードの意味を理解する。<br>応用する。 |
| 想定時間 | 30時間 |


## 0　2nd Stepの復習
### リスト
```
>>> num = [1, 2, 3, 4, 5]
>>> num
[1, 2, 3, 4, 5]
>>> num[0]
1
>>> num[5]		# インデックスにない指定をすると
Traceback (most recent call last):
  File "<pyshell#79>", line 1, in <module>
    num[5]
IndexError: list index out of range
>>> num[-1]
5
```

### リストは変更可能（ミュータブル）
```
>>> odd_num = [1, 3, 5, 7, 10]		# 奇数のリスト　間違ってしまった
>>> odd_num[4]=9			# 変更
>>> odd_num				# これで大丈夫
[1, 3, 5, 7, 9]
```

### append()メソッド
```
>>> odd_num.append(11)
>>> odd_num
[1, 3, 5, 7, 9, 11]
```

### len()関数
```
>>> len(odd_num)
6
```

### リストの入れ子（ネスト）
```
>>> o_n = [1, 3, 5]		# 奇数のリスト
>>> e_n = [2, 4, 6]		# 偶数のリスト
>>> num = [o_n, e_n]		# 2つのリストのリスト
>>> num
[[1, 3, 5], [2, 4, 6]]
>>> num[1]			# 2番目の要素（リスト）を取り出す
[2, 4, 6]
>>> num[0][1]			# 最初の要素の2番目の値を取り出す
3
```

### if文
```
>>> x = int(input('整数を入れてください：'))
整数を入れてください：20
>>> if x >= 0:
...     print("正の数を入れましたね")
... elif x == 0:
...     print("0を入れましたね")
... else:
...     print("負の数を入れましたね")
...
正の数を入れましたね
```

### for文
```
>>> words = ["art", "lemon", "river"]
>>> for w in words:
...     print(w)
...
art
lemon
river
```

### range() 関数
```
>>> for i in range(5):          # for i in range(0, 6): と同じ
...     print(i)
...
0
1
2
3
4
```


## 1　コメント

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | Pythonの中で、コメントの書き方やその効果について理解する |
| キーワード | コメント、#|

{% highlight Python linenos %}
print("Hello world") # ←この「#」シャープ記号の後ろはコメントになる
# コメントとして記述された文はプログラムとして認識されない
# print("code after # won't be processed")
# for i in range(10):
#     print("nothing happened")
{% endhighlight %}

### 解説
　コメントはプログラムの中でプログラムとして認識されない部分だ。認識されないからといって、大事でないという訳ではない。
　プログラミングするのは人間である。人間の脳は完璧ではないので、自分が書いたコードの意味をすぐに忘れてしまう。コメントを書くことで、自分がコードを書く時の考えを整理し、保存できる。
　プログラミング言語で記述された部分は理解しづらい。しかしコメントでは、日常生活で使う言葉を使って、自分が理解できるように記述できる。

格言
*プログラムを書いたらすぐコメントを書け。一ヶ月後の自分は完全に別人だからだ！*

この先のサンプルコードのコメントの部分は解説として読むこと。入力・実行する必要は無い。


## 2　関数を作る、使う

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | 簡単な関数を作る |
| キーワード | 関数定義 |
| 行数 | 20行程度|

関数の定義は必ず 「`def`」 で始まる。英単語 define (定義する)の略。
「`def`」の後に一スペースを開けて、関数の名前を書く。

{% highlight Python linenos %}
def nanimosinaikansuu(): # 今回は「何もしない関数」と命名した
    pass # 何もしないので、passで関数をスキップ
{% endhighlight %}

次は、足し算をする関数を定義してみる。
{% highlight Python linenos %}
def tasizann(a,b): # 関数名の後のカッコの中に「仮引数名」を書く
    c = a + b # aとbの中にデータが入っていると仮定して足し算をする
    return c
{% endhighlight %}

　「仮引数」とは、関数の中で処理したいデータがあるとき、そのデータを変数で処理したいので、とりあえず今は仮の名前を与えて、その仮の名前を持つ変数を処理する。
今回は `a` と `b` を仮引数とする。

　データを呑み込んで、データを吐き出すのが一般的な関数。
データを吐き出す時、まず「`return`」(リターン)を書いて、「`return`」の後に一スペースを空いて、吐き出したいデータを書く。

　関数を使うときも簡単だ。関数の定義をする時に書いた関数名を書いて、その後にカッコを書いて、カッコの中に必要なデータを入れて(なければ入れない)、その関数は使用される。
例えば:
{% highlight Python linenos %}
kekka = tasizann(12, 56)
print(kekka)
{% endhighlight %}

「`tasizann`」(足し算)関数を使って、12足す56を計算する、その結果を「`kekka`」に代入する。


## 3　`cd` コマンド
`cd`コマンドは「change directory」を略したコマンドである。「ディレクトリの変更」という意味。皆さんが使っているUnixやLinuxでは、このコマンドを使って、ディレクトリ(フォルダ)を移動する。
以下のコマンドで「`/`」ルートディレクトリに行く。
```
$ cd /
```

以下のコマンドで「自分のディレクトリ」に行く
```
$ cd ~
```


## 4　`ls` コマンド
`ls`コマンドは「list」の略したコマンドである。「『今のディレクトリ』にあるファイルを表示する」。

```
$ ls
```

自分の`Anaconda`ディレクトリに入って中に何が入っているかを確認してみよう

```
$ cd ~/Anaconda3
$ ls
```

すると、以下のように、ディレクトリの中に入っているファイルとディレクトリが表示される。

```
./                      lib/                               qml/
../                     libexec/                           resources/
Anaconda-Navigator.app/ man/                               sbin/
bin/                    mkspecs/                           selenium/
conda-meta/             org.freedesktop.dbus-session.plist share/
condabin/               phrasebooks/                       shell/
doc/                    pkgs/                              ssl/
etc/                    plugins/                           translations/
include/                python.app/                        var/
```

`/`が末尾についているのはディレクトリで、`/`が無いのはファイルである。


## 5　ファイルに書き込んで実行してみる
　今までは全部、pythonの「インタラクティブモード」でやってきた。
これからはpythonのコードをファイルに保存して、実行してみよう。
　以下はエディタの簡単の使い方、好きなエディタを選んでやってみよう。
どれが良いのかがわからない人は自分の担当講師に聞いてください。
「vimの使い方」
「atomの使い方」
以上のエディタを使って、以下のコードをファイル`hello_world.py`に保存しよう。

{% highlight Python linenos %}
for i in range(10):
    print(i, "hello world")
{% endhighlight %}

今、`hello_world.py`が作られたとする。以下のコマンドを打つと
```
$ python3 hello_world.py
```

以下の様な表示が出てくるはず

```
0 hello world
1 hello world
2 hello world
3 hello world
4 hello world
5 hello world
6 hello world
7 hello world
8 hello world
9 hello world
```

次は`hello_world.py`を下のように編集し直そう。

{% highlight Python linenos %}
for i in range(10):
    print("hello","*"*i,"world")
{% endhighlight %}

また上と同じように実行してみよう。すると、以下のような表示が出てくるはず。

```
hello  world
hello * world
hello ** world
hello *** world
hello **** world
hello ***** world
hello ****** world
hello ******* world
hello ******** world
hello ********* world
```

この様にして、自分の書きたいコマンドをファイルとして保存できる


## 6　インデントで決まるコードブロック
pythonはインデントによってコードブロックが決まる言語になる。


インデントって何？
例えば、以下のコードの2行目、print関数を入力する前に、4スペース分が開けられているのがわかる。

{% highlight Python linenos %}
for i in range(5):
    if True:
        print("Nice to meet you")
{% endhighlight %}

この2行にの前に開けられているのはインデントである。
3行目の先頭に開けている8スペース分もインデントである。

インデントは何をするの？
インデントはコードの実行範囲を決める。
例えば、以下のコードをまず実行してみよう。

{% highlight Python linenos %}
for i in range(5):
    if True:
        print("Nice to meet you")
        print(i, "hogehoge")
{% endhighlight %}

以下の結果になるはず。

```
Nice to meet you
0 hogehoge
Nice to meet you
1 hogehoge
Nice to meet you
2 hogehoge
Nice to meet you
3 hogehoge
Nice to meet you
4 hogehoge
```

## 7　サンプルプログラム
以下は脱初心者用のトレーニング。
写経、改良した後、自分の発想で企画・開発。
機会があるごとに報告や発表。
報告や発表後にテーマを変更しても何も問題なし。

### (1)　リストと関数定義のサンプル （作者　宮澤修　Osamu MIYAZAWA）

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | タートルが様々な色とサイズの正方形をランダムな位置に100個表示する |
| キーワード | リスト、関数定義、グラフィック |
| 行数 | 20行程度 |
| URL | |

{% highlight Python linenos %}
# リストと関数定義のサンプル　（宮澤修 作）
import random
import turtle
t = turtle.Pen()
t.shape("turtle")
t.width(3)
t.speed(0)
colorlist = ['red', 'green', 'blue', 'orange', 'gray', 'brown', 'gold']

def square(size):
    for i in range(4):
        t.forward(size)
        t.left(90)

for i in range(100):
    x = random.randrange(-200, 200)
    y = random.randrange(-200, 200)
    t.up()
    t.goto(x, y)
    t.down()
    col = random.choice(colorlist)
    t.color(col)
    square(random.randrange(10, 200))
{% endhighlight %}

### (2)　ユーグリッドの互除法　（作者　相原大希 Hiroki AIBARA）

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | 最小公倍数を求めるプログラム |
| キーワード | ユーグリッドの互除法、関数定義、再帰処理 |
| 行数 | 10行程度 |
| URL | |

{% highlight Python linenos %}
# ユーグリッドの互除法　（相原大希 作）
def gcd(x, y):
    if y == 0:
        return x
    else:
        return gcd(y, x % y)

x = int(input('はじめの数字を入れてください：' ))
y = int(input('二番目の数字を入れてください： '))

print(gcd(x, y))
{% endhighlight %}

### (3)　シェルピンスキーの三角形（作者　富樫治輝 Haruki TOGASHI）

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | シェルピンスキーの三角形を描くプログラム |
| キーワード | 関数定義、条件分岐 |
| 行数 | 20行程度 |
| URL | |

{% highlight Python linenos %}
# シェルピンスキーの三角形（富樫治輝 作）
d = int(input('層数を入力してください:'))
print(d,"層のシェルピンスキーの三角形を描きます")
from turtle import *

def sankakkei(hen,n):
    if n == 0:
        down()
    else:
    for i in range(3):
        forward(hen)
        left(120)
        sankakkei(hen / 2, n - 1)

speed(0)
up()
setx(-300)
sety(-250)
down()

sankakkei(600,d)
input()
{% endhighlight %}

### (4)　コッホ曲線（作者　富樫治輝 Haruki TOGASGI）

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | コッホ曲線描くプログラム |
| キーワード | 関数定義、条件分岐 |
| 行数 | 20行程度 |
| URL | |

{% highlight Python linenos %}
# コッホ曲線（富樫治輝 作）
k = int(input('何段階まで描きますか？:'))
print(k,"段階のコッホ曲線を描きます")
from turtle import *

def triangle (steps, n):
    if n == 1:
        forward(steps)
    else:
        triangle(steps / 3, n - 1)
    left(60)
    triangle(steps / 3, n - 1)
    right(120)
    triangle(steps / 3, n - 1)
    left(60)
    triangle(steps / 3, n - 1)

speed('fastest')
up()
setx(-400)
down()

triangle(800, k)
input()
{% endhighlight %}

### (5)　グリコのゲーム（作者　木村 紗瑛  Sae KIMURA）

| 要点 | 説明 |
| ----------- | ------------ |
| どんなプログラムか | コンピュータとじゃんけん勝負するゲーム |
| キーワード | 条件分岐 |
| 行数 | 50行程度 |
| URL | |

{% highlight Python linenos %}
# インデントにご注意願います
import random
print("a : あなた b : コンピューター")
a = 0
b = 0
goal = 20
print("グリコ開始!!")
while (a < goal) and (b < goal) :
    print("------")
    print("0:グー 1:チョキ 2:パー")
    com = random.randint(0,2)
    you = int(input("あなたの手は? : "))
    print("コンピューターの手は? : "+ str(com))
    n = (com - you + 3) % 3
    if n == 0:
        print("あいこ")
        print("進めないよ(>_<)m")
    elif n == 1 :
        print("勝ち!!")
        if you == 1:
            print("チ・ョ・コ・レ・ー・ト")
            print("6歩進めるよ(^[]^)v")
            a = a + 6
        elif you == 2:
            print("パ・イ・ナ・ッ・プ・ル")
            print("6歩進めるよ(^[]^)v")
            a = a + 6
        else :
            print("グ・リ・コ")
            print("3歩進めるよ(^[]^)v")
            a = a + 3
    else :
        print("負け!!")
        if com == 1 :
            print("チ・ョ・コ・レ・ー・ト")
            print("6歩進まれるよ(>_<)m")
            b = b + 6
        elif com == 2 :
            print("パ・イ・ナ・ッ・プ・ル")
            print("6歩進まれるよ(>_<)m")
            b = b + 6
        else :
            print("グ・リ・コ")
            print("3歩進まれるよ(>_<)m")
            b = b + 3
    print("a:" + ">" * a + "&")
    print("b:" + ">" * b + "&")

if a == b :
    print("引き分け")
elif a > b :
    print("あなたの勝ち")
else :
    print("あなたの負け")
{% endhighlight %}

[Top Page](./index)
