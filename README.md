# QuickMaster

## プロジェクトの作成
### dotnet new mvc -o QuickMaster -f net7.0 --no-https

## アプリの起動
### dotnet watch

## Routeの定義
### プロジェクト配下: Program.cs

## Layoutの定義
### /Views/Shared/_Layout.cshtml

## EF Core利用の為のツール/パッケージのインストール
### dotnet tool install --global dotnet-ef
#### ツール ディレクトリ '/home/shusuke/.dotnet/tools' は現在、PATH 環境変数にありません。
#### Bash を使用している場合、次のコマンドを実行してプロファイルに追加できます。

#### cat << \EOF >> ~/.bash_profile
#### # Add .NET Core SDK tools
#### export PATH="$PATH:/home/shusuke/.dotnet/tools"
#### EOF

#### 次のコマンドを実行して現在のセッションに追加できます。

#### export PATH="$PATH:/home/shusuke/.dotnet/tools"

#### 次のコマンドを使用してツールを呼び出せます。dotnet-ef
#### ツール 'dotnet-ef' (バージョン '7.0.7') が正常にインストールされました。

### dotnet tool install --global dotnet-aspnet-codegenerator
#### ツール ディレクトリ '/home/shusuke/.dotnet/tools' は現在、PATH 環境変数にありません。
#### Bash を使用している場合、次のコマンドを実行してプロファイルに追加できます。

#### cat << \EOF >> ~/.bash_profile
#### # Add .NET Core SDK tools
#### export PATH="$PATH:/home/shusuke/.dotnet/tools"
#### EOF

#### 次のコマンドを実行して現在のセッションに追加できます。

#### export PATH="$PATH:/home/shusuke/.dotnet/tools"

#### 次のコマンドを使用してツールを呼び出せます。dotnet-aspnet-codegenerator
#### ツール 'dotnet-aspnet-codegenerator' (バージョン '7.0.7') が正常にインストールされました。

### dotnet add package Microsoft.EntityFrameworkCore
### dotnet add package Microsoft.EntityFrameworkCore.SqlServer
### dotnet add package Pomelo.EntityFrameworkCore.MySql
### dotnet add package Microsoft.EntityFrameworkCore.Design
### dotnet add package Microsoft.EntityFrameworkCore.Tools
### dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
### dotnet add package Microsoft.SqlServer → 不要かも
### (※) Microsoft.EntityFrameworkCore　Microsoft.EntityFrameworkCore.SqlServer　→ MySQLを使用するとしても、スキャフォールディングを使用するさいに必要。

## マイグレーション
### export PATH="$PATH:/home/shusuke/.dotnet/tools"
### dotnet ef migrations add Initial
### dotnet ef database update

## MariaDBのユーザ
### GRANT ALL PRIVILEGES ON QuickMaster.* TO dotnetusr@localhost IDENTIFIED BY 'dotnetpass';

##  スキャフォールディング
### export PATH="$PATH:/home/shusuke/.dotnet/tools"
### dotnet aspnet-codegenerator controller --project "./" --controllerName BookController --relativeFolderPath Controllers --useAsyncActions --model Book --dataContext MyContext --useDefaultLayout --referenceScriptLibraries
### 画面での確認 http://localhost:5220/book