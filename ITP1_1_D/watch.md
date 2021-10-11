## 問題文要旨
- 秒単位時間を"時:分:秒"の形に変換し出力せよ
- ゼロ埋めによる2桁表示は必要ない
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int S;
	int h, m, s;
	int diff;

	cin >> S;

	h = S / 3600;
	diff = S - (3600 * h);

	m = diff / 60;
	
	s = diff - (60 * m);

	cout << h << ":" << m << ":" << s << endl;
}
```
## 学んだこと
### 演算子(C++)
- 計算式`y = 2*x + 3`の場合, `y`, `2`, `X`, `3`が**オペランド**, `=`, `*`, `+`が**演算子**という
- `+=`のように, 演算と代入を一つにまとめた演算子のことを複合代入演算子という