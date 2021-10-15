## 問題文要旨
- pが1, 2, 3, ∞のとき, ベクトル間のミンコフスキー距離を出力せよ
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	int n, x[100] = {}, y[100] = {};
	double D1 = 0, D2 = 0, D3 = 0, D_inf = 0;
	int i;

	cin >> n;

	for (i = 0; i < n; i++) {
		cin >> x[i];
	}
	for (i = 0; i < n; i++) {
		cin >> y[i];
	}

	for (i = 0; i < n; i++) {
		D1 += abs(x[i] - y[i]);
		
		D2 += pow(abs(x[i] - y[i]), 2.0);

		D3 += pow(abs(x[i] - y[i]), 3.0);

		if (D_inf < abs(x[i] - y[i])) {
			D_inf = abs(x[i] - y[i]);
		}
	}
	D2 = sqrt(D2);
	D3 = pow(D3, 1.0 / 3.0);

	cout << fixed << D1 << endl;
	cout << fixed << D2 << endl;
	cout << fixed << D3 << endl;
	cout << fixed << D_inf << endl;
}
```
## 学んだこと
### ミンコフスキー距離(数学)
「```p```が大きいほど差が大きい成分を重視して, 差が小さい成分を無視する」傾向にある

[![Image from Gyazo](https://i.gyazo.com/50ea8870b7ecff59e096acdc19da68f6.png)](https://gyazo.com/50ea8870b7ecff59e096acdc19da68f6)

- p = 1 のマンハッタン距離は「どの成分も平等に見る」
- p = ∞ のチェビシェフ距離は「差が一番大きい成分以外は完全無視する」
- p = 2 のユークリッド距離はその中間くらい