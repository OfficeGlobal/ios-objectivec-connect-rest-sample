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
# Пример приложения iOS, подключающегося к Office 365 и использующего Microsoft Graph

Подключение к Office 365 — это первый шаг, который должно выполнить каждое приложение iOS, чтобы начать работу со службами и данными Office 365. В этом примере показано, как подключить, а затем вызвать один API с помощью Microsoft Graph (прежнее название — единый API Office 365).

 
## Необходимые компоненты
* [Xcode](https://developer.apple.com/xcode/downloads/) от Apple
* Учетная запись Office 365. Вы можете [подписаться на план Office 365 для разработчиков](https://aka.ms/devprogramsignup), который включает ресурсы, необходимые для создания приложений Office 365.

     > Примечание. Если у вас уже есть подписка, при выборе приведенной выше ссылки откроется страница с сообщением *К сожалению, вы не можете добавить это к своей учетной записи*. В этом случае используйте учетную запись, сопоставленную с текущей подпиской на Office 365.
* Клиент Microsoft Azure для регистрации приложения. В Azure Active Directory (AD) доступны службы идентификации, которые приложения используют для проверки подлинности и авторизации. Здесь можно получить пробную подписку: [Microsoft Azure](https://account.windowsazure.com/SignUp).

     > Важно! Убедитесь, что ваша подписка на Azure привязана к клиенту Office 365. Для этого просмотрите запись в блоге команды Active Directory, посвященную [созданию нескольких каталогов Microsoft Azure AD и управлению ими](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx). Инструкции приведены в разделе о **добавлении нового каталога**. Дополнительные сведения см. в статье [Как настроить среду разработки для Office 365](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription) и, в частности, в разделе **Связывание Azure AD и учетной записи Office 365 для создания приложений и управления ими**.
      
* URI перенаправления и идентификатор клиента (идентификатор приложения), указанные при регистрации приложения в Azure. Этому приложению необходимо предоставить разрешение **Отправка почты от имени пользователя** для **Microsoft Graph**. Сведения о том, как создать регистрацию, см. в статье [Предоставление разрешений для приложения Connect в Azure](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure).


       
## Запуск примера в XCode

1. Клонируйте этот репозиторий
2. Используйте [Carthage](https://github.com/Carthage/Carthage) для импорта библиотеки проверки подлинности Майкрософт для iOS. Скачайте последнюю версию Carthage [здесь](https://github.com/Carthage/Carthage/releases). 
3. Откройте **O365-iOS-Microsoft-Graph-Connect.xcodeproj**
4. Откройте **info.plist**. Здесь указывается **ClientID** (идентификатор приложения, полученный в результате процесса регистрации в разделе "Необходимые компоненты").
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

    
## Сборка платформы MSAL

Ознакомительная версия MSAL распространяется в виде исходного кода с помощью Carthage. Чтобы создать исходный код, выполните указанные ниже действия.

1. Откройте терминал Bash и перейдите к корневой папке приложения.
2. Создайте **cartfile**: скопируйте `echo "github \"AzureAD/microsoft-authentication-library-for-objc\" \"master\"" > Cartfile` в терминал и выполните команду.
3. Создайте библиотеку MSAL: скопируйте `carthage update` в терминал и выполните команду.        

5. Запустите пример.

Дополнительные сведения о приложении см. в статье [Вызов Microsoft Graph в приложении для iOS](https://graph.microsoft.io/en-us/docs/platform/ios).

## Вопросы и комментарии

Мы будем рады получить от вас отзывы о проекте приложения iOS, подключающегося к Office 365 и использующего Microsoft Graph. Отправляйте нам свои вопросы и предложения в раздел этого репозитория, посвященный [проблемам](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues).

Общие вопросы о разработке решений для Office 365 следует публиковать на сайте [Stack Overflow](http://stackoverflow.com/questions/tagged/Office365+API). Обязательно помечайте свои вопросы и комментарии тегами \[Office365] и \[MicrosoftGraph].

## Участие
Прежде чем отправить запрос на включение внесенных изменений, необходимо подписать [лицензионное соглашение с участником](https://cla.microsoft.com/). Чтобы заполнить лицензионное соглашение с участником (CLA), вам потребуется отправить запрос с помощью формы, а затем после получения электронного сообщения со ссылкой на этот документ подписать CLA с помощью электронной подписи. 

Этот проект соответствует [Правилам поведения разработчиков открытого кода Майкрософт](https://opensource.microsoft.com/codeofconduct/). Дополнительные сведения см. в разделе [вопросов и ответов о правилах поведения](https://opensource.microsoft.com/codeofconduct/faq/). Если у вас возникли вопросы или замечания, напишите нам по адресу [opencode@microsoft.com](mailto:opencode@microsoft.com).

## Дополнительные ресурсы

* [Центр разработки для Office](http://dev.office.com/)
* [Страница с общими сведениями о Microsoft Graph](https://graph.microsoft.io)
* [Использование CocoaPods](https://guides.cocoapods.org/using/using-cocoapods.html)

## Авторское право
(c) Корпорация Майкрософт (Microsoft Corporation), 2017. Все права защищены.
