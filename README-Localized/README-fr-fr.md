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
# Exemple de connexion d’iOS à Office 365 à l'aide de Microsoft Graph

La connexion à Office 365 est la première étape que chaque application iOS doit suivre pour commencer à travailler avec les données et services Office 365. Cet exemple explique comment connecter, puis appeler une API via Microsoft Graph (précédemment appelée API unifiée Office 365).

 
## Conditions préalables
* [Xcode](https://developer.apple.com/xcode/downloads/) d’Apple
* Un compte Office 365. Vous pouvez vous inscrire à [un abonnement Office 365 Developer](https://aka.ms/devprogramsignup) incluant les ressources dont vous avez besoin pour commencer à créer des applications Office 365.

     > Remarque : Si vous avez déjà un abonnement, le lien précédent vous renvoie vers une page avec le message suivant : *Désolé, vous ne pouvez pas ajouter ceci à votre compte existant*. Dans ce cas, utilisez un compte lié à votre abonnement Office 365 existant.
* Un client Microsoft Azure pour enregistrer votre application. Azure Active Directory (AD) fournit des services d’identité que les applications utilisent à des fins d’authentification et d’autorisation. Un abonnement d’évaluation peut être demandé ici : [Microsoft Azure](https://account.windowsazure.com/SignUp).

     > Important : Vous devrez également vous assurer que votre abonnement Azure est lié à votre client Office 365. Pour cela, consultez le billet du blog de l’équipe d’Active Directory relatif à la [création et la gestion de plusieurs fenêtres dans les répertoires Azure Active Directory](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx). La section sur l’**ajout d’un nouveau répertoire** vous explique comment procéder. Pour en savoir plus, vous pouvez également consulter la rubrique relative à la [Configuration de votre environnement de développement Office 365](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription) et la section sur l’**Association de votre compte Office 365 à Azure Active Directory pour créer et gérer des applications**.
      
* Un ID client (ID d'application) et des valeurs URI de redirection d’une application enregistrée dans Azure. Cet exemple d’application doit obtenir l’autorisation **Envoyer un courrier électronique en tant qu’utilisateur** pour **Microsoft Graph**. Pour créer l’inscription, voir [Octroyer des autorisations à l’application Connect dans Azure](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure).


       
## Exécution de cet exemple dans Xcode

1. Clonez ce référentiel
2. Installez [Carthage](https://github.com/Carthage/Carthage) pour importer la dépendance iOS de la bibliothèque d'authentification Microsoft (MSAL). Téléchargez la dernière version de Carthage [ici](https://github.com/Carthage/Carthage/releases). 
3. Ouvrez **O365-iOS-Microsoft-Graph-Connect.Xcodeproj**
4. Ouvrez **info.plist**. Vous constatez que le **ClientID** (ID d’application que vous avez reçu lors du processus d’inscription dans la section conditions préalables) se place ici.
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

    
## Créez l’infrastructure MSAL

La préversion de MSAL est distribuée sous forme de code source à l’aide de Carthage. Pour créer le code source, procédez comme suit :

1. Ouvrez le terminal Bash et accédez au dossier racine de l’application.
2. Créez un élément **cartfile** : Copiez `echo "github \"AzureAD/microsoft-authentication-library-for-objc\" \"master\"" > Cartfile` dans le terminal et exécutez la commande.
3. Créez la bibliothèque d’authentification Microsoft (MSAL) : Copiez `Carthage Update` dans le terminal, puis exécutez la commande.        

5. Exécutez l’exemple.

Pour en savoir plus sur cet exemple, consultez la rubrique relative à l’[appel de Microsoft Graph dans une application iOS](https://graph.microsoft.io/en-us/docs/platform/ios).

## Questions et commentaires

Nous serions ravis de connaître votre opinion sur le projet de connexion d’iOS à Office 365 avec Microsoft Graph. Vous pouvez nous faire part de vos questions et suggestions dans la rubrique [Problèmes](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues) de ce référentiel.

Si vous avez des questions sur le développement d’Office 365, envoyez-les sur [Stack Overflow](http://stackoverflow.com/questions/tagged/Office365+API). Assurez-vous de poser vos questions ou de rédiger vos commentaires avec les tags \[MicrosoftGraph] et \[Office 365].

## Contribution
Vous devrez signer un [Contrat de licence de contributeur](https://cla.microsoft.com/) avant d’envoyer votre requête de tirage. Pour compléter le Contrat de licence de contributeur (CLA), vous devez envoyer une requête en remplissant le formulaire, puis signer électroniquement le CLA lorsque vous recevez le courrier électronique contenant le lien vers le document. 

Ce projet a adopté le [Code de conduite Open Source de Microsoft](https://opensource.microsoft.com/codeofconduct/). Pour en savoir plus, reportez-vous à la [FAQ relative au code de conduite](https://opensource.microsoft.com/codeofconduct/faq/) ou contactez [opencode@microsoft.com](mailto:opencode@microsoft.com) pour toute question ou tout commentaire.

## Autres ressources

* [Centre de développement Office](http://dev.office.com/)
* [Page de présentation de Microsoft Graph](https://graph.microsoft.io)
* [Utilisation de CocoaPods](https://guides.cocoapods.org/using/using-cocoapods.html)

## Copyright
Copyright (c) 2017 Microsoft. Tous droits réservés.
