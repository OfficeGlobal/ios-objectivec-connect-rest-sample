---
page_type: sample 
products:
- office-365
- office-outlook
- ms-graph
languages:
- objc
extensions:
  contentType: samples
  technologies:
  - Microsoft Graph
  services:
  - Office 365
  - Outlook
  createdDate: 9/8/2015 12:08:46 PM
---
# Microsoft Graph を使った iOS 用 Office 365 Connect サンプル

各 iOS アプリで Office 365 のサービスとデータの操作を開始するため、最初に Office 365 に接続する必要があります。このサンプルでは、Microsoft Graph (以前は Office 365 統合 API と呼ばれていた) を介して、1 つの API に接続して呼び出す方法を示します。

 
## 前提条件
* Apple 社の [Xcode](https://developer.apple.com/xcode/downloads/)
* Office 365 アカウント。Office 365 アプリのビルドを開始するために必要なリソースを含む [Office 365 Developer サブスクリプション](https://aka.ms/devprogramsignup)にサインアップできます。

     > 注:サブスクリプションをすでにお持ちの場合、上記のリンクをクリックすると、「*申し訳ございません。現在のアカウントに追加できません*」というメッセージが表示されるページに移動します。その場合は、現在使っている Office 365 サブスクリプションのアカウントをご利用いただけます。
* アプリケーションを登録する Microsoft Azure テナント。Azure Active Directory (AD) は、アプリケーションでの認証と承認に使う ID サービスを提供します。ここでは、試用版サブスクリプションを取得できます。[Microsoft Azure](https://account.windowsazure.com/SignUp)。

     > 重要:Azure サブスクリプションが Office 365 テナントにバインドされていることを確認する必要もあります。確認する方法については、Active Directory チームのブログ投稿「[複数の Windows Azure Active Directory を作成して管理する](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx)」をご覧ください。「**新しいディレクトリを追加する**」セクションで、この方法を説明しています。また、詳しくは、「[Office 365 開発環境のセットアップ](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription)」と「**Office 365 アカウントを Azure AD と関連付けて、アプリを作成して管理する**」のセクションもご覧ください。
      
* Azure に登録されたアプリケーションのクライアント ID とリダイレクト URI の値。このサンプル アプリケーションには、**Microsoft Graph** 用に**ユーザーとしてメールを送信する**アクセス許可が付与される必要があります。登録を作成する方法については、「[Grant permissions to the Connect application in Azure (Azure で Connect アプリケーションにアクセス許可を付与する)](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure)」を参照してください。


       
## Xcode でこのサンプルを実行する

1. このリポジトリの複製を作成する
2. [Carthage](https://github.com/Carthage/Carthage) を使用して、Microsoft 認証ライブラリ (MSAL) の iOS 依存関係をインポートします。Carthage の最新バージョンを[こちら](https://github.com/Carthage/Carthage/releases)からダウンロードします。 
3. **O365-iOS-Microsoft-Graph-Connect.xcodeproj** を開きます。
4. **info.plist** を開きます。**ClientID** (「前提条件」セクションの登録プロセスで受け取ったアプリケーション ID) は次の場所で使用します。
  ```xml
    <key>CFBundleURLTypes</key>
      <array>
          <dict>
              <key>CFBundleTypeRole</key>
              <string>Editor</string>
              <key>CFBundleURLName</key>
              <string>$(PRODUCT_BUNDLE_IDENTIFIER)</string>
              <key>CFBundleURLSchemes</key>
              <array>
                  <string>msalENTER_YOUR_CLIENT_ID</string>
                  <string>auth</string>
              </array>
          </dict>
      </array>

  ```

    
## MSAL フレームワークをビルドする

MSAL のプレビュー バージョンは、Carthage を使用してソース コードとして配布されています。ソース コードを作成するには、次の手順を実行します。

1. Bash ターミナルを開き、アプリのルート フォルダーに移動します。
2. **cartfile** を作成します:`echo "github \"AzureAD/microsoft-authentication-library-for-objc\" \"master\"" > Cartfile` をターミナルにコピーし、コマンドを実行します。
3. MSAL ライブラリのビルド:`carthage update` をターミナルにコピーし、コマンドを実行します。        

5. サンプルを実行します。

サンプルについて詳しくは、「[iOS アプリで Microsoft Graph を呼び出す](https://graph.microsoft.io/en-us/docs/platform/ios)」をご覧ください。

## 質問とコメント

Office 365 iOS Microsoft Graph Connect プロジェクトに関するフィードバックをお寄せください。質問や提案につきましては、このリポジトリの「[問題](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues)」セクションで送信できます。

Office 365 開発全般の質問につきましては、「[スタック オーバーフロー](http://stackoverflow.com/questions/tagged/Office365+API)」に投稿してください。質問やコメントには、必ず \[Office365] と \[MicrosoftGraph] のタグを付けてください。

## 投稿
プル要求を送信する前に、[投稿者のライセンス契約](https://cla.microsoft.com/)に署名する必要があります。投稿者のライセンス契約 (CLA) を完了するには、ドキュメントへのリンクを含むメールを受信した際に、フォームから要求を送信し、CLA に電子的に署名する必要があります。 

このプロジェクトでは、[Microsoft Open Source Code of Conduct (Microsoft オープン ソース倫理規定)](https://opensource.microsoft.com/codeofconduct/) が採用されています。詳細については、「[Code of Conduct の FAQ](https://opensource.microsoft.com/codeofconduct/faq/)」を参照してください。また、その他の質問やコメントがあれば、[opencode@microsoft.com](mailto:opencode@microsoft.com) までお問い合わせください。

## その他のリソース

* [Office デベロッパー センター](http://dev.office.com/)
* [Microsoft Graph の概要ページ](https://graph.microsoft.io)
* [CocoaPods を使う](https://guides.cocoapods.org/using/using-cocoapods.html)

## 著作権
Copyright (c) 2017 Microsoft.All rights reserved.
