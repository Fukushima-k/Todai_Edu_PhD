# 博士論文テンプレート

このプロジェクトは、博士論文作成のためのLaTeXテンプレートです。

## フォルダ構造

```
2025_PhD_templete/
├── main/                    # メインのLaTeXファイル
│   └── main.tex            # メインの文書ファイル
├── Chap_templete/          # テンプレート章
│   └── templete.tex       # 基本的な章のテンプレート
├── Chap_Examples/          # 利用例章（新規追加）
│   └── Examples.tex       # 参照方法の例示
├── Abst/                   # 要約関連ファイル
│   ├── abst.tex           # 要約ファイル
│   ├── abst_yoyaku.tex    # 予約要約ファイル
│   └── abst_text.tex      # 要約テキスト
├── aux_files/              # 補助ファイル
│   └── bibliography.bib   # 参考文献データベース
└── images/                 # 図表ファイル
    ├── Chap_A/            # 章A用の図表
    │   └── demo_plot.png  # サンプルプロット
    └── Chap_B/            # 章B用の図表
        └── table_postSD_all_informative.tex
```

## 主要な機能

### 1. 章構造の管理
- `main.tex`で全体の構造を管理
- `subfiles`パッケージを使用して章ごとに独立したファイルを作成
- 各章は独立してコンパイル可能

### 2. 参照システム
- `cleveref`パッケージによる自動参照
- 章、節、図、表、式の参照
- 章をまたいだ参照のサポート

### 3. 図表の管理
- 図表の自動番号付け
- サブキャプション対応
- 図表リストの自動生成

### 4. 文献管理
- `biblatex`パッケージによる文献管理
- APA形式の引用スタイル
- 日本語・英語混在対応

## 利用例章（Chap_Examples）

新しく追加された利用例章では、以下の内容を例示しています：

### 参照方法
- `\cref{}`による自動参照
- 複数項目の同時参照
- 章をまたいだ参照

### 図表の挿入
- 基本的な図の挿入
- 表の作成と参照
- サブキャプション付き図
- 複数図の組み合わせ

### 引用方法
- `\citet{}`による著者名付き引用
- `\citep{}`による括弧内引用
- 複数文献の同時引用
- ページ指定付き引用

### 数式の参照
- 基本的な数式の参照
- 連立方程式の参照
- 式と図表の組み合わせ参照

## 使用方法

1. メインファイルのコンパイル：
   ```bash
   cd main
   lualatex main.tex
   biber main
   lualatex main.tex
   lualatex main.tex
   ```

2. 個別の章のコンパイル：
   ```bash
   cd Chap_Examples
   lualatex Examples.tex
   ```

## 注意事項

- 日本語処理には`luatexja`パッケージを使用
- 図表ファイルは`images/`フォルダ内に配置
- 参考文献は`aux_files/bibliography.bib`に追加
- 新しい章を追加する場合は`main.tex`に`\subfile{}`を追加

## カスタマイズ

### 新しい章の追加
1. 新しいフォルダ（例：`Chap_NewChapter/`）を作成
2. 章ファイル（例：`NewChapter.tex`）を作成
3. `main.tex`に`\subfile{../Chap_NewChapter/NewChapter.tex}`を追加

### スタイルの変更
- `main.tex`のプリアンブル部分でパッケージの設定を変更
- 各章ファイルは`\documentclass[../main/main.tex]{subfiles}`で開始

このテンプレートを使用することで、効率的に博士論文を作成できます。
