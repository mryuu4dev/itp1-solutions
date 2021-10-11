## 問題文要旨
- 各桁の合計値を出力せよ
- 1000桁以下の整数
- データセット
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	string x;
	int sum = 0;
	int i;

	while (1) {
		cin >> x;
		if (x == "0") { 
			break; 
		}
		for (i = 0; i < x.size(); i++) {
			sum += x[i] - '0';
		}
		cout << sum << endl;
		sum = 0;
	}
}
```
## 学んだこと
### 文字列の入出力
- `cin`は空白・タブ・改行区切りで, 読み込める
    - 下記のような複数の空白・タブ・改行が入っていてもOK
    ```cmd
    // 入力ここから
    5
    red   bule yello

    pink
            green
    // 入力ここまで
    ```
- `string`クラスの`length()`と`size()`の違いはない??

## 注意
- 1000桁以下つまり, 10^99以下なので, string型を用いる