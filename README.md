## pnpmを使用したパッケージインストール

このプロジェクトは `pnpm` を前提にしています。
下記のコマンドは`npm ci`と同じくlockファイルを元にパッケージをインストールします。

```bash
pnpm i --frozen-lockfile
```

## tsc と tsx の違い

- `tsc` は TypeScript の「コンパイラ」。`.ts` を `.js` に変換して `dist/` に出力する。
- `tsx` は TypeScript を「直接実行」するランタイム。ビルドせずに `.ts` を実行できる。

使い分けのイメージ:

- 本番や配布向け: `tsc` でビルド → `node dist/*.js` を実行
- 開発や検証: `tsx` でそのまま実行

## 実行方法

### tsc（ビルド）

```bash
pnpm tsc
```

出力された JavaScript を実行:

```bash
node dist/hello-word.js
```

ウォッチモード:

```bash
pnpm tsc:w
```

### tsx（直接実行）

スクリプトは実行時にオプション(`--`)の後に実行したいファイルまでのパスを記述してください。

#### 実行

**スクリプト経由で実行**

```bash
pnpm tsx -- src/hello-word.ts
```

**直接実行**

```bash
pnpm exec tsx src/hello-word.ts
```

#### ウォッチモード

**スクリプト経由で実行**

```bash
pnpm tsx:w -- src/hello-word.ts
```

**直接実行**

```bash
pnpm exec tsx watch src/hello-word.ts
```
