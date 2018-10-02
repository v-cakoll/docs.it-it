---
title: "Procedura: Compilare un'applicazione Web ASP.NET MVC in grado di riconoscere attestazioni con WIF"
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
ms.openlocfilehash: 4a003acbf4e182a0493368b586a3add229d8b526
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863026"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a>Procedura: Compilare un'applicazione Web ASP.NET MVC in grado di riconoscere attestazioni con WIF
## <a name="applies-to"></a>Si applica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   MVC ASP.NET®  
  
## <a name="summary"></a>Riepilogo  
 Questo argomento include le procedure dettagliate per creare una semplice applicazione Web MVC ASP.NET in grado di riconoscere attestazioni. Sono inoltre disponibili istruzioni su come testare la semplice applicazione Web MVC ASP.NET in grado di riconoscere attestazioni per la corretta implementazione dell'autenticazione basata su attestazioni. La procedura decritta in questo argomento non include istruzioni dettagliate per la creazione di un servizio token di sicurezza e presuppone che il servizio sia già stato configurato.  
  
## <a name="contents"></a>Sommario  
  
-   Obiettivi  
  
-   Riepilogo dei passaggi  
  
-   Passaggio 1: creare l'applicazione MVC ASP.NET semplice  
  
-   Passaggio 2: configurare l'applicazione MVC ASP.NET per l'autenticazione basata su attestazioni  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
-   Elementi correlati  
  
## <a name="objectives"></a>Obiettivi  
  
-   Configurare l'applicazione Web MVC ASP.NET per l'autenticazione basata su attestazioni  
  
-   Testare l'applicazione Web MVC ASP.NET in grado di riconoscere attestazioni  
  
## <a name="summary-of-steps"></a>Riepilogo dei passaggi  
  
-   Passaggio 1: creare l'applicazione MVC ASP.NET semplice  
  
-   Passaggio 2: configurare l'applicazione MVC ASP.NET per l'autenticazione basata su attestazioni  
  
-   Passaggio 3: eseguire i test sulla soluzione  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a>Passaggio 1: creare l'applicazione MVC ASP.NET semplice  
 In questo passaggio si creerà una nuova applicazione MVC ASP.NET.  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a>Per creare un'applicazione MVC ASP.NET semplice  
  
1.  Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.  
  
2.  Nella finestra **Nuovo progetto** fare clic su **Applicazione Web MVC 3 ASP.NET**.  
  
3.  In **Nome** immettere `TestApp` e fare clic su **OK**.  
  
4.  Nella finestra di dialogo **Nuovo progetto MVC 3 ASP.NET** selezionare **Applicazione Internet** tra i modelli disponibili, assicurarsi che **Motore di visualizzazione** sia impostato su **Razor** e quindi fare clic su **OK**.  
  
5.  All'apertura del nuovo progetto fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e scegliere **Proprietà**.  
  
6.  Nella pagina delle proprietà del progetto fare clic sulla scheda **Web** a sinistra e assicurarsi che sia selezionata l'opzione **Usa server Web IIS locale**.  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a>Passaggio 2: configurare l'applicazione MVC ASP.NET per l'autenticazione basata su attestazioni  
 In questo passaggio si aggiungeranno voci di configurazione al file di configurazione *Web.config* dell'applicazione Web MVC ASP.NET per renderla in grado di riconoscere attestazioni.  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a>Per configurare l'applicazione MVC ASP.NET per l'autenticazione basata su attestazioni  
  
1.  Aggiungere le definizioni di sezione di configurazione seguenti nel file di configurazione *Web.config*, che definiscono le sezioni di configurazione richieste da Windows Identity Foundation. Aggiungere le definizioni subito dopo l'elemento di apertura **\<configuration>**:  
  
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
  
4.  Aggiungere le voci di configurazione correlate a Windows Identity Foundation seguenti e assicurarsi che l'URL e il numero di porta dell'applicazione ASP.NET corrispondano ai valori nella voce **\<audienceUris>**, all'attributo **realm** dell'elemento **\<wsFederation>** e all'attributo **reply** dell'elemento **\<wsFederation>**. Assicurarsi anche che il valore **issuer** sia appropriato per l'URL del servizio token di sicurezza.  
  
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
  
5.  Aggiungere un riferimento all'assembly <xref:System.IdentityModel>.  
  
6.  Compilare la soluzione e assicurarsi che non ci siano errori.  
  
## <a name="step-3--test-your-solution"></a>Passaggio 3: eseguire i test sulla soluzione  
 In questo passaggio si testerà l'applicazione Web MVC ASP.NET configurata per l'autenticazione basata sulle attestazioni. Per eseguire un test di base, si aggiungerà codice semplice che visualizza le attestazioni nel token rilasciato dal servizio token di sicurezza.  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a>Per testare l'applicazione MVC ASP.NET per l'autenticazione basata su attestazioni  
  
1.  In **Esplora soluzioni** espandere la cartella **Controller** e aprire il file *HomeController.cs* nell'editor. Aggiungere il codice seguente al metodo **Index**:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  In **Esplora soluzioni** espandere le cartelle **Visualizzazioni** e **Home** e aprire il file *Index.cshtml* nell'editor. Eliminarne il contenuto e aggiungere il markup seguente:  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  Eseguire la soluzione premendo **F5**.  
  
4.  Dovrebbe essere visualizzata la pagina che mostra le attestazioni nel token emesso dal servizio token di sicurezza.  
  
## <a name="related-items"></a>Elementi correlati  
  
-   [Procedura: Compilare un'applicazione Web Form ASP.NET che può riconoscere attestazioni con WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
