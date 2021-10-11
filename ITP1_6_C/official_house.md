## 問題文要旨
- 公舎(3階建て, 10部屋)が4棟ある. 各部屋の入居者数を出力せよ
- 入力: n件のデータ(b棟, r階, r番目の部屋, v人が追加で入居)
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n;
    int b, f, r, v;
    int cnt[4][3][10] = {};
    int i, j, k;

    cin >> n;

    for (i = 0; i < n; i++) {
        cin >> b >> f >> r >> v;
        cnt[b - 1][f - 1][r - 1] += v;
    }

    for (i = 0; i < 4; i++) {
        for (j = 0; j < 3; j++) {
            for (k = 0; k < 10; k++) {
                cout << " " << cnt[i][j][k];
            }
            cout << endl;
        }
        if (i != 3) {
            cout << "####################" << endl;
        }   
    }
}
```
## 学んだこと
### 解き方
- 配列cntを下記のように置くとよい
- 二次元配列で実現しようとして, コードが長くなってしまったorz
```cpp
int cnt[棟数][階数][部屋数] = {};
```