# Python_Scrape

pythonでスクレイピングをすぐに始めたい時に使えるリポジトリ。  
powershellのスクリプトで環境を整える。 
[Beautiful Soup - 日本語ドキュメント](http://kondou.com/BS4/)

## 環境と仕様
- OS  
    - windows10
- 使用するライブラリ  
    - requests          （リクエスト、レスポンスを簡単に行う）  
    - beautifulsoup4    （スクレイピングを行う）  
    - jupyter           （pythonをweb上で簡単に実行する）  
    - selenium          （プログラムでブラウザ操作をおこなう）  
    - reppy             （robots.txtからルールの取得を行う）  
    **※詳しくは「[requirements.txt](./requirements.txt)」を参照。**   
- [setup.ps1](./setup.ps1)について
    - 仮想環境の作成、起動、再起動
    - requirements.txtのバックアップ出力
    - pythonライブラリのインストール
    - jupiterの起動を行う

## 事前準備（windows10-64bitの場合）

- python3.8がインストールされていること  
⇒未インストールの場合は下記手順でインストールを行う  
    - [Python 公式 サイト](https://www.python.org/)にアクセスし、メニューの「Download」から「windows」を選択する。  
    - 「 Windows x86-64 executable installer」をクリックして、インストーラーをダウンロードする。  
    - インストーラーを起動し、「Add Python3.8 to PATH」にチェックをいれ、「install now」をクリックする。  
    - cmdから「python --version」でインストールされているか確認する。  
    （pythonのバージョン情報が表示されていれば成功）  
- （必須ではないが）powershell core、またはpowershellの文字コード設定がUTF8に設定されていること  
※windowsに初めからインストールされているpowershellだとスクリプトのメッセージが文字化けするかも...  
⇒[powershell coreのインストール方法](https://docs.microsoft.com/ja-jp/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.2)
  

## 使い方（リポジトリ）

リポジトリをクローンし、[setup.ps1](./setup.ps1)を実行すると、  
ローカルサーバーでスクレイピング環境が整った状態のjupyter-notebookが起動する。  
Let's Scrape

## 不具合等について

### setup.ps1でreppyのインストール時にエラーが出る場合
下記のようなエラーが表示されるので、[ここからVisual Studioのコミュニティ版](https://visualstudio.microsoft.com/downloads/)をインストールし、再度setup.ps1を実行してください。  
（Visual StudioはIDEとして必要ではありませんが、同時にインストールされるツールキットが必要です）  
```ps1
    ERROR: Command errored out with exit status 1:
    command: 'c:\users\username\desktop\個人フォルダ\dev\python\python_scrape\.venv\scripts\python.exe' -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\username\\AppData\\Local\\Temp\\pip-install-evhv9026\\reppy\\setup.py'"'"'; __file__='"'"'C:\\Users\\username\\AppData\\Local\\Temp\\pip-install-evhv9026\\reppy\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' install --record 'C:\Users\username\AppData\Local\Temp\pip-record-kia5d9pl\install-record.txt' --single-version-externally-managed --compile --install-headers 'c:\users\username\desktop\個人フォルダ\dev\python\python_scrape\.venv\include\site\python3.8\reppy'
        cwd: C:\Users\username\AppData\Local\Temp\pip-install-evhv9026\reppy\
    Complete output (17 lines):
    Building from C++
    running install
    running build
    running build_py
    creating build
    creating build\lib.win-amd64-3.8
    creating build\lib.win-amd64-3.8\reppy
    copying reppy\exceptions.py -> build\lib.win-amd64-3.8\reppy
    copying reppy\ttl.py -> build\lib.win-amd64-3.8\reppy
    copying reppy\util.py -> build\lib.win-amd64-3.8\reppy
    copying reppy\__init__.py -> build\lib.win-amd64-3.8\reppy
    creating build\lib.win-amd64-3.8\reppy\cache
    copying reppy\cache\policy.py -> build\lib.win-amd64-3.8\reppy\cache
    copying reppy\cache\__init__.py -> build\lib.win-amd64-3.8\reppy\cache
    running build_ext
    building 'reppy.robots' extension
    error: Microsoft Visual C++ 14.0 is required. Get it with "Build Tools for Visual Studio": https://visualstudio.microsoft.com/downloads/
    ----------------------------------------
ERROR: Command errored out with exit status 1: 'c:\users\username\desktop\個人フォルダ\dev\python\python_scrape\.venv\scripts\python.exe' -u -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\username\\AppData\\Local\\Temp\\pip-install-evhv9026\\reppy\\setup.py'"'"'; __file__='"'"'C:\\Users\\username\\AppData\\Local\\Temp\\pip-install-evhv9026\\reppy\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' install --record 'C:\Users\username\AppData\Local\Temp\pip-record-kia5d9pl\install-record.txt' --single-version-externally-managed --compile --install-headers 'c:\users\username\desktop\個人フォルダ\dev\python\python_scrape\.venv\include\site\python3.8\reppy' Check the logs for full command output.
```

## コミットメッセージ
feat: 新しい機能  
fix: バグの修正  
docs: ドキュメントのみの変更  
style: 空白、フォーマット、セミコロン追加など  
refactor: 仕様に影響がないコード改善(リファクタ)  
perf: パフォーマンス向上関連  
test: テスト関連  
chore: ビルド、補助ツール、ライブラリ関連  