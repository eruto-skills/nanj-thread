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

## Codex / Claude Code installation

This package supports both Codex and Claude Code. The plugin entry point is
`skills/nanj-thread/SKILL.md`; the root `SKILL.md` remains the standalone source.

For Codex, add the public `eruto-skills` marketplace in the plugin UI using
`https://github.com/eruto-skills/marketplace`, then install `nanj-thread`.
To install as a standalone user skill instead:

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/eruto-skills/nanj-thread.git ~/.agents/skills/nanj-thread
```

On Windows PowerShell:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE/.agents/skills" | Out-Null
git clone https://github.com/eruto-skills/nanj-thread.git "$env:USERPROFILE/.agents/skills/nanj-thread"
```

In Codex, select the installed skill by name or invoke `$nanj-thread` with a task.
In Claude Code:

```text
/plugin marketplace add eruto-skills/marketplace
/plugin install nanj-thread@eruto-skills
```

The instructions use the tools available in the current host. Scripts are resolved
from the actual skill directory, rather than a fixed author path. Additional browser,
Python, or format-specific dependencies are described in `SKILL.md` and the references;
installing the plugin alone does not install those external programs.

## Maintaining the plugin package

Edit the root `SKILL.md` and its supporting resources, then run:

```bash
node scripts/package-plugin.mjs
node scripts/package-plugin.mjs --check
```

Commit the generated `skills/` files with the source changes. CI checks that both
layouts match, including the Claude manifest. Do not edit generated files directly.
