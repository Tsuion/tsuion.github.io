# VuePressに触れる
2022.5.31

---
さて、私はMisskey(厳密にはGroundpolisというMisskeyの派生)というSNSに参加している。このSNSのすごいところは、syuilo氏という日本人が開発された**オープンソースのプロジェクト**であることだ。  
このプロジェクトの公式ドキュメントサイト、[MisskeyHub](https://misskey-hub.net/)がVuePressで実装されていることを[知り](https://misskey-hub.net/blog/2021-12-01-inside-misskey-hub.html)、使ってみようと思ったのだ。  
本記事では、備忘録としてVuePressの使い方や自分が構築の際迷ったところをまとめていこうと思う。
## インストール
VuePressV1は、簡単なコマンドで秒で構築できる。
```sh
npx create-vuepress-site
```
これで基本的なインストールは完了。続いて、簡易的なビューを表示しよう。
```sh
cd docs
npm install
```
ちょっと時間がかかるので、けなげに待つこと。
```sh
npm run dev
```
これで、簡易的なプレビューが見られる。ちなみに、変更内容を保存していくたびに自動でプレビューを更新してくれる。
## ソースコード
`config.js`下
- logo 左上に画像を置くことができる。
```js
logo: '任意の画像URL',
```
- 下で移動したい
```js
sidebar: {
      '/blog/': [
        {
          title: 'Blog',
          collapsable: false,
          children: [
            '',
            'using-vue',
          ]
        }
      ],
    }
```