## 問題文要旨
- 2つの整数(a, b)を読み込み下記の計算結果を出力せよ
    - a ÷ b ： d (整数)
    - a ÷ b の余り ： r (整数)
    - a ÷ b ： f (浮動小数点数)
- fについては, 0.00001以下の誤差があってもよい
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int a, b;
	cin >> a >> b;

	cout << a / b << " " << a % b << " " << fixed << 1.0 * a / b << endl;
}
```
## 学んだこと
### 混合演算(C++)
- 混合演算(異なる型どうしの演算)は精度の高いほうへ型変換が行われる
### 表示桁数の指定(C++)
- `printf()`の場合, 入力フォーマット指定子を用いる
    - 入力フォーマット指定子, `%f`, `%lf`相当が`cout`における, `fixed`か?
- float型, double型ともにデフォルトでは, 小数点以下6桁で表示される(Clangコンパイラの場合)
    - `cout << fixed << 3.1415926535 << endl; // "3.141593"`
    - `printf("%f\n", 3.1415926535); // "3.141593"`
    - `printf("%lf\n", 3.1415926535); // "3.141593"`
- [入出力ストリーム](https://www-he.scphys.kyoto-u.ac.jp/member/n-kota/dokuwiki/doku.php?id=ja:cpp:iostream)のフォーマット指定, フォーマット指定子を参照

