# C++ 中級者向け問題集

## 1. 基本的なアルゴリズムとデータ構造

### 問題 1: 配列の最大値・最小値
整数の配列が与えられたとき、最大値と最小値を求める関数を実装してください。

```cpp
int findMax(const std::vector<int>& arr);
int findMin(const std::vector<int>& arr);
```

### 問題 2: 二分探索
ソートされた配列とターゲットの整数が与えられたとき、二分探索を用いてその要素のインデックスを返す関数を実装してください。

```cpp
int binarySearch(const std::vector<int>& arr, int target);
```

### 問題 3: 連結リストの逆転
単方向リストを逆順にする関数を実装してください。

```cpp
struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* reverseList(ListNode* head);
```

---

## 2. メモリ管理とポインタ

### 問題 4: スマートポインタの利用
`std::unique_ptr` を用いて動的配列を管理するクラスを作成してください。

```cpp
class SmartArray {
public:
    SmartArray(size_t size);
    int& operator[](size_t index);
    size_t size() const;
private:
    std::unique_ptr<int[]> data;
    size_t arraySize;
};
```

### 問題 5: 参照カウント付きポインタ
`std::shared_ptr` を使って、複数のオブジェクトで共有されるリソースを管理してください。

```cpp
class Resource {
public:
    Resource(int id);
    void show() const;
};

void sharedPointerDemo();
```

---

## 3. STL（標準テンプレートライブラリ）

### 問題 6: マップの活用
`std::map` を用いて文字列の出現回数をカウントする関数を作成してください。

```cpp
std::map<std::string, int> wordFrequency(const std::vector<std::string>& words);
```

### 問題 7: 優先度付きキュー（ヒープ）
整数のリストから上位N個の最大値を求める関数を `std::priority_queue` を使って実装してください。

```cpp
std::vector<int> topNElements(const std::vector<int>& arr, int N);
```

---

## 4. 並行処理とマルチスレッド

### 問題 8: マルチスレッドでの計算
複数のスレッドを用いて、配列内の値の合計を計算するプログラムを作成してください。

```cpp
int parallelSum(const std::vector<int>& arr, int numThreads);
```

### 問題 9: ミューテックスによる同期
`std::mutex` を使ってスレッドセーフなカウンタを作成してください。

```cpp
class ThreadSafeCounter {
public:
    void increment();
    int get() const;
private:
    int count = 0;
    std::mutex mtx;
};
```

---

## 5. テンプレートと高度なC++機能

### 問題 10: 汎用的な最大値関数
テンプレートを使用して、異なる型の値に対応する `max` 関数を実装してください。

```cpp
template <typename T>
T myMax(T a, T b);
```

### 問題 11: コンパイル時計算
テンプレートメタプログラミングを用いてコンパイル時にフィボナッチ数列を計算するクラスを作成してください。

```cpp
template<int N>
struct Fibonacci {
    static constexpr int value = Fibonacci<N-1>::value + Fibonacci<N-2>::value;
};

template<>
struct Fibonacci<0> {
    static constexpr int value = 0;
};

template<>
struct Fibonacci<1> {
    static constexpr int value = 1;
};
```

---

## 6. 例外処理とエラーハンドリング

### 問題 12: 例外を投げる関数
負の数が入力された場合に例外を投げる関数を作成してください。

```cpp
int factorial(int n);
```

### 問題 13: ユーザー定義の例外クラス
カスタム例外クラス `InvalidAgeException` を作成し、年齢が負の値のときに例外をスローしてください。

```cpp
class InvalidAgeException : public std::exception {
public:
    const char* what() const noexcept override;
};
```

---

## 7. ファイル入出力

### 問題 14: ファイルからの単語カウント
テキストファイルを読み込み、各単語の出現回数をカウントするプログラムを作成してください。

```cpp
std::map<std::string, int> countWordsFromFile(const std::string& filename);
```

### 問題 15: バイナリファイルの読み書き
整数のリストをバイナリファイルに書き込み、再び読み込む関数を実装してください。

```cpp
void writeBinaryFile(const std::string& filename, const std::vector<int>& data);
std::vector<int> readBinaryFile(const std::string& filename);
```

---

## 8. クラス設計とオブジェクト指向

### 問題 16: 継承と多態性
`Shape` クラスを基底クラスとして、`Circle` と `Rectangle` を派生クラスとして作成し、それぞれの `area()` 関数を実装してください。

```cpp
class Shape {
public:
    virtual double area() const = 0;
    virtual ~Shape() {}
};

class Circle : public Shape {
    // 実装
};

class Rectangle : public Shape {
    // 実装
};
```

---

これらの問題を解くことで、中級者レベルのC++のスキルをしっかりと身につけることができます。

