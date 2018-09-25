# PEP: 8

## これはなに

* Pythonのコーディング規約PEP8を個人的にまとめたりしたものです。
* 個人の私見が入ることもあります。
* 公式ドキュメントは以下「参考」リンクのものを参照してください。

## 参考

* [PEP 8 -- Style Guide for Python Code](https://legacy.python.org/dev/peps/pep-0008/)
* [pep8-ja 1.0 ドキュメント](https://pep8-ja.readthedocs.io/ja/latest/)

## インデント

Pythonは他の多くの言語とは異なり、インデントの深さによってコードの解釈が変わる言語なので、インデントの規約は複雑です。

インデントにはスペース4つを使います。

```
def add_variables(value1, value2):
    return value1 + value2
```

引数などインデントで複数行に書く場合は開きカッコのレベルに揃えます。この場合、「インデントはスペース4つ」のルールには従わなくても構いません。

```
add_variables(value1,
              value2)
```

メソッド定義の引数と本体が区別しやすいように、引数部分にはインデントを加えます。

```
def add_variables(
        value1,
        value2):
    return value1 + value2
```

PEP8では以下のような1行に複数引数を書くような書き方も許容されています。
ただ、PHPのコーディング規約PSRではこれは認められていませんし、あまり見やすいものではなので、カンマごとに改行するのが良いでしょう。

```
def add_variables(value1, value2,
                  value3, value4):
    return value1 + value2 + value3 + value4
```

閉じカッコの前で改行することもできます。改行した場合のとじカッコのインデントのいちは以下のどちらかです。後者で書くパターンの言語が多いかと思います。

```
def add_variables(
        value1,
        value2
        ):
    return value1 + value2

def add_variables(
        value1,
        value2
    ):
    return value1 + value2
```

リストも同様です。

```
numbers = [
    1,
    2,
    3,
    ]

# または
numbers = [
    1,
    2,
    3,
]
```

## 空行

トップレベルの関数やクラスは2行の空行。クラス内の関数は1行の空行を挟む。

```
def add(value1, value2):
    return value1 + vaue2


def mult(value1, value2):  #空行2行
    return value1 * value2


class Square():
    
    def get_x(self):
        return self.x

    def get_y(self):
        return self.y


class Circle():

    def get_r(self):
        return self.r

    def get_x(self)
        return self.x
```

## import

