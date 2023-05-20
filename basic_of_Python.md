# Pythonの基礎(basic of Python)


##　変数宣言（Variable declaration）
**変数宣言**は、変数名に値を代入することで行う。
`変数名 = 値`で宣言し、型は自動的に判別されため、型宣言は不要である。
変数名は、数字から始まることはできない。また、予約語（if, for, while, def, class, など）は変数名に使うことができない。
```python
num = 1
print(num)
name = "Python"
print(name)
```

**型の確認**は、`type()`関数を使う。
```python
num = 1
print(type(num))
name = "Python"
print(type(name))
```

**型の変換**は、`int()`関数、`float()`関数、`str()`関数を使う。
`int()`関数は、小数点以下を切り捨てる。
`float()`関数は、小数点以下を切り捨てない。
`str()`関数は、文字列に変換する。
```python
num = 1
print(type(num))
num = float(num)
print(type(num))
num = str(num)
print(type(num))
```

## print関数
**print関数**は、引数に指定した値を出力する。
```python
print("Hello World")
```

**複数の値**を出力する場合は、カンマで区切る。
```python
print("Hello", "World")
```

## 数値
pythonの数値には、**整数**と**浮動小数点数**がある。
```python
num = 1
print(type(num))
num = 1.0
print(type(num))
```

**四則演算**は、`+`、`-`、`*`、`/`、`%`を使う。
```python
print(1 + 1) # 2
print(1 - 1) # 0
print(2 * 2) # 4
print(2 / 2) # 1.0
print(2 % 2) # 0
```

**べき乗**は、`**`を使う。
```python
print(2 ** 2) # 4
```

**割り算の商**は、`//`を使う。
```python
print(5 // 2) # 2
```

**割り算の余り**は、`%`を使う。
```python
print(5 % 2) # 1
```

**インクリメント**は、`+=`を使う。
```python
num = 1
num += 1
print(num) # 2
```

**デクリメント**は、`-=`を使う。
```python
num = 1
num -= 1
print(num) # 0
```

**絶対値**は、`abs()`関数を使う。
```python
print(abs(-1)) # 1
```

**四捨五入**は、`round()`関数を使う。
```python
print(round(1.5)) # 2
print(round(1.4)) # 1
```

`math`モジュールを使うと、より高度な数学関数を使うことができる。
```python
import math
print(math.ceil(1.1)) # 2
print(math.floor(1.9)) # 1
print(math.sqrt(4)) # 2.0
print(math.pi) # 3.141592653589793
```
モジュールとライブラリの違い
モジュールは、Pythonのファイルのことで、ライブラリは、モジュールの集まりのことである。
`math`モジュールの確認
`math`モジュールの確認は、`help()`関数を使う。
```python
import math
help(math)
```

## 文字列
**文字列**は、`""`または`''`で囲む。
```python
print("Hello World")
print('Hello World')
```

**文字列の連結**は、`+`を使う。
```python
print("Hello" + "World") # HelloWorld
```

**文字列の繰り返し**は、`*`を使う。
```python
print("Hello" * 3) # HelloHelloHello
```

**文字列の長さ**は、`len()`関数を使う。
```python
print(len("Hello")) # 5
```

**文字列のエスケープ**は、`\`を使う。
```python
print("Hello\nWorld") # 改行 
print("Hello\tWorld") # タブ
print("Hello\"World") # ダブルクォーテーション
print("Hello\'World") # シングルクォーテーション
print("Hello\\World") # バックスラッシュ
```

複数行の文字列は、`"""`または`'''`で囲む。
```python
print("""Hello
World""")
print("""\
    Hello
    World\
""")
```

## 文字列のインデックスとスライス
**文字列のインデックス**は、`[]`を使う。
```python
print("Hello"[0]) # H
print("Hello"[1]) # e
print("Hello"[2]) # l
print("Hello"[3]) # l
print("Hello"[4]) # o
```

**文字列のスライス**は、`[start:end:step]`を使う。
```python
print("Hello"[0:2]) # He
print("Hello"[0:3]) # Hel
print("Hello"[0:4]) # Hell
print("Hello"[0:5]) # Hello
print("Hello"[0:6]) # Hello
print("Hello"[0:2:1]) # He
print("Hello"[0:3:1]) # Hel
print("Hello"[0:4:1]) # Hell
print("Hello"[0:5:1]) # Hello
print("Hello"[0:6:1]) # Hello
```

**文字列の逆順**は、`[::-1]`を使う。
```python
print("Hello"[::-1]) # olleH
```

## 文字列のメソッド
**文字列の大文字**は、`upper()`メソッドを使う。
```python
print("Hello".upper()) # HELLO
```

**文字列の小文字**は、`lower()`メソッドを使う。
```python
print("Hello".lower()) # hello
```

**文字列の置換**は、`replace()`メソッドを使う。
```python
print("Hello".replace("H", "J")) # Jello
```

**文字列の検索**は、`find()`メソッドを使う。
```python
print("Hello".find("H")) # 0
print("Hello".find("e")) # 1
print("Hello".find("l")) # 2
print("Hello".find("o")) # 4
print("Hello".find("a")) # -1
```

**文字列の検索**は、`index()`メソッドを使う。
```python
print("Hello".index("H")) # 0
print("Hello".index("e")) # 1
print("Hello".index("l")) # 2
print("Hello".index("o")) # 4
print("Hello".index("a")) # ValueError: substring not found
```

**文字列の検索**は、`startswith()`メソッドを使う。
```python
print("Hello".startswith("H")) # True
print("Hello".startswith("e")) # False
print("Hello".startswith("l")) # False
print("Hello".startswith("o")) # False
print("Hello".startswith("a")) # False
```

**文字列の検索**は、`endswith()`メソッドを使う。
```python
print("Hello".endswith("H")) # False
```

## 文字列の代入
**文字列の分割**は、`split()`メソッドを使う。
```python
print("Hello World".split()) # ['Hello', 'World']
```

**文字列の結合**は、`join()`メソッドを使う。
```python
print(" ".join(["Hello", "World"])) # Hello World
```

**文字列の埋め込み**は、`format()`メソッドを使う。
```python
print("Hello {}".format("World")) # Hello World
print("Hello {0}".format("World")) # Hello World
print("Hello {name}".format(name="World")) # Hello World
print("Hello {0} {name}".format("World", name="Python")) # Hello World Python
```

## f-string
**文字列の埋め込み**は、`f-string`を使う。
```python
name = "World"
print(f"Hello {name}") # Hello World
```

