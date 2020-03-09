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
# Exemplo de conexão com o Office 365 para iOS usando o Microsoft Graph

A primeira etapa para que os aplicativos iOS comecem a funcionar com dados e serviços do Office 365 é estabelecer uma conexão com essa plataforma. Este exemplo mostra como se conectar e chamar uma única API do Microsoft Graph (antiga API unificada do Office 365).

 
## Pré-requisitos
* [Xcode](https://developer.apple.com/xcode/downloads/) da Apple
* Uma conta do Office 365. Inscreva-se para uma [Assinatura de Desenvolvedor do Office 365](https://aka.ms/devprogramsignup), que inclui os recursos necessários para começar a criação de aplicativos do Office 365.

     > Observação: Caso já tenha uma assinatura, o link anterior direcionará você para uma página com a mensagem *Não é possível adicioná-la à sua conta atual*. Nesse caso, use uma conta de sua assinatura atual do Office 365.
* Um locatário do Microsoft Azure para registrar o seu aplicativo. O Active Directory (AD) do Azure fornece serviços de identidade que os aplicativos usam para autenticação e autorização. Você pode adquirir uma assinatura de avaliação aqui: [Microsoft Azure](https://account.windowsazure.com/SignUp).

     > Importante: Você também deve garantir que a assinatura do Azure esteja vinculada ao seu locatário do Office 365. Para saber como fazer isso, confira a postagem de blog da equipe do Active Directory, [Criando e gerenciando vários Active Directories do Microsoft Azure](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx). A seção **Adicionando um novo diretório** explica como fazer isso. Para saber mais, confira o artigo [Configurar o ambiente de desenvolvimento do Office 365](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription) e a seção **Associar uma conta do Office 365 ao Azure AD para criar e gerenciar aplicativos**.
      
* Valores de uma id do cliente (id de aplicativo) e de um uri de redirecionamento de um aplicativo registrado no Azure. Esse exemplo de aplicativo deve ter a permissão **Enviar email como usuário** concedida para o **Microsoft Graph**. Para criar o registro, confira [Conceder permissões para o aplicativo Connect no Azure](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure).


       
## Executando este exemplo em Xcode

1. Clonar este repositório
2. Use o [Carthage](https://github.com/Carthage/Carthage) para importar a dependência de iOS da Biblioteca de Autenticação da Microsoft (MSAL). Baixe a versão mais recente do Carthage [aqui](https://github.com/Carthage/Carthage/releases). 
3. Abra **O365-iOS-Microsoft-Graph-Connect.xcodeproj**
4. Abra **info.plist**. Você verá que o **ClientID** (ID do aplicativo que você recebeu do processo de registro na seção de pré-requisitos) vai aqui.
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

    
## Criar a estrutura da MSAL

A versão de visualização da MSAL é distribuída como código-fonte usando o Carthage. Para criar o código-fonte, siga estas etapas:

1. Abra o terminal Bash e vá para a pasta raiz do aplicativo.
2. Crie um **cartfile**: Copie `echo "github \"AzureAD/microsoft-authentication-library-for-objc\" \"master\"" > Cartfile` no terminal e execute o comando.
3. Criar biblioteca da MSAL: Copie a `atualização do carthage` no terminal e execute o comando.        

5. Execute o exemplo.

Para saber mais sobre o exemplo, confira o artigo [Chamar o Microsoft Graph em um aplicativo iOS](https://graph.microsoft.io/en-us/docs/platform/ios).

## Perguntas e comentários

Gostaríamos de saber sua opinião sobre o projeto de conexão com o Office 365 para iOS usando o Microsoft Graph. Você pode enviar perguntas e sugestões na seção [Problemas](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues) deste repositório.

Faça a postagem de perguntas sobre desenvolvimento do Office 365 em geral na página do [Stack Overflow](http://stackoverflow.com/questions/tagged/Office365+API). Não deixe de marcar as perguntas ou comentários com \[Office365] e \[MicrosoftGraph].

## Colaboração
Assine o [Contributor License Agreement (Contrato de Licença de Colaborador)](https://cla.microsoft.com/) antes de enviar a solicitação pull. Para concluir o CLA (Contributor License Agreement), você deve enviar uma solicitação através do formulário e assinar eletronicamente o CLA quando receber o email com o link para o documento. 

Este projeto adotou o [Código de Conduta de Código Aberto da Microsoft](https://opensource.microsoft.com/codeofconduct/).  Para saber mais, confira as [Perguntas frequentes sobre o Código de Conduta](https://opensource.microsoft.com/codeofconduct/faq/) ou entre em contato pelo [opencode@microsoft.com](mailto:opencode@microsoft.com) se tiver outras dúvidas ou comentários.

## Recursos adicionais

* [Centro de Desenvolvimento do Office](http://dev.office.com/)
* [Página de visão geral do Microsoft Graph](https://graph.microsoft.io)
* [Usando o CocoaPods](https://guides.cocoapods.org/using/using-cocoapods.html)

## Direitos autorais
Copyright (c) 2017 Microsoft. Todos os direitos reservados.
