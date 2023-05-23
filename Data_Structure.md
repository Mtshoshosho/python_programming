# データ構造（Data Structure）

## リスト型（List）
`リスト型`とは、複数のデータをまとめて扱うためのデータ型です。
リスト型は、`[]`（角括弧）で囲んだ中に、複数のデータをカンマ区切りで並べて記述します。
```python
list = [1, 2, 3]
print(list) # [1, 2, 3]
```
リスト型の要素には、数値や文字列など、どんなデータ型でも格納することができます。
```python
list = [1, "Hello", 3]
print(list) # [1, 'Hello', 3]
```
リスト型の要素には、リスト型を格納することもできます。
```python
list = [1, [2, 3], 4]
print(list) # [1, [2, 3], 4]
```
リスト型の要素には、変数を格納することもできます。
```python
num = 1
list = [num, 2, 3]
print(list) # [1, 2, 3]
```

リストの要素の結合は、`+`を使う。
```python
list_a = [1,2,3,4,5]
list_b = [6,7,8,9,10]
list_c = list_a + list_b
print(list_c) # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
`extend`メソッドを使うことで、リストの要素を結合することができる。
```python
list_a = [1,2,3,4,5]
list_b = [6,7,8,9,10]
list_a.extend(list_b)
print(list_a) # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### リストのメソッド
リスト型には、リストの要素を操作するためのメソッドが用意されています。
リストのメソッドは、`リスト名.メソッド名()`のように記述します。

`index`メソッドは、リストの要素のインデックスを取得する。
```python
list = [1, 2, 3]
print(list.index(2)) # 1
```

`count`メソッドは、リストの要素の数を取得する。
```python
list = [1, 2, 3, 2]
print(list.count(2)) # 2
```

`append`メソッドは、リストの末尾に要素を追加する。
```python
list = [1, 2, 3]
list.append(4)
print(list) # [1, 2, 3, 4]
```

`insert`メソッドは、リストの指定した位置に要素を追加する。
```python
list = [1, 2, 3]
list.insert(1, 4)
print(list) # [1, 4, 2, 3]
```

`sort`メソッドは、リストの要素を昇順に並び替える。
```python
list = [3, 2, 1]
list.sort()
print(list) # [1, 2, 3]
```

`reverse`メソッドは、リストの要素を逆順に並び替える。
```python
list = [1, 2, 3]
list.reverse()
print(list) # [3, 2, 1]
```

`split`メソッドは、リストの要素を指定した文字列で分割して、リストに格納する。
```python
str = "Hello World"
list = str.split(" ")
print(list) # ['Hello', 'World']
```

`join`メソッドは、リストの要素を指定した文字列で結合する。
```python
list = ['Hello', 'World']
str = " ".join(list)
print(str) # Hello World
```


### リストのコピー
リスト型の変数を別の変数に代入すると、同じリストが参照される。
```python
list_a = [1, 2, 3]
list_b = list_a
list_b[0] = 4
print(list_a) # [4, 2, 3]
print(list_b) # [4, 2, 3]
```

`copy`メソッドを使うことで、リストのコピーを作成することができる。
```python
list_a = [1, 2, 3]
list_b = list_a.copy()
list_b[0] = 4
print(list_a) # [1, 2, 3]
print(list_b) # [4, 2, 3]
```

値渡しと参照渡しの違い
変数や関数の引数に値を渡す方法には、**値渡し**と**参照渡し**の2種類があります。
値渡しは、値のコピーを渡す方法で、参照渡しは、値の参照を渡す方法です。
変数に値を代入すると、値渡しによって値のコピーが作成されます。
```python
num_a = 1
num_b = num_a
num_b = 2
print(num_a) # 1
print(num_b) # 2
```
リスト型の変数を別の変数に代入すると、参照渡しによって同じリストが参照されます。
そのため、上記のlist_aとlist_bの例のように、list_bの要素を変更すると、list_aの要素も変更されます。
そこで、リストのコピーを作成するには、copyメソッドを使うことで、値渡しによってリストのコピーを作成することができます。
`id`関数は、変数の参照を取得する。
```python
list_a = [1, 2, 3]
list_b = list_a
list_c = list_a.copy()
print(id(list_a)) # 140539547316864
print(id(list_b)) # 140539547316864
print(id(list_c)) # 140539547316992
```
list_aとlist_bは、同じ参照を持っているので、id関数で取得した参照は同じになります。
list_aとlist_cは、異なる参照を持っているので、id関数で取得した参照は異なります。
よって値渡しによってリストのコピーを作成するには、copyメソッドを使うことで、リストのコピーを作成することができます。

