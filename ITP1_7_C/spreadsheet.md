## 問題文要旨
- 表の行ごとの合計値, 列ごとの合計値を含めた表を出力せよ
- 入力: `r`行, `c`列の表
- 出力: `r + 1`行, `c + 1`列の表
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int r, c;
	int ss[100][100] = {};
	int sum = 0, last_elem = 0;
	int i, j;

	cin >> r >> c;

	for (i = 0; i < r; i++) {
		for (j = 0; j < c; j++) {
			cin >> ss[i][j];
		}
	}

	// 最後の行以外の描画
	for (i = 0; i < r; i++) {
		for (j = 0; j < c; j++) {
			cout << ss[i][j] << " ";
			sum += ss[i][j];
		}
		last_elem += sum;

		cout << sum << endl;
		sum = 0;
	}

	// 最後の行の描画
	for (i = 0; i < c; i++) {
		for (j = 0; j < r; j++) {
			sum += ss[j][i];
		}
		cout << sum << " ";
		sum = 0;
		if (i == c - 1) {
			cout << last_elem << endl;
		}
	}
}
```
