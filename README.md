# release-please-monorepo-sample

[release-please](https://github.com/googleapis/release-please) のモノレポ対応サンプルリポジトリです。

## Structure

ディレクトリ単位でリリース対象が存在し、それぞれ独立したバージョニングを行います。

| Directory | Tag Format | Description |
|-----------|------------|-------------|
| `targetA/` | `targetA/vx.y.z` | リリース対象 A |
| `targetB/` | `targetB/vx.y.z` | リリース対象 B |

## How it works

1. `main` ブランチへの push 時に release-please-action が実行される
2. [Conventional Commits](https://www.conventionalcommits.org/) に基づいてバージョンを自動決定
3. 各パッケージごとに独立したリリース用 Pull Request を作成
4. リリース PR のマージ時に GitHub Release とタグが作成される

## Configuration

- `release-please-config.json`: リリース対象パッケージの設定
- `.release-please-manifest.json`: 各パッケージの現在のバージョンを管理
- `separate-pull-requests: true` により、パッケージごとに個別のリリース PR が作成されます
- `tag-separator: "/"` により、`targetA/v0.1.0` のようなスラッシュ区切りのタグが生成されます