### リストの使い所
リスト型は、複数のデータをまとめて扱うためのデータ型です。
```python
seats = []
min = 0
max = 5
```
上記のように、リスト型の変数を使うことで、複数のデータをまとめて扱うことができます。
```python
seats = []
min = 0
max = 5
```
シートの長さ
```python
min <= len(seats) < max
```
シートの長さが、min以上、max未満の場合にTrueを返す。
```python
seats.append("p")
min <= len(seats) < max # True
```
シートに5人を追加する。
```python
seats.append("p")
seats.append("p")
seats.append("p")
seats.append("p")
min <= len(seats) < max # False
```
シートから一人を削除する。
```python
seats.pop()
min <= len(seats) < max # True
```


## タプル型（Tuple）
`タプル型`も同様に、複数のデータをまとめて扱うためのデータ型です。
タプル型は、`()`（丸括弧）で囲んだ中に、複数のデータをカンマ区切りで並べて記述します。
```python
tuple = (1, 2, 3, 4, 5)
print(tuple) # (1, 2, 3, 4, 5)
```
タプル型とリスト型の違いは、タプル型は要素の変更ができないことです。
```python
tuple = (1, 2, 3)
tuple[0] = 4 # エラー
```
そのため読み込み用で使用することが多いです。
`タプル型`では直接Indexを指定して要素を取得することができるが、`リスト型`では`index`メソッドを使う必要がある。
```python
tuple = (1, 2, 3)
print(tuple[0]) # 1
```
```python
list = [1, 2, 3]
print(list.index(0)) # 1
```
`タプル型`は要素の変更ができないため、`count`メソッドを使うことができない。
```python
tuple = (1, 2, 3)
print(tuple.count(2)) # エラー
```
```python
list = [1, 2, 3]
print(list.count(2)) # 1
```
`タプル型`は()もしくは、`,`を使って定義する。
```python
tuple = (1, 2, 3)
tuple = 1, 2, 3
```
`タプル型`は、要素が1つの場合は、`,`を付けないと、`int型`として扱われることに注意。
```python
tuple = (1)
print(type(tuple)) # <class 'int'>
```
```python
tuple = (1,)
print(type(tuple)) # <class 'tuple'>
```

### タプルのアンパッキング
`タプル型`は、複数の変数に代入することができる。
```python
tuple = (1, 2, 3)
num1, num2, num3 = tuple
print(num1) # 1
print(num2) # 2
print(num3) # 3
```
上記のように、タプルでは変数を複数用意して、タプルを代入すると、タプルの要素が順番に変数に代入されます。
このように、タプルの要素を変数に代入することを、`タプルのアンパッキング`と呼びます。
また、値の入れ替えも、タプルのアンパッキングを使うことで、簡単に行うことができます。
```python
num1 = 1
num2 = 2
num1, num2 = num2, num1
print(num1) # 2
print(num2) # 1
```

## タプルの使い所
再代入ができないため、変更されないことが保証されているデータを扱う場合に使用する。
```python
tuple = (1, 2, 3)
```
タプル型は、リスト型よりもメモリの使用量が少ないため、リスト型よりも高速に処理することができます。
```python
import sys
list = [1, 2, 3]
tuple = (1, 2, 3)
print(sys.getsizeof(list)) # 88
print(sys.getsizeof(tuple)) # 72
```


## 辞書型（Dictionary）
`辞書型`は、キーと値のペアを複数格納するためのデータ型です。
辞書型は、`{}`（波括弧）で囲んだ中に、キーと値のペアを`:`（コロン）で区切って記述します。
```python
dict = {"key1": "value1", "key2": "value2"}
print(dict) # {'key1': 'value1', 'key2': 'value2'}
```

