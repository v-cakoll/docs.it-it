---
title: 'Procedura: Compilare un''applicazione Web Form ASP.NET in grado di riconoscere attestazioni con WIF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d5b81e20ed1b39c7750329718729905484eb7fa1
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a>Procedura: Compilare un'applicazione Web Form ASP.NET in grado di riconoscere attestazioni con WIF
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Web Form ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per creare una semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni. Sono inoltre disponibili istruzioni su come testare la semplice applicazione Web Form ASP.NET in grado di riconoscere attestazioni per la corretta implementazione dell'autenticazione federata. La procedura decritta in questo argomento non include istruzioni dettagliate per la creazione di un servizio token di sicurezza e presuppone che il servizio sia già stato configurato.  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="objectives"></a>Obiettivi  
  
-   Configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni  
  
-   Testare l'applicazione Web Form ASP.NET in grado di riconoscere attestazioni  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
  
-   Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione federata  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Passaggio 1: creare una semplice applicazione Web Form ASP.NET  
 In questo passaggio si creerà una nuova applicazione Web Form ASP.NET.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Per creare un'applicazione ASP.NET semplice  
  
1.  Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2.  Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.  
  
3.  In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a>Passaggio 2: configurare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni  
 In questo passaggio si aggiungeranno voci di configurazione al file di configurazione *Web.config* dell'applicazione Web Form ASP.NET per renderla in grado di riconoscere attestazioni.  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a>Per configurare l'applicazione ASP.NET per l'autenticazione basata su attestazioni  
  
1.  Aggiungere le seguenti voci di sezione di configurazione al file di configurazione *Web.config* subito dopo l'elemento di apertura **\<configuration>**:  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Aggiungere un **elemento \<location>** che consente l'accesso ai metadati di federazione dell'applicazione:  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  Aggiungere le seguenti voci di configurazione all'interno di elementi **\<system.web>** per negare le autorizzazioni agli utenti, disabilitare l'autenticazione nativa e abilitare WIF per gestire l'autenticazione.  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Aggiungere un elemento **\<system.webServer>** che definisce i moduli per l'autenticazione federata. Si noti che l'attributo *PublicKeyToken* deve essere uguale all'attributo *PublicKeyToken* per le voci **\<configSections>** aggiunte in precedenza:  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Aggiungere le voci di configurazione correlate a Windows Identity Foundation seguenti e assicurarsi che l'URL e il numero di porta dell'applicazione ASP.NET corrispondano ai valori nella voce **\<audienceUris>**, all'attributo **realm** dell'elemento **\<wsFederation>** e all'attributo **reply** dell'elemento **\<wsFederation>**. Assicurarsi anche che il valore **issuer** sia appropriato per l'URL del servizio token di sicurezza.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  Aggiungere un riferimento all'assembly <xref:System.IdentityModel>.  
  
7.  Compilare la soluzione e assicurarsi che non ci siano errori.  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio si testerà l'applicazione Web Form ASP.NET configurata per l'autenticazione basata sulle attestazioni. Per eseguire un test di base, si aggiungerà codice che visualizza le attestazioni nel token rilasciato dal servizio token di sicurezza.  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a>Per testare l'applicazione Web Form ASP.NET per l'autenticazione basata su attestazioni  
  
1.  Aprire il file **Default.aspx** nel progetto **TestApp** e sostituire il markup esistente con quello seguente:  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  Salvare **Default.aspx** e quindi aprire il file code-behind denominato **Default.aspx.cs**.  
  
    > [!NOTE]
    >  Il file **Default.aspx.cs** potrebbe essere nascosto sotto **Default.aspx** in Esplora soluzioni. Se **Default.aspx.cs** non è visibile, espandere **Default.aspx** facendo clic sul triangolo accanto.  
  
3.  Sostituire il codice esistente nel metodo **Page_Load** in **Default.aspx.cs** con il codice seguente:  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  Salvare **Default.aspx.cs** e compilare la soluzione.  
  
5.  Eseguire la soluzione premendo **F5**.  
  
6.  Dovrebbe essere visualizzata la pagina che mostra le attestazioni nel token emesso dal servizio token di sicurezza.

