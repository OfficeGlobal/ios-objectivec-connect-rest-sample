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
# 使用 Microsoft Graph 的 iOS Office 365 Connect 示例

连接到 Office 365 是每个 iOS 应用开始使用 Office 365 服务和数据必须采取的第一步。该示例演示如何通过 Microsoft Graph（旧称 Office 365 统一 API）连接并调用一个 API。

 
## 先决条件
* Apple [Xcode](https://developer.apple.com/xcode/downloads/)
* Office 365 帐户。你可以注册 [Office 365 开发人员订阅](https://aka.ms/devprogramsignup)，其中包含你开始构建 Office 365 应用所需的资源。

     > 注意：如果您已经订阅，之前的链接会将您转至包含以下信息的页面：*抱歉，您无法将其添加到当前帐户*。在这种情况下，请使用当前 Office 365 订阅中的帐户。
* 用于注册您的应用程序的 Microsoft Azure 租户。Azure Active Directory (AD) 为应用程序提供了用于进行身份验证和授权的标识服务。您还可在此处获得试用订阅：[Microsoft Azure](https://account.windowsazure.com/SignUp)。

     > 重要说明：还需要确保你的 Azure 订阅已绑定到 Office 365 租户。要执行这一操作，请参阅 Active Directory 团队的博客文章：[创建和管理多个 Microsoft Azure Active Directory](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx)。**添加新目录**一节将介绍如何执行此操作。你还可以参阅[“设置 Office 365 开发环境”](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription)和**“关联你的 Office 365 帐户和 Azure AD 以创建并管理应用”**部分获取详细信息。
      
* 在 Azure 中注册的应用程序的客户端 ID（应用程序 ID）和重定向 URI 值。必须向该示例应用程序授予**以用户身份发送邮件**权限以使用 **Microsoft Graph**。若要创建注册，请参阅[在 Azure 中向 Connect 应用程序授予权限](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure)。


       
## 在 Xcode 中运行此示例

1. 克隆该存储库
2. 使用 [Carthage](https://github.com/Carthage/Carthage) 以导入 Microsoft 身份验证库 (MSAL) iOS 依赖项。请在[此处](https://github.com/Carthage/Carthage/releases)下载 Carthage 最新版本。 
3. 打开 **O365-iOS-Microsoft-Graph-Connect.xcodeproj**
4. 打开 **info.plist**。你将看到 **ClientID**（在“先决条件”部分的注册过程中收到的应用程序 ID）位于此处。
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

    
## 生成 MSAL 框架

MSAL 预览版将作为使用 Carthage 的源代码进行分发。若要构建源代码，请执行以下步骤：

1. 打开 Bash 终端并转到应用根文件夹。
2. 创建 **cartfile**：将 `echo "github \"AzureAD/microsoft-authentication-library-for-objc\" \"master\"" > Cartfile` 复制到终端并运行命令。
3. 生成 MSAL 库：将 `carthage update` 复制到终端，并运行该命令。        

5. 运行示例。

要了解有关该示例的详细信息，请参阅[在 iOS 应用中调用 Microsoft Graph](https://graph.microsoft.io/en-us/docs/platform/ios)。

## 问题和意见

我们乐意倾听您有关 Office 365 iOS Microsoft Graph Connect 项目的反馈。您可以在该存储库中的[问题](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues)部分将问题和建议发送给我们。

与 Office 365 开发相关的问题一般应发布在[堆栈溢出](http://stackoverflow.com/questions/tagged/Office365+API)中。确保您的问题或意见使用了 \[Office365] 和 \[MicrosoftGraph] 标记。

## 贡献
您需要在提交拉取请求之前签署[参与者许可协议](https://cla.microsoft.com/)。要完成参与者许可协议 (CLA)，你需要通过表格提交请求，并在收到包含文件链接的电子邮件时在 CLA 上提交电子签名。 

此项目已采用 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。有关详细信息，请参阅[行为准则常见问题解答](https://opensource.microsoft.com/codeofconduct/faq/)。如有其他任何问题或意见，也可联系 [opencode@microsoft.com](mailto:opencode@microsoft.com)。

## 其他资源

* [Office 开发人员中心](http://dev.office.com/)
* [Microsoft Graph 概述页](https://graph.microsoft.io)
* [使用 CocoaPods](https://guides.cocoapods.org/using/using-cocoapods.html)

## 版权信息
版权所有 (c) 2017 Microsoft。保留所有权利。