### 辞書型のメソッド
辞書型には、辞書の要素を操作するためのメソッドが用意されています。
辞書のメソッドは、`辞書名.メソッド名()`のように記述します。
`辞書名.keys()`は、辞書のキーを取得する。
```python
dict = {"key1": "value1", "key2": "value2"}
print(dict.keys()) # dict_keys(['key1', 'key2'])
```
`辞書名.values()`は、辞書の値を取得する。
```python
dict = {"key1": "value1", "key2": "value2"}
print(dict.values()) # dict_values(['value1', 'value2'])
```
`辞書名.update()`は、辞書の要素を更新する。
```python
dict = {"key1": "value1", "key2": "value2"}
dict.update({"key1": "value3"})
print(dict) # {'key1': 'value3', 'key2': 'value2'}
```
`辞書名.get()`は、辞書の要素を取得する。
```python
dict = {"key1": "value1", "key2": "value2"}
print(dict.get("key1")) # value1
```
`辞書名.pop()`は、辞書の要素を削除する。
```python
dict = {"key1": "value1", "key2": "value2"}
dict.pop("key1")
print(dict) # {'key2': 'value2'}
```
`辞書名.clear()`は、辞書の要素を全て削除する。
```python
dict = {"key1": "value1", "key2": "value2"}
dict.clear()
print(dict) # {}
```

### 辞書のコピー
辞書型の変数を別の変数に代入すると、同じ辞書が参照される。
```python
dict_a = {"key1": "value1", "key2": "value2"}
dict_b = dict_a
dict_b["key1"] = "value3"
print(dict_a) # {'key1': 'value3', 'key2': 'value2'}
print(dict_b) # {'key1': 'value3', 'key2': 'value2'}
```
`copy`メソッドを使うことで、辞書のコピーを作成することができる。
```python
dict_a = {"key1": "value1", "key2": "value2"}
dict_b = dict_a.copy()
dict_b["key1"] = "value3"
print(dict_a) # {'key1': 'value1', 'key2': 'value2'}
print(dict_b) # {'key1': 'value3', 'key2': 'value2'}
```
list型と同様に、辞書型も値が参照渡しになるため、copyメソッドを使うことで、辞書のコピーを作成することができます。

### 辞書の使い所
オブジェクトのプロパティを表現する場合に使用する。つまりは、Keyを使用してValueを取得する場合に使用する。
```python
dict_fruits = {"apple": 100, "banana": 200, "orange": 300}
```
また、辞書型ではハッシュテーブルというデータ構造を使用しているため、検索処理が高速に行うことができます。


## 集合型（Set）
`集合型`は、重複しない要素を複数格納するためのデータ型です。
集合型は、`{}`（波括弧）で囲んだ中に、複数の要素をカンマ区切りで並べて記述します。
```python
set = {1, 2, 3}
print(set) # {1, 2, 3}
```
集合型は、重複する要素を格納することができません。
```python
set = {1, 2, 3, 3}
print(set) # {1, 2, 3}
```
集合型は、要素の順番を保持しません。
```python
set = {1, 2, 3}
print(set) # {1, 2, 3}
```
集合型は、要素の順番を保持しないため、インデックスを指定して要素を取得することができません。
```python
set = {1, 2, 3}
print(set[0]) # エラー
```

### 集合型のメソッド
`add`メソッドは、集合に要素を追加する。
```python
set = {1, 2, 3}
set.add(4)
print(set) # {1, 2, 3, 4}
```
`remove`メソッドは、集合から要素を削除する。
```python
set = {1, 2, 3}
set.remove(3)
print(set) # {1, 2}
```
`clear`メソッドは、集合の要素を全て削除する。
```python
set = {1, 2, 3}
set.clear()
print(set) # set()
```

### 集合の使い所
共通点や差分を求める場合に使用する。
- ユースケース...ユーザーの趣味を集合型で管理しておき、共通点や差分を求めることで、マッチングを行うことができます。
```python
set_a = {1, 2, 3}
set_b = {2, 3, 4}
```
共通点を求める。
```python
set_a & set_b # {2, 3}
```
差分を求める。
```python
set_a - set_b # {1}
```
和集合を求める。
```python
set_a | set_b # {1, 2, 3, 4}
```
対象差を求める。
```python
set_a ^ set_b # {1, 4}
```
list型から集合型に変換する。
- ユースケース...list型の要素の重複を削除する場合に使用する。
```python
list = [1, 2, 3]
set = set(list)
print(set) # {1, 2, 3}
```


