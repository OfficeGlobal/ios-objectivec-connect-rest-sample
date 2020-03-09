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
# Ejemplo Connect de Office 365 para iOS con Microsoft Graph

Conectarse a Office 365 es el primer paso que debe realizar cada aplicación iOS para empezar a trabajar con los datos y servicios de Office 365. Este ejemplo muestra cómo conectar y cómo llamar después a una API a través de Microsoft Graph (anteriormente denominada API unificada de Office 365).

 
## Requisitos previos
* [Xcode](https://developer.apple.com/xcode/downloads/) de Apple
* Una cuenta de Office 365. Puede realizar [una suscripción a Office 365 Developer](https://aka.ms/devprogramsignup) que incluya los recursos que necesite para comenzar a crear aplicaciones de Office 365.

     > Nota: Si ya dispone de una suscripción, el vínculo anterior le dirige a una página con el mensaje *No se puede agregar a su cuenta actual*. En ese caso, use una cuenta de su suscripción actual a Office 365.
* Un inquilino de Microsoft Azure para registrar la aplicación. Azure Active Directory (AD) proporciona servicios de identidad que las aplicaciones usan para autenticación y autorización. Puede adquirir una suscripción de prueba aquí: [Microsoft Azure](https://account.windowsazure.com/SignUp).

     > Importante: Además, necesitará asegurarse de que su suscripción a Azure esté enlazada a su inquilino de Office 365. Para ello, consulte la publicación del blog del equipo de Active Directory, [Crear y administrar varios directorios de Windows Azure Active Directory](http://blogs.technet.com/b/ad/archive/2013/11/08/creating-and-managing-multiple-windows-azure-active-directories.aspx). La sección **Agregar un nuevo directorio** le explicará cómo hacerlo. También puede ver [configurar el entorno](https://msdn.microsoft.com/office/office365/howto/setup-development-environment#bk_CreateAzureSubscription) de desarrollo de Office 365 y la **sección asociar la cuenta de Office 365 Azure AD para crear** y administrar aplicaciones y obtener más información.
      
* Un ID. de cliente (ID. de la aplicación) y redirige los valores de URI de una aplicación registrada en Azure. A esta aplicación de ejemplo se le debe conceder el permiso **Enviar correo como usuario** para **Microsoft Graph**. Para crear el registro, vea [conceder permisos a la aplicación conectar en Azure](https://github.com/microsoftgraph/ios-objectivec-connect-rest-sample/wiki/Grant-permissions-to-the-Connect-application-in-Azure).


       
## Ejecutar este ejemplo en Xcode

1. Clone este repositorio.
2. Use [Carthage](https://github.com/Carthage/Carthage) para importar la dependencia de iOS de la biblioteca de Authenticaion de Microsoft (MSAL). Descargue la versión más reciente de Carthage [aquí](https://github.com/Carthage/Carthage/releases). 
3. Abra **O365-iOS-Microsoft-Graph-Connect.xcodeproj**
4. Abra **Info.plist**. Verá que la **ClientID** (ID. de la aplicación que ha recibido del proceso de registro en la sección requisitos previos) va aquí.
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

    
## Compilación del marco MSAL

La versión preliminar de MSAL se distribuye como código fuente mediante Carthage. Para crear el código fuente, siga estos pasos:

1. Abra el terminal Bash y vaya a la carpeta raíz de la aplicación.
2. Cree un **cartfile**: Copie `echo "GitHub \" AzureAD/Microsoft-Authentication-Library-for-objc \ "\" Master \ "" > Cartfile` en el terminal y ejecute el comando.
3. Cree la biblioteca MSAL: Copie `Carthage actualización` en el terminal y ejecute el comando.        

5. Ejecute el ejemplo.

Para obtener más información acerca del ejemplo, consulte [Llamar a Microsoft Graph en una aplicación iOS](https://graph.microsoft.io/en-us/docs/platform/ios).

## Preguntas y comentarios

Nos encantaría recibir sus comentarios sobre el proyecto Connect de Office 365 para iOS con Microsoft Graph. Puede enviarnos sus preguntas y sugerencias a través de la sección [Problemas](https://github.com/OfficeDev/O365-iOS-Microsoft-Graph-Connect/issues) de este repositorio.

Las preguntas generales sobre desarrollo en Office 365 deben publicarse en [Stack Overflow](http://stackoverflow.com/questions/tagged/Office365+API). Asegúrese de que sus preguntas o comentarios se etiquetan con \[Office365] y \[MicrosoftGraph].

## Colaboradores
Deberá firmar un [Contrato de licencia de colaborador](https://cla.microsoft.com/) antes de enviar la solicitud de incorporación de cambios. Para completar el Contrato de licencia de colaborador (CLA), deberá enviar una solicitud mediante el formulario y, después, firmar electrónicamente el CLA cuando reciba el correo electrónico que contiene el vínculo al documento. 

Este proyecto ha adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/). Para obtener más información, vea [Preguntas frecuentes sobre el código de conducta](https://opensource.microsoft.com/codeofconduct/faq/) o póngase en contacto con [opencode@microsoft.com](mailto:opencode@microsoft.com) si tiene otras preguntas o comentarios.

## Recursos adicionales

* [Centro para desarrolladores de Office](http://dev.office.com/)
* [Página de información general de Microsoft Graph](https://graph.microsoft.io)
* [Usar CocoaPods](https://guides.cocoapods.org/using/using-cocoapods.html)

## Copyright
Copyright (c) 2017 Microsoft. Todos los derechos reservados.
