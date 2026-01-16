# Repository Guidelines

このドキュメントはリポジトリの参加者向けガイドです。Android Javaテンプレートとしての作業を迅速に始めるため、構成と基本ルールをまとめます。

## プロジェクト構成とモジュール
- ルートは Gradle Kotlin DSL 構成で、`settings.gradle.kts`と`build.gradle.kts`が入口。
- アプリ本体は単一モジュール `app/`。Javaソースは `app/src/main/java/jp/ac/jec/cm0199/jecandroidjavatemplate/`。
- リソースは `app/src/main/res/`、マニフェストは `app/src/main/AndroidManifest.xml`。
- 共有設定は `gradle/`と`gradle/libs.versions.toml`で管理。

## ビルド・テスト・開発コマンド
- `./gradlew assembleDebug` : デバッグAPKを生成。
- `./gradlew assembleRelease` : リリースAPKを生成（minifyは無効）。
- `./gradlew installDebug` : 接続端末にインストール。
- `./gradlew test` : JVMユニットテスト（JUnit4）。
- `./gradlew connectedAndroidTest` : 実機 / エミュレータ向け 計測テスト。
- `./gradlew lint` : Android Lintを実行。

## コーディング規約と命名
- Java 11を前提。インデントは4 スペース、タブ禁止。
- クラス は PascalCase、メソッド/変数はlowerCamelCase。
- リソース名はlower_snake_case。例:`activity_main.xml`,`@+id/btn_submit`。
- 画面実装は View Systemを採用する。
- レイアウトはConstraintLayoutを避け、必要に応じてLinearLayoutなどを使用する。
- ロジックも含めて処理はActivityにまとめる。
- ダークテーマは非対応。

## 設定・環境
- `local.properties`はSDKパス用。個人環境の値は共有しない。
- 依存バージョン変更は影響範囲を記録し、`gradle/libs.versions.toml`を更新。

## ドキュメント
- `README.md` : プロジェクト概要とセットアップ手順。
- `SPEC.md` : アプリ仕様書。画面一覧と技術仕様を記載。
- `TUTORIAL.md` : 授業用テキスト。Android アプリ開発入門の解説と演習問題。
