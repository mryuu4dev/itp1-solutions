## 問題文要旨
- 足りないカードを出力せよ
- トランプ(S, H, C, D, それぞれ13枚)は, 全52枚
## 解答例
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    /* 入力ここから */
    int n, value;
    char pic;
    int cards[4][13] = {};
    /* 入力ここまで */
    char pics[4] = { 'S', 'H', 'C', 'D' };
    int i, j;

    cin >> n;

    for (i = 0; i < n; i++) {
        cin >> pic >> value;
        // picと同じ要素をもつpicsのindexを取得
        int pic2num = distance(pics, find(pics, pics + 4, pic));
        cards[pic2num][value - 1] = 1;
    }

    for (i = 0; i < 4; i++) {
        for (j = 0; j < 13; j++) {
            if (cards[i][j] == 0) {
                cout << pics[i] << " " << j + 1 << endl;
            }
        }
    }
}
```
## 学んだこと
### 多次元配列の宣言(C++)
- 2次元配列の宣言
    ```
    型 配列変数名[縦方向のサイズ][横方向のサイズ];
    ```
### 配列, 要素検索(C++)
```cpp
int pic2num = distance(pics, find(pics, pics + 4, pic));
```
- 配列picsからpicという要素のインデックスを検索する方法
    - 配列picsの中からpicと同じ要素を見つける
    - その要素とpicsの0番目の要素との距離を出す
### 文字の読み込みで`scanf()`を使う場合(C)
- 文字を`scanf()`で読み込む場合は, 変換指定子`%c`を用いる
    - `%c`は, **空白も改行も読み込んでしまう**ため, 連続して読み込む場合には注意が必要
        ```c
        /* Cのコード */
        scanf("%d", &n);
        for(i = 1; i <= n; i++){
            scanf("%c", &ch); /* 前の行の改行を１つ読み込む*/
            scanf("%c %d", &ch, &x); /* i行目の、文字と整数の組を読み込む*/
            /* ... */
        }
        ```
        ```cpp
        /* C++のコード */
        cin >> n;
        for(i = 1; i <= n; i++){
            cin >> ch >> x; // cin は空白改行を読み飛ばします
            // ...
        }
        ```