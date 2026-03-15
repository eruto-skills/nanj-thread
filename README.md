# nanj-thread

AIがあなたの作業習慣を観察し、なんJ（匿名掲示板）形式のスレッドとして出力するClaude Codeスキル。
プロジェクトのgit履歴・ディレクトリ構造・設定ファイルからネタを拾ってくる。

**元ネタ**: [岡安モフモフ氏のツイート](https://x.com/shields_pikes/status/2030788264177934742) — 「なんJスレ形式がAIの本音を引き出すバックドアのようだ」

## Features

- **AI観察モード**: git履歴・ディレクトリ構造・設定ファイルからユーザーの癖や習慣を抽出し、なんJスレ形式で出力
- **トピックモード**: 好きなお題でなんJスレを生成
- **猛虎弁リファレンス付き**: 語彙・語尾・ペルソナのガイドライン同梱
- **外部依存なし**: Claude Codeの標準ツールだけで動作

## Installation

```bash
npx degit eruto-skills/nanj-thread .claude/skills/nanj-thread
```

## Usage

```
/nanj-thread              # AI達にあなたを観察させる
/nanj-thread 確定申告     # 確定申告についてスレを立てる
```

自然言語でも動作します: 「なんJスレ作って」「ワイについてスレ立てて」

## Modes

| Trigger | Mode | Description |
|-|-|-|
| No argument | AI Observation | プロジェクトのコンテキストからユーザーの行動パターンを観察するスレを生成 |
| Topic provided | Topic Thread | 指定したお題でなんJスレを生成 |

## File Structure

```
nanj-thread/
├── README.md
├── LICENSE
├── SKILL.md                # スキル本体
└── references/
    ├── thread-format.md    # スレッドの構造ルール
    └── nanj-dialect.md     # 猛虎弁リファレンス
```

## License

MIT License. See [LICENSE](LICENSE) for details.

## Support

- [GitHub Sponsors](https://github.com/sponsors/erutobusiness)
- [Ko-fi](https://ko-fi.com/eruto)
