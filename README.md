# razer-tartarus-v2-for-karabiner
Razer Tartarus V2 for Karabiner-Elements  
  
私はイラストを描く際、左手キーボードとしてRazer Tartarus V2を愛用しています  
ですが、Razer公式で提供しているデバイス(とキーマッピング)管理アプリのSynapse2が長らくメンテされておらず、  
macOSのアップグレードに追従していませんでした  
そこにClipStudioがMojaveのサポートを近々切る通知を出してきたので  
重い腰をあげてSynapse2からKarabiner-Elementsへ移行しました  

## 確認した動作環境

- macOS Monterey 12.4
- Karabiner-Elements 14.4.0

## 前提

- このリポジトリで扱っているrazer_tartarus_v2_for_karabiner.jsonはRazer Tartarus v2を扱う為だけの構成になっています
- Razer Tartarus v2のほぼ全てのボタン(`from`部分)は網羅しています
  - ただしホイールの上下スクロールだけはKarabiner-Elementsが未対応の為、キーマッピングがありません
- 記載されている内容(`to`部分)は全て私の環境のものです。サンプルとしてお使い下さい

## 使い方

1. [Karabiner-Elements](https://karabiner-elements.pqrs.org)をインストールする
2. Preference -> MiscのOpen config folderのボタンをクリックする
3. 開いたフォルダのassets -> complex_modifications へ razer_tartarus_v2_for_karabiner.json を入れる
4. Preference -> Complex modificationsにあるAdd ruleのボタンをクリックする
5. Razer Tartarus v2という名前のruleがあるのを確認する
6. 3のjsonを好きなように修正する
  - descriptionにどこのボタンかを記載してあります
  - 下記の例は`Razer Tartarus V2`の`01のボタン`が押されたら`option と ピリオドを同時押しとして扱う` というのを表しています
  ```
{
  "description": "【key:01】下に転写 (opt + .)",
  "manipulators": [{"conditions": [{"type": "device_if","identifiers": [{"product_id": 555,"vendor_id": 5426}]}],"type": "basic","from":{"key_code":"1"},
    "to":{"key_code":"period","modifiers":["left_option"]}
    }]
}
  ```
  - 他のボタンを参考にするか、必要であればネットで調べた上で`"to":{"key_code":"period","modifiers":["left_option"]}`の部分を好きなように修正すればOKです
7. jsonが出来上がったら再び4、5を行い、全てEnableにします。jsonの構文が間違っている場合は5でruleが確認出来ない筈です。恐らく6の修正で何か誤りがあります
8. Razer Tartarus v2が設定したjsonの通りに動作する筈です。動作しない場合はjsonが誤っていたり、Preference -> DevicesでRazer Tartarus v2のキーボードとマウスが有効化されていない可能性があります

## 謝辞
- [rbradcurtis](https://github.com/rbradcurtis)様
  - [Razer Tartarus v2 Json](https://ke-complex-modifications.pqrs.org/#Razer_Tartarus_v2)
