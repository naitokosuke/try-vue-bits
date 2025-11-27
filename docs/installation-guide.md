# Vue Bits インストールガイド

Vue Bits は、アニメーション豊かな Vue コンポーネントのオープンソースコレクションです。

公式サイト: https://vue-bits.dev/

## jsrepo バージョンについて

2025 年 11 月 27 日時点で、Vue Bits は jsrepo v2.x 系のみ対応しています。
v3 には対応していません。

## 前提条件

Vue Bits のコンポーネントは Tailwind CSS を使用しています。コンポーネントをインストールする前に、プロジェクトに Tailwind CSS をセットアップしてください。

```bash
ni -D tailwindcss @tailwindcss/vite
```

`vite.config.ts` に Tailwind プラグインを追加します。

```ts
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

CSS ファイル（例: `src/styles.css`）に Tailwind をインポートします。

```css
@import "tailwindcss";
```

## インストール方法

### コマンド形式

```bash
npx jsrepo@2.5.2 add https://vue-bits.dev/ui/<Category>/<ComponentName>
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
npx jsrepo@2.5.2 add https://vue-bits.dev/ui/Components/SpotlightCard
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

Yes を選択します。ウォーターマークは、コンポーネントファイルの先頭に jsrepo による自動生成コメントを追加する機能です。どのようなコメントが追加されるか確認するために Yes を選択します。

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
    └── Components/
        └── SpotlightCard/
            └── SpotlightCard.vue
```

jsrepo はカテゴリとコンポーネント名でディレクトリをネストして作成します。

## 依存関係のあるコンポーネント

一部のコンポーネントは外部ライブラリを必要とします。インストール時に依存関係のインストールを確認されるので、Yes を選択してください。

```
◆  Would you like to install dependencies?
│  ● Yes / ○ No
```

Yes を選択すると、必要なパッケージが自動的にインストールされます。

### Three.js（three）

```bash
npx jsrepo@2.5.2 add Animations/GhostCursor
```

### GSAP（gsap）

```bash
npx jsrepo@2.5.2 add Animations/AnimatedContent
```

### OGL（ogl）

```bash
npx jsrepo@2.5.2 add Backgrounds/Iridescence
```

## Full CLI Setup

上記の手順では、コンポーネントをインストールするたびに初期化確認が表示されます。

Vue Bits 公式ドキュメント（https://vue-bits.dev/）の「Full CLI Setup」に記載されている方法を使うと、プロジェクト全体で jsrepo を設定でき、この確認を省略できます。

### jsrepo の初期化

#### コマンド実行

```bash
npx jsrepo@2.5.2 init https://vue-bits.dev/ui
```

#### デフォルトインストールパスの指定

```
┌   jsrepo  v2.5.2
│
◆  Please enter a default path to install the blocks
│  ./src/blocks
```

`./src/components` と入力します。コンポーネントを配置するデフォルトパスを指定します。

#### フォーマッターの選択

```
◇  Please enter a default path to install the blocks
│  ./src/components
│
◇  Which formatter would you like to use?
│  None
```

None を選択します。

#### 認証トークンの追加

```
●  Initializing https://vue-bits.dev/ui
│
◆  Would you like to add an auth token?
│  ○ Yes / ● No
```

No を選択します。Vue Bits は公開リポジトリなので認証トークンは不要です。

#### カテゴリパスの設定

```
◆  Which category paths would you like to configure?
│  ◻ Animations
│  ◻ Backgrounds
│  ◻ Components
│  ◻ TextAnimations
```

何も選択せずにそのまま Enter を押します。カテゴリごとに個別のパスを設定する必要はありません。

#### 追加リポジトリの設定

```
◆  Add another repo?
│  ○ Yes / ● No
```

No を選択します。Vue Bits のみを使用するため、他のリポジトリを追加する必要はありません。

#### 完了

jsrepo.json が作成されます。この設定により、以降のコンポーネントインストール時に初期化確認が表示されなくなります。

### コンポーネント一覧から選択

```bash
npx jsrepo@2.5.2 add
```

コマンドを実行すると、利用可能なコンポーネントの一覧が表示されます。

```
┌   jsrepo  v2.5.2
│
◇  Retrieved blocks from https://vue-bits.dev/ui
│
◆  Select which blocks to add.
│  ◻ Animations/AnimatedContent
│  ◻ Animations/BlobCursor
│  ◻ Animations/ClickSpark
│  ◻ Animations/CountUp
...
```

インタラクティブにコンポーネント一覧から選択できます。

### 特定のコンポーネントを直接指定

```bash
npx jsrepo@2.5.2 add TextAnimations/ShinyText
```

コンポーネント名を直接指定してインストールできます。

## 今後を見据えたコンポーネント管理

コンポーネントが増えていくと、以下のようなインポートが煩雑になります。

```ts
import SpotlightCard from './components/Components/SpotlightCard/SpotlightCard.vue'
import GradientText from './components/TextAnimations/GradientText/GradientText.vue'
import CountUp from './components/Animations/CountUp/CountUp.vue'
// コンポーネントが増えるたびに長いパスを書く必要がある...
```

これを解決するため、Vue Bits のコンポーネントを専用ディレクトリにまとめ、`index.ts` から一括エクスポートする構成にします。

### ディレクトリ構成

```
src/
└── components/
    └── vue-bits/
        ├── index.ts
        ├── Components/
        │   └── SpotlightCard/
        │       └── SpotlightCard.vue
        └── TextAnimations/
            └── GradientText/
                └── GradientText.vue
```

- Vue Bits のコンポーネントとプロジェクト独自のコンポーネントを明確に分離できる
- `index.ts` から1行でまとめてインポートできる
- コンポーネントの追加・削除時に影響範囲が限定される

### jsrepo.json の設定変更

`jsrepo.json` の `paths` を更新して、コンポーネントが `vue-bits` ディレクトリにインストールされるようにします。

```json
{
  "paths": {
    "*": "./src/components/vue-bits"
  }
}
```

### index.ts の作成

`src/components/vue-bits/index.ts` を作成し、全コンポーネントをエクスポートします。

```ts
export { default as SpotlightCard } from './Components/SpotlightCard/SpotlightCard.vue'
export { default as GradientText } from './TextAnimations/GradientText/GradientText.vue'
```

コンポーネントを追加するたびに、このファイルにエクスポートを追加します。

### 使用方法

```vue
<script setup lang="ts">
import { SpotlightCard, GradientText } from './components/vue-bits'
</script>
```

1行で複数のコンポーネントをインポートできるようになります。
