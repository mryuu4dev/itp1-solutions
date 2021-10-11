## 問題文要旨
- 文字列を並び替えて出力せよ
- 詳細は問題文
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	string str;
	int m, h;
	string str_diff;
	int i;

	while (1) {
		cin >> str;
		if (str == "-") {
			break;
		}

		cin >> m;

		for (i = 0; i < m; i++) {
			cin >> h;
			str_diff = str.substr(0, h);
			str.replace(0, h, "");
			str += str_diff;
		}
		cout << str << endl;
	}	
}
```
## 学んだこと
### 部分文字列(C++)
- 文字列から部分文字列を取り出したいときは, `substr()`を使う
    - `numbers.substr(3, 5) // 要素3から5文字分の部分文字列を返す`
- 指定した位置の文字列を置き換えたいときは, `replace()`を使う
    - `numbers.substr(3, 5, "") // 要素3から5文字分の部分文字列を削除する`