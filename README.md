# 2022年度アルゴリズムとデータ構造B グループワーク 9班

# サンプルコードの説明

## 配布物について
- `adsb_G9.c`
    - 説明
        - 実際に提出するプログラムの例を示しています。内容は、入力を受け取り、各クエリ1回ずつ聞き直した後 `1〜100` のうちランダムに数字を出力するというものです。
        - 入力の受け取り方や出力方法の参考にしてください。

- `ask.h`
    - 特定のクエリに関して同じ箇所を聞き直す際に用いる関数です。
    - 引数の説明
        - `query_id`
            - $i (1 \leq i \leq 100)$ 番目のクエリについて聞き直したい場合は、`query_id`に $i$ を指定してください。
            - 例: 5番目のクエリについて聞き直したい場合は、`query_id = 5` とする。
        - `answer_filename`
            - クエリに対する正解データ のファイル名（のパス）を指定します。
    - 注意点
        - なお、このヘッダファイルは`constraint.h`、`myrandom.h`、`vector.h`に依存しています。
        - `myrandom.h` は `sys/random.h` を include しているため、例えば macOS などではコンパイル出来ない可能性があります。**提出時の動作確認も含めて、Linux環境で使用することを推奨します**。（Linux環境の準備については、詳しくはスライドを参照してください。）

## 実行について
性能評価を行う際は以下のようなコマンドでコンパイルし、実行されます。（スライド参照）

```bash
$ gcc adsb_G9.c -o run_G9 -lm -O2

$ timeout 10 run_G9 (inputファイル名) (outputファイル名) (answerファイル名)
```

例えば本サンプルプログラムだと、以下のようなコマンドで実行することになります。

例として、`sample` ディレクトリ内に `all` (テストケースが入っているディレクトリ) があり、`sample` ディレクトリ内で 1 つ目のテストケースについてプログラムを実行する場合のコマンドを示します。 

```bash
$ gcc adsb_G9.c -o run_G9 -lm -O2

$ timeout 10 ./run_G9 all/testcase1/idata out.txt all/testcase1/answer

$ /usr/bin/time -v timeout 10 ./run_G9 all/testcase1/idata out.txt all/testcase1/answer
```

この場合、出力は `out.txt` に出力されます。
