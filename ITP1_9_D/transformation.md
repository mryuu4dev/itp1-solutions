## 問題文要旨
- 文字列```str```について, 与えられた処理を実行し結果を出力せよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	string str, cmd, p;
	int q, a, b;
	int i;

	cin >> str >> q;

	for (i = 0; i < q; i++) {
		cin >> cmd >> a >> b;

		if (cmd == "print") {
			cout << str.substr(a, b - a + 1) << endl;
		}
		else if (cmd == "reverse") {
			reverse(str.begin() + a, str.end() - ((str.size() - 1) - b));
		}
		else if (cmd == "replace") {
			cin >> p;
			str.replace(a, b - a + 1, p);
		}
	}
}
```
## 学んだこと
### 文字列の関数(C++)
```cpp
// substr関数
string hoge = str.substr(開始文字index, 切り抜く文字列の長さ);
// replace関数
str.replace(開始文字index, 置換する部分文字列の長さ, 置き換える新しい文字列);
```