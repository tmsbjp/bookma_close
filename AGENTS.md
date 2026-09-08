# AGENTS.md

## ローカル作業データの保存（X9・2026-09-09）

このMacでの保存先は本節を優先する。Git管理するソース・設定・台本・制作スクリプト・必要な配布素材は本体のrepoに置き、Git管理しない大容量の制作物・比較画像・生成物は `/Volumes/X9/Projects/bookma_close/` に置く。

- before/afterスクショ: `/Volumes/X9/Projects/bookma_close/screenshots/YYYY-MM-DD/<task>/`。同じ対象を `<screen>-1-before.png` / `<screen>-2-after.png` で保存し、最終報告には絶対パスを記載する。以下にある旧 `screenshots/` の保存先・当日だけ保持する指示は、この外部保存ルールで置き換える。X9上の記録は無断で削除しない。
- プロモーション動画: `/Volumes/X9/Projects/bookma_close/media/<production>/` に素材・Blenderファイル・レンダー・書き出し動画を保存する。コード、台本、再生成手順、素材一覧はrepo側に残す。公開サイト・アプリのビルドに必要な配布用アセットはGit管理を維持する。
- ビルド生成物・機械ログ・キャッシュ: `/Volumes/X9/Projects/bookma_close/` 以下で用途別に保存する。出力先オプションを優先し、移行済みの互換シンボリックリンクを通常フォルダに置き換えない。Xcodeは `XCODE_DERIVED_DATA_DIR=/Volumes/X9/Projects/bookma_close/cache/DerivedData` と `XCODE_CLONED_SOURCE_PACKAGES_DIR=/Volumes/X9/Projects/bookma_close/cache/SourcePackages` を設定して既存wrapperを使う。wrapperが無い場合は同じ場所をCLIオプションで指定する。
- 作業開始前にX9が実際にマウント済みであることを確認する。未接続時は外部出力を停止し、内蔵へ自動フォールバックしたり `/Volumes/X9` を通常ディレクトリとして作ったりしない。
- 「Git未管理」は移動の十分条件ではない。新規ソース、秘密情報、ローカル設定、稼働中DB、`.git` は一括移動しない。`node_modules` は当面本体に残し、休止repoでは必要時に再生成する。HushChamber用の小さな判断・作業ログもrepoに残す。
- 既存のGit管理ファイルは勝手に追跡解除しない。新規生成物や外部へのリンクはGitに追加しない。移行はコピー・内容照合・参照確認の後に元データを削除する。X9は作業領域であり、再生成できない素材には別のバックアップが必要。
