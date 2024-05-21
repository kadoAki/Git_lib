# PowerShell

## vscodeで書く際の注意
* powershellで文字列をvscodeを使って書くとき、文字コードのアンマッチで文字化けを起こす。
* その際にダブルクォーテーションやシングルクォートが意図した位置からずれることがある
* 対処法は右下のUTF-8等の文字コードをクリックし、"エンコード付きで保存" -> "UTF-8 with BOM"を選択すると直る

## インタラクティブシェル

### プログラムの実行
* スクリプトやアプリをpowershellで実行するときのコマンド
```powershell
# argumentsは引数なので実行するコマンドに合わせて変えること

# 通常
program.exe arguments
ScriptName.ps1 arguments
BatchFile.cmd arguments

# 名前にスペースがあるとき
&'C:\Program Files\Program.exe' arguments

# 名前にスペースが含まれるコマンドをカレントディレクトリから実行するとき
&'.\Program with spaces.exe' arguments

```

* cmd.exeでは、スペースが含まれるコマンドを実行する際はダブルクォートで囲むがpowershellだと式を評価することになる
```powershell
PS >"Hello" + " World"
Hello World
PS >"C:\Program Files\Program.exe"
"C:\Program Files\Program.exe"
```

* カレントディレクトリからプログラムを実行することを明示するのが基本。
* システム上の悪意を持つユーザーは正規ユーザーが該当ディレクトリへの移動時に打ち込むコマンドと同様の名前である邪悪なプログラムを使うことを防ぐ



