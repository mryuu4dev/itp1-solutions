## 問題文要旨
- 文字列sに文字列pが含まれるかどうか判定せよ
- 文字列sは, 問題文のようにリング状になっている
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	string s, p;
	
	cin >> s;
	cin >> p;

	if ((s + s).find(p) != string::npos) {
		cout << "Yes" << endl;
	}
	else {
		cout << "No" << endl;
	}
}
```