## 問題文要旨
- 3つの整数を小さい順にソートせよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int a, b, c;
	int t;
	cin >> a >> b >> c;

	if (a > b) {
		t = a;
		a = b;
		b = t;
	}
	if (a > c) {
		t = a;
		a = c;
		c = t;
	}
	if (b > c) {
		t = b;
		b = c;
		c = t;
	}

	cout << a << " " << b << " " << c << endl;
}
```
## 学んだこと
### ソートのアルゴリズム
- 多重条件分岐
    - 3つの整数を並べる通りは3!で6通り. 6つの条件式を書くことによって目的の出力を得る
    ```cpp
    if ( a < b && b < c ){
        cout << a << " " << b << " " << c << endl;
    } else if ( a < c && c < b ){
        cout << a << " " << c << " " << b << endl;
    } else if ( b < a && a < c ){
        cout << b << " " << a << " " << c << endl;
    } ...
    :
    :			 
    } else {
        cout << c << " " << b << " " << a << endl;
    }
    ```
    - **同じ値を持つ場合うまく動作しない可能性があり, 修正がしにくい**
- 値の入れ替え
    - 2つの変数の値を入れ替える