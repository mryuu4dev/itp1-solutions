## 問題文要旨
- 三角形の2辺とその間の角から, 面積, 周, 高さを出力せよ
- 0.0001以下の誤差は許容
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
	const double PI = acos(-1);
	int a, b, C;	
	double S, c, L, h;

	cin >> a >> b >> C;

	// sinを用いた面積の公式 (1 / 2 * a * b * sinC)
	S = (a * b) / 2 * sin(C * PI / 180);

	// 余弦定理 (c = a^2 + b^2 - 2 * a * b * cosC)
	c = sqrt(pow(a, 2.0) + pow(b, 2.0) - 2 * (double)a * b * cos(C * PI / 180));

	L = (double)a + b + c;

	h = 2 * S / a;

	cout << fixed << S << endl;
	cout << fixed << L << endl;
	cout << fixed << h << endl;
}
```
## 学んだこと
### 度からラジアンへの変換(数学)
- ```2πラジアン = 360°```より変換を行う
- ```rad = 変換したい角度(°) * π / 180```となる

### πの算出方法(C++)
- ```cos(π) = -1```より```π = acos(-1)```となる.
- したがって逆余弦関数```acos(-1)```より算出

### 余弦定理(数学)
- 三角形の外周を余弦定理を用いて求めることができる
<img src="https://juken-mikata.sakura.ne.jp/wp-content/uploads/2015/08/17cb28e7db57bc0881da03e544ef89db.png" width="360">

### sinを使って三角形の面積を求める(数学)
- 2辺とその間の角を使って面積を求めることができる
<img src="https://analytics-notty.tech/wp-content/uploads/2018/09/%E4%B8%89%E8%A7%92%E5%BD%A2%E3%81%AE%E9%9D%A2%E7%A9%8D_sin%E5%85%AC%E5%BC%8F%E5%AF%BE%E5%BF%9C.jpg" width="320">