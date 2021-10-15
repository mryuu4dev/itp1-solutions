## 問題文要旨
- 点数の標準偏差を求めよ
- 複数のデータセット
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, s[1000] = {};
	double sum_dev = 0, avg;
	int i;

	while (1) {
		cin >> n;

		if (n == 0) {
			break;
		}

		for (i = 0; i < n; i++) {
			cin >> s[i];
		}

		// ★ int / intで少数が四捨五入されるのでdoubleにキャストする必要あり
		avg = accumulate(s, s + n, 0) / (double)n;

		for (i = 0; i < n; i++) {
			// 偏差の二乗の和
			sum_dev += pow(s[i] - avg, 2.0);
		}

		cout << fixed << sqrt(sum_dev / n) << endl;

		sum_dev = 0;
	}
}
```
## 学んだこと
### accumulate関数(C++)
- 配列等の指定範囲の要素の合計値を求める
```
accumulate(始点アドレス, 終点アドレス, 総和の初期値);
```