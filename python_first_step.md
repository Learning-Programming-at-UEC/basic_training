電気通信大学　プログラミング教室
# Python 1st Stepの基礎トレ　説明

## 1 1st Stepの趣旨説明

| 項目 | 説明 |
| ----------- | ------------ |
| 項目 | 初めてPython3でプログラミングする人 |
| ねらいその1 | 人とコンピュータは「人がデータやプログラムを入力 → コンピュータが処理 → コンピュータが出力＝人が結果を得る」という関係．<br>この関係を、2つの方法で体験する．<br>2つの方法とは「インタラクティブ・モード」と「スクリプト・モード」 |
| ねらいその2 | プログラミングによる問題解決手法「順次・選択・繰り返し」のうちの「順次」を理解し、打ち込み・動かす経験をして自分の技にする |
| ねらいその3 | これまでアプリを使う側だった人が、作り手側の考え方と方法を身につける |
| 方法 | コード例を手打ちで入力して動かす．<br>コードの解説を読んで意味を理解する　→　クイズで理解度を確認．<br>エラー・メッセージを読み修正する |
| 想定時間 | 20時間：　「いろはボード」に毎日、取り組み時間を記録します |


## 5 Python3 インタラクティブモードで文字を表示させよう

| 要点 | 説明 |
| ----------- | ------------ |
| 目的 | Pythonとの対話を楽しむ |
| 得られる知識 | - print( ) 関数<br> - 英語の打ち込み方<br> - 文字の表示
| 手順 |（1）>>> の後の青文字を打ち込む<br>（2）リターンキーを押す<br>（3）結果を見る<br>（4）赤字のエラーメッセージが出たら、どこかに間違いがあるので、前と違うやり方で試す。 |

```
>>> print( " Hello World ! " )
Hello World
>>> print "Hello"
SyntaxError: Missing parentheses in call to 'print'
>>> print ("Hello")
Hello
>>> print ('Hello')
Hello
>>> print ('''Hello''')
Hello
>>> print('Hello World')
Hello World
>>> print("""Hello World""")
Hello World
>>> print('''Hello World''')
Hello World
>>> print("Hello World')
SyntaxError: EOL while scanning string literal
>>>  "Hello World"
'Hello World'
>>> Hello World
SyntaxError: invalid syntax
>>> 'Hello World'
'Hello World'
>>> 'That's a bird.'
SyntaxError: invalid syntax
>>> "That's a bird."
"That's a bird."
>>> print("That's a bird.")
That's a bird.
```


[Top Page](https://learning-programing-at-uec.github.io/basic_training/)