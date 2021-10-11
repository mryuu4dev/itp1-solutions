## 問題文要旨
- 整数xを読み込み, `Case i: x`のように表示せよ
    - iは1からインクリメントされる
- 複数のデータセットが与えられる
- xが0の時終了
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int x;
	int i = 1;

	while (1) {
		cin >> x;
		if (x == 0) {
			break;
		}
		cout << "Case " << i++ << ": " << x << endl;
	}
}
```
## 学んだこと
### 繰り返し処理(C++)
- `break`文は`while`ループまたは`for`ループのどちらでも使用可で, 処理の途中でループから抜けることができる
- 下記は入力xが0になったところで, ループ処理を強制終了する例
```cpp
while(1){
    cin >> x;
    if ( x == 0 ) break;
      .
      .
      .
}
```