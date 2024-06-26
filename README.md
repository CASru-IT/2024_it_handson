# IT班体験会
このREADMEを読むことでサイト制作に関する一通りの手順が学べます。
## 目次
### [1_始めに](#1-始めに)
### [2_環境構築](#2-環境構築)
### [3_HTMLについて](#3-HTMLについて)
### [4_CSSについて](#4-CSSについて)
### [5_JavaScriptについて](#5-JavaScriptについて)
### [6_実際にページを作ってみよう](#6-実際にページを作ってみよう)
### [7_作ったページを公開してみよう](#7-作ったページを公開してみよう)
### [8_最後に](#8-最後に)
### [9_補足](#9-補足)
　　
## 1. 始めに
この体験会はHTMLもCSSも触ったことのない完全に初心者に向けたウェブサイト作成チュートリアルとなっています。既にnode.js等のフレームワークを触るくらい習熟しているような方は[補足](#9-補足)の部分だけ見ていただけるとIT班の今の環境が大体わかるのでそちらを参照してください。
## 2. 環境構築
ウェブサイトを作る時、またそれ以外の開発を行う際に主に使われている環境を構築しましょう。IT班では主にVisualStudioCode(以下VScodeと略します)というエディターを利用してコードを書いています。
>[!Note]
エディターとはコードを書くために利用するソフトウェアのことで、基本的にプログラムを書く際はエディターを利用します。<br>エディターにはコーディングを行う際に便利な機能が詰まっています。
### VSCodeのインストールとセットアップ
VScodeのインストールと初期設定の方法を説明します。
1. [このページ](https://code.visualstudio.com/download)を開きwindows用のボタンを押してインストーラをダウンロードします。
2. ダウンロードしたインストーラを実行します。
>[!Note]
「デスクトップ上にアイコンを作成する」にチェックを入れ、途中で出てくる使用許諾契約書は同意してください。<br>それ以外は触らずに次へを押してインストールは完了してください。
3. 拡張機能ボタンをクリックする。
4. 検索欄に"Japanese Language Pack for Visual Studio Code"と入力し出てきたものを選択します。
5. 選択したものをInstallします。
![Image1](/Images/tutorial1.jpg)
6. 3~5までと同じ手順で以下の三つをインストールしてください。
    - HTML CSS Support
        - 機能：CSSファイルにあるクラス定義からHTMLのクラスを入力する際に、自動補完をしてくれる。
    - HTMLHint
        - 機能：HTMLの構文チェックを行ってくれる。
    - Live Server
        - 機能：HTMLとCSSのファイルからプレビューをリアルタイムで表示してくれる。
7. VScodeを再起動してください。これで環境構築は完了です。
>[!Note]
ここまでの手順でインストールしたものは拡張機能と言ってその名の通りVScodeの機能を拡張するものでコードの補完や構文ミスを指摘してくれる機能を付ける等の拡張機能があります。今回提示したもの以外にも様々な拡張機能があるのでぜひ入れてみてください。

## 3. HTMLについて
HTML（HyperText Markup Language）は、ウェブページを作成するための標準的なマークアップ言語です。HTMLを使用して、テキストコンテンツに構造を付けたり、リンク、画像、リスト、テーブルなどの要素をウェブページに追加したりすることができます。

### HTMLの基本構造
HTMLドキュメントは、`<!DOCTYPE html>`で始まり、`<html>`タグで囲まれた中に`<head>`セクションと`<body>`セクションが含まれます。
### 主なHTML要素
- `<h1>`から`<h6>`までの見出しタグ: セクションのタイトルやサブタイトルに使用します。
- `<p>`: 段落を定義します。
- `<a href="URL">`: リンクを作成します。
- `<img src="画像のURL" alt="代替テキスト">`: 画像を挿入します。
- `<ul>`, `<ol>`, `<li>`: 箇条書きリスト（`<ul>`は番号なし、`<ol>`は番号付き）とリスト項目を作成します。
- `<table>`, `<tr>`, `<td>`: テーブルを作成します。

### HTMLページの例
以下はHTMLを使用して簡単なウェブページを作成する例です。
```html
<!DOCTYPE html>
<html>
<head>
<title>私のウェブページ</title>
</head>
<body>
<h1>こんにちは、世界！</h1>
<p>これは私の最初のウェブページです。</p>
<a href="https://www.example.com">Example.comへのリンク</a>
</body>
</html>
```
HTMLはウェブ開発の基礎であり、CSSやJavaScriptと組み合わせることで、より動的でスタイリッシュなウェブサイトを作成することができます。

## 4. CSSについて
CSS（Cascading Style Sheets）は、ウェブページのデザインやレイアウトを指定するために使用されるスタイルシート言語です。HTMLがウェブページの構造を定義するのに対し、CSSはその見た目と感じを定義します。色、フォント、間隔、配置など、ページ上の要素のスタイルを細かく制御できます。

### CSSの基本
CSSをHTMLに適用する方法は主に3つあります。
1. **インラインスタイル**: 直接HTMLタグの中に`style`属性を使用してスタイルを適用します。
2. **内部スタイルシート**: `<head>`セクション内に`<style>`タグを使用してスタイルを定義します。
3. **外部スタイルシート**: CSSを別のファイルに記述し、HTMLファイルからリンクします。

### CSSの例
以下は、CSSを使用してHTML要素のスタイルを定義する簡単な例です。
```css
/* 外部スタイルシートファイル（styles.css） */
body {
background-color: lightblue;
}
h1 {
color: navy;
margin-left: 20px;
}
```
HTMLファイルでの外部スタイルシートのリンク方法：
```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="styles.css">
</head>
<body>
<h1>これは見出しです</h1>
<p>この段落はlightblueの背景色で表示されます。</p>
</body>
</html>
```
### CSSの利点
- **再利用性**: 同じスタイルシートを複数のページで使用でき、一貫したデザインを簡単に実現できます。
- **メンテナンスの容易さ**: スタイルを一箇所で更新するだけで、サイト全体の見た目を変更できます。
- **ページの読み込み時間の短縮**: スタイル情報を外部ファイルに分離することで、HTMLファイルのサイズを小さく保ち、ページの読み込みを高速化できます。

CSSはウェブ開発において不可欠な技術であり、HTMLとJavaScriptと共に、ウェブページの構造、スタイル、動作を定義するために使用されます。
## 5. JavaScriptについて
JavaScriptは、ウェブページに動的な要素を追加するために使用されるプログラミング言語です。HTMLがページの構造を、CSSがスタイルを定義するのに対し、JavaScriptはウェブページの動作を制御します。例えば、ユーザーのアクションに応じてコンテンツを更新したり、インタラクティブなマップを表示したり、アニメーション効果を加えたりすることができます。

### JavaScriptの基本
JavaScriptコードは、HTMLドキュメント内に直接記述することも、外部ファイルとしてリンクすることもできます。直接HTML内に記述する場合は`<script>`タグを使用し、外部ファイルをリンクする場合は`<script src="ファイル名.js">`タグを使用します。

### JavaScriptの例
以下は、ボタンをクリックするとアラートが表示される簡単なJavaScriptの例です。
```html
<!DOCTYPE html>
<html>
<head>
<title>JavaScriptの例</title>
</head>
<body>
<h1>JavaScriptのデモ</h1>
<button onclick="showMessage()">クリックしてね</button>
<script>
function showMessage() {
alert("こんにちは、世界！");
}
</script>
</body>
</html>
```
### JavaScriptを使用する利点
- **インタラクティビティ**: ユーザーの入力やアクションに基づいてコンテンツを動的に変更することができます。
- **リッチなユーザーインターフェース**: ドラッグアンドドロップ機能やスライダーなど、高度なユーザーインターフェースコンポーネントを実装できます。
- **データの検証**: フォーム送信前にクライアントサイドでデータを検証し、ユーザーにフィードバックを提供できます。
- **非同期通信**: Ajaxを使用して、ページの再読み込みなしにサーバーとデータを交換し、ページの一部を更新できます。

JavaScriptは、HTMLとCSSと共にウェブ開発の三大要素とされ、現代のウェブアプリケーション開発において不可欠な技術です。
## 6. 実際にページを作ってみよう
