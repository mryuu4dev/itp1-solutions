## 問題文要旨
- "Hello World"と表示するプログラムを作成せよ
- 改行を忘れないこと
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	cout << "Hello World" << endl;
}
```
## 学んだこと
### 標準出力(C++)
- `printf()`, `cout`が利用可
- `printf()`を使うには`cstdio`をインクルードする
- `cout`を使う場合, 改行は`endl`を用いる
    - `endl`は改行を行い, バッファをフラッシュする<sup>[1](#note1)</sup>
    - `cout`におけるフラッシュのタイミングは環境に依存するため, `\n`のみで改行し明示的にフラッシュを行わない場合には注意が必要
### 名前空間(C++)
- `using namespace std;`は, 一般的な開発では推奨されない
### エラー表示
- Presentation Error: 表示フォーマットの間違いのこと

## 注釈
<small id="note1">1: バッファとは, 処理を高速化するために出力データを溜めておく仕組みのことで, フラッシュ操作によって溜められたデータを出力する</small>