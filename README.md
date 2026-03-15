# nanj-thread

**【朗報】Claude Code、ワイらの本音を暴露するスキルが爆誕**

AI達が匿名掲示板（なんJ風）に集まって、お前の作業習慣をネタにするスレを立てるスキルや。
プロジェクトのgit履歴やディレクトリ構造を読み取って、「こいつ深夜3時にREADME直してて草」みたいな観察を猛虎弁で吐き出すで。

## 何ができるんや

- **AI観察モード**: お前に仕えてるAI達が匿名で集まって、お前の癖・習慣・こだわりをネタにするスレを生成する
- **トピックモード**: 好きなお題でなんJスレを生成する
- **猛虎弁完備**: 「ワイ」「ニキ」「草」「ファッ!?」など本格的ななんJ語彙リファレンス付き
- **依存なし**: Claude Codeの標準ツールだけで動く。npm installもpip installもいらん

## インストール

```bash
# クローンするんや
git clone https://github.com/eruto-skills/nanj-thread.git

# プロジェクトの .claude/skills/ にコピーや
cp -r nanj-thread /path/to/your-project/.claude/skills/nanj-thread
```

これだけや。依存パッケージ？ そんなものはない。

## 使い方

### スラッシュコマンド

```
/nanj-thread              ← AI達にお前を観察させる
/nanj-thread 確定申告     ← 確定申告についてスレを立てる
```

### 自然言語でもいける

- 「なんJスレ作って」
- 「ワイについてスレ立てて」
- 「AI観察スレ見せて」
- 「git rebaseについてなんJスレ」

## モード一覧

| トリガー | モード | やること |
|-|-|-|
| 引数なし | AI観察 | お前の行動パターンをAI達が匿名で議論する |
| トピック指定 | トピック | 指定したお題でなんJスレを生成する |

## AI観察モードの仕組み

1. プロジェクトの構成ファイル、git履歴、ディレクトリ構造を読み取る
2. お前の癖やパターンを特定する（深夜コミット、ジャンル迷子、命名規則のこだわり等）
3. 複数のAIペルソナが匿名掲示板形式で観察結果を語り合うスレを生成する

**元ネタ**: [岡安モフモフ氏のツイート](https://x.com/shields_pikes/status/2030788264177934742) — 「なんJスレ形式がAIの本音を引き出すバックドアのようだ」

## ファイル構成

```
nanj-thread/
├── README.md              ← イマココ
├── LICENSE                 ← MIT（自由に使ってクレメンス）
├── SKILL.md                ← スキル本体
└── references/
    ├── thread-format.md    ← スレッドの構造ルール
    └── nanj-dialect.md     ← 猛虎弁リファレンス
```

## ライセンス

MIT License。好きに使え。詳しくは [LICENSE](LICENSE) を見てクレメンス。

## サポート

このスキルが気に入ったら応援してくれると助かるで:

- [GitHub Sponsors](https://github.com/sponsors/erutobusiness)
- [Ko-fi](https://ko-fi.com/eruto)
