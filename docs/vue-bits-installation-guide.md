# Vue Bits インストールガイド

Vue Bitsは、アニメーション豊かなVueコンポーネントのオープンソースコレクションです。

公式サイト: https://vue-bits.dev/

## インストール方法

### コマンド形式

```bash
npx jsrepo add https://vue-bits.dev/ui/<Category>/<ComponentName>
```

カテゴリは以下の4つです。

- TextAnimations
- Animations
- Components
- Backgrounds

### 初回インストール時の手順

SpotlightCard コンポーネントをインストールする例です。

#### コマンド実行

```bash
npx jsrepo add https://vue-bits.dev/ui/Components/SpotlightCard
```

#### jsrepo 初期化の確認

```
◇  You don't have jsrepo initialized in your project. Do you want to continue?
│  Yes
```

Yes を選択します。

#### ブロック取得の完了

```
◇  Retrieved blocks from https://vue-bits.dev/ui/
```

ブロックの取得が完了すると表示されます。

#### インストール先の指定

```
◆  Where would you like to add Components?
```

`./src/components` と入力します。

#### テストファイルの要否

```
◆  Include tests?
│  ○ Yes / ● No
```

今回は No を選択します。テストファイルには、コンポーネントの動作確認用のサンプルコードが含まれています。学習目的であれば Yes を選択してテストファイルを確認することもできます。

#### ウォーターマークの追加

```
◆  Add watermark?
│  ● Yes / ○ No
```

Yes を選択します。ウォーターマークは、コンポーネントファイルの先頭に jsrepo による自動生成コメントを追加する機能です。
どのようなコメントが追加されるか確認するために Yes を選択します。

#### フォーマッターの選択

```
◆  What formatter would you like to use?
│  ○ Prettier
│  ○ Biome
│  ● None
```

None を選択します。今回はフォーマッターを使用しません。

#### 完了メッセージ

```
◇  What formatter would you like to use?
│  None
│
◇  Added blocks Components/SpotlightCard
│
└  All done!
```

インストールが完了しました。

### インストール完了

指定したディレクトリにコンポーネントファイルが作成されます。

```
src/
└── components/
    └── SpotlightCard.vue
```
