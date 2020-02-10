# ヒラマサ用コーディング規約

原則、[PSR-2](http://www.infiniteloop.co.jp/docs/psr/psr-2-coding-style-guide.html)に準拠します。まずはPSR-2を軽く読んでください。

## 細かいルール

### プロジェクト構成

(課題クリア後に追記)

### 命名規則

a, b, tmpといった変数名は使わない。英語であっても他の人がパッと意味を連想できない名前に関しては、英語ではなくてローマ字表記でもよい。

#### 参考記事

- https://qiita.com/KeithYokoma/items/2193cf79ba76563e3db6
- https://qiita.com/yskszk/items/5a7f99c974773f03a82a
- https://qiita.com/Ted-HM/items/7dde25dcffae4cdc7923

### コーディングスタイル

#### コメント

- 関数には必ずコメントをつけるようにする。

### 禁止事項

- env()はconfig以外では使わないようにする。本番環境ではenv()の中身が空になるため。
- デバッグ時のコード(Log等)は必ず消すようにする。どうしても必要な場合は、コメントに残す。

### 制限事項

- 三項演算子は中の式が複雑になるようなら使用しない。

### 推奨事項

- 関数内の引数、返り値には型を宣言するようにする。

```php:Person.php
<?php

class Person
{

    const ADULT_AGE = 20;

    // 引数に型を指定する
    public function getProfile(string $name, int $age): string # 返り値にもどんな型を想定しているか記載する
    {
        return $name . 'は' . $age .'歳です。';
    }

    public function isAdult(int $age): bool
    {
        return $age >= self::ADULT_AGE;
    }
}



```

## 環境構築について

環境構築は[こちら](build.md)を参照
