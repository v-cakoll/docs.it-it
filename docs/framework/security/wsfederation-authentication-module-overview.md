---
title: Panoramica del modulo di autenticazione WSFederation
ms.date: 03/30/2017
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
author: BrucePerlerMS
ms.openlocfilehash: 63090efdf97066b4a276880d4f4be0f843de6800
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586048"
---
# <a name="wsfederation-authentication-module-overview"></a>Panoramica del modulo di autenticazione WSFederation
Windows Identity Foundation (WIF) include il supporto per l'autenticazione federata nelle applicazioni ASP.NET tramite il modulo di autenticazione WS-Federated (WS-FAM, WS-Federated Authentication Module). Questo argomento aiuta capire come funziona l'autenticazione federata e come usarla.  
  
### <a name="overview-of-federated-authentication"></a>Panoramica dell'autenticazione federata  
 L'autenticazione federata consente a un servizio token di sicurezza in un dominio di trust di fornire informazioni di autenticazione a un servizio token di sicurezza in un altro dominio di trust quando tra i due domini c'è una relazione di trust. Nella figura seguente è riportato un esempio di questo oggetto:  
  
 ![Diagramma che illustra lo scenario di autenticazione federata.](./media/wsfederation-authentication-module-overview/federated-authentication.gif)  
  
1. Un client nel dominio di trust Fabrikam invia una richiesta a un'applicazione relying party nel dominio di trust Contoso.  
  
2. La relying party reindirizza il client a un servizio token di sicurezza nel dominio di trust Contoso. Questo servizio token di sicurezza non conosce il client.  
  
3. Il servizio token di sicurezza di Contoso reindirizza il client a un servizio token di sicurezza nel dominio di trust Fabrikam, con cui il dominio di trust Contoso ha una relazione di trust.  
  
4. Il servizio token di sicurezza di Fabrikam verifica l'identità del client e rilascia un token di sicurezza al servizio token di sicurezza di Contoso.  
  
5. Il servizio token di sicurezza di Contoso usa il token di Fabrikam per creare un proprio token che può essere usato dalla relying party e lo invia alla relying party.  
  
6. La relying party estrae le attestazioni del client dal token di sicurezza e prende una decisione relativa all'autorizzazione.  
  
### <a name="using-the-federated-authentication-module-with-aspnet"></a>Uso del modulo di autenticazione federata con ASP.NET  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WS-FAM) è un modulo HTTP che consente di aggiungere l'autenticazione federata a un'applicazione [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. L'autenticazione federata lascia che la logica di autenticazione venga gestita dal servizio token di sicurezza e consente allo sviluppatore di concentrarsi sulla scrittura della logica di business.  
  
 WS-FAM viene configurato per specificare il servizio token di sicurezza a cui devono essere reindirizzate le richieste non autenticate. WIF consente di autenticare un utente in due modi:  
  
1. Reindirizzamento passivo: Quando un utente non autenticato prova ad accedere a una risorsa protetta e si vuole semplicemente reindirizzarlo a un servizio token di sicurezza senza richiedere una pagina di accesso, si tratta dell'approccio corretto. Il servizio token di sicurezza verifica l'identità dell'utente e rilascia un token di sicurezza contenente le attestazioni appropriate per l'utente. Per questa opzione è necessario aggiungere WS-FAM nella pipeline dei moduli HTTP. È possibile usare Identity and Access Tool per Visual Studio 2012 per modificare il file di configurazione dell'applicazione per usare WS-FAM e stabilire la federazione con un servizio token di sicurezza. Per altre informazioni, vedere [Identity and Access Tool for Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md) (Identity and Access Tool per Visual Studio 2012).  
  
2. È possibile chiamare il metodo <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=nameWithType> o il metodo <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> dal code-behind per una pagina di accesso nell'applicazione relying party.  
  
 Nel reindirizzamento passivo tutte le comunicazioni avvengono tramite risposta/reindirizzamento dal client (in genere un browser). È possibile aggiungere WS-FAM alla pipeline HTTP dell'applicazione, dove controlla le richieste utente non autenticate e reindirizza gli utenti al servizio token di sicurezza specificato.  
  
 WS-FAM genera inoltre diversi eventi che consentono di personalizzare le relative funzionalità in un'applicazione [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
### <a name="how-the-ws-fam-works"></a>Funzionamento di WS-FAM  
 WS-FAM viene implementato nella classe <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>. In genere, si aggiunge WS-FAM alla pipeline HTTP dell'applicazione relying party [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Quando un utente non autenticato cerca di accedere a una risorsa protetta, la relying party restituisce una risposta HTTP di tipo "401 autorizzazione negata". WS-FAM intercetta questa risposta invece di consentire al client di riceverla, quindi reindirizza l'utente al servizio token di sicurezza specificato. Il servizio token di sicurezza rilascia un token di sicurezza, che viene anch'esso intercettato da WS-FAM. WS-FAM Usa il token per creare un'istanza di <xref:System.Security.Claims.ClaimsPrincipal> per l'utente autenticato, che consente i normali meccanismi di autorizzazione .NET Framework funzionare.  
  
 Poiché HTTP è senza stato, è necessaria una soluzione per evitare di ripetere l'intero processo ogni volta che l'utente cerca di accedere a un'altra risorsa protetta. A questo scopo, si usa <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Quando il servizio token di sicurezza rilascia un token di sicurezza per l'utente, <xref:System.IdentityModel.Services.SessionAuthenticationModule> crea anche un token di sicurezza della sessione per l'utente e lo inserisce in un cookie. Nelle richieste successive, <xref:System.IdentityModel.Services.SessionAuthenticationModule> intercetta questo cookie e lo usa per ricostruire l'oggetto <xref:System.Security.Claims.ClaimsPrincipal> dell'utente.  
  
 Il diagramma seguente mostra il flusso generale delle informazioni nel caso del reindirizzamento passivo. La richiesta viene reindirizzata automaticamente tramite il servizio token di sicurezza per stabilire le credenziali senza una pagina di accesso:  
  
 ![Diagramma che mostra Accedi con reindirizzamento passivo.](./media/wsfederation-authentication-module-overview/sign-in-using-passive-redirect.gif)  
  
 Il diagramma seguente mostra in modo più dettagliato ciò che succede quando l'utente ha eseguito l'autenticazione nel servizio token di sicurezza e i relativi token di sicurezza vengono elaborati da <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>:  
  
 ![Diagramma temporale per l'elaborazione del token con reindirizzamento passivo](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.gif "SignInUsingPassiveRedirect_TokenProcessing")  
  
 Il diagramma seguente mostra in modo più dettagliato ciò che succede quando i token di sicurezza dell'utente sono stati serializzati nei cookie e intercettati da <xref:System.IdentityModel.Services.SessionAuthenticationModule>:  
  
 ![Diagramma temporale SAM che mostra l'accesso tramite controlli](../../../docs/framework/security/media/signinusingconrols-sam.gif "SignInUsingConrols_SAM")  
  
### <a name="events"></a>Eventi  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>, <xref:System.IdentityModel.Services.SessionAuthenticationModule> e la relativa classe padre <xref:System.IdentityModel.Services.HttpModuleBase> generano eventi in corrispondenza di varie fasi dell'elaborazione di una richiesta HTTP. È possibile gestire questi eventi nel file `global.asax` dell'applicazione [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
- L'infrastruttura ASP.NET richiama il metodo <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> del modulo per inizializzare il modulo.  
  
- L'evento <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=nameWithType> viene generato quando l'infrastruttura ASP.NET richiama il metodo <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> per la prima volta in uno dei moduli dell'applicazione che derivano da <xref:System.IdentityModel.Services.HttpModuleBase>. Questo metodo accede alla proprietà <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> statica, che comporta il caricamento della configurazione dal file Web.config. Questo evento viene generato solo quando si accede a questa proprietà per la prima volta. All'oggetto <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> inizializzato dalla configurazione è possibile accedere tramite la proprietà <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> in un gestore eventi. È possibile usare questo evento per modificare la configurazione prima che venga applicata ai moduli. È possibile aggiungere un gestore per questo evento nel metodo Application_Start:  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     Ogni modulo esegue l'override dei metodi astratti <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=nameWithType> e <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=nameWithType>. Il primo di questi metodi aggiunge i gestori per gli eventi della pipeline ASP.NET rilevanti per il modulo. Nella maggior parte dei casi, è sufficiente l'implementazione predefinita del modulo. Il secondo di questi metodi inizializza le proprietà del modulo dalla relativa proprietà <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=nameWithType>. Si tratta di una copia della configurazione caricata in precedenza. Potrebbe essere necessario eseguire l'override di questo secondo metodo, se si vuole supportare l'inizializzazione di nuove proprietà dalla configurazione nelle classi derivate da <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> o <xref:System.IdentityModel.Services.SessionAuthenticationModule>. In casi di questo tipo, è anche necessario derivare dagli oggetti di configurazione appropriati per supportare le proprietà di configurazione aggiunte, ad esempio da <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> o <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
- WS-FAM genera l'evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived> quando intercetta un token di sicurezza che è stato rilasciato dal servizio token di sicurezza.  
  
- WS-FAM genera l'evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated> dopo la convalida del token.  
  
- <xref:System.IdentityModel.Services.SessionAuthenticationModule> genera l'evento <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated> quando crea un token di sicurezza della sessione per l'utente.  
  
- <xref:System.IdentityModel.Services.SessionAuthenticationModule> genera l'evento <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived> quando intercetta le richieste successive con il cookie contenente il token di sicurezza della sessione.  
  
- Prima di reindirizzare l'utente all'autorità di certificazione, WS-FAM genera l'evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>. La richiesta di accesso WS-Federation è disponibile tramite la proprietà <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> dell'oggetto <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> passato nell'evento. È possibile scegliere di modificare la richiesta prima di inviarla all'autorità di certificazione.  
  
- WS-FAM genera l'evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn> quando il cookie è stato scritto correttamente e l'utente ha effettuato l'accesso.  
  
- WS-FAM genera l'evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> una volta per ogni sessione quando la sessione viene chiusa per ogni utente. L'evento non viene generato se la sessione viene chiusa sul lato client (ad esempio, eliminando il cookie di sessione). In un ambiente SSO il servizio token di sicurezza del provider di identità può richiedere anche la disconnessione di ogni relying party. Anche in questo caso viene generato l'evento, con il valore di <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> impostato su `true`.  
  
> [!NOTE]
>  Non usare la proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> durante qualsiasi evento generato da <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> o <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Il motivo è che l'impostazione di <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> avviene dopo il processo di autenticazione, mentre gli eventi vengono generati durante il processo di autenticazione.  
  
### <a name="configuration-of-federated-authentication"></a>Configurazione dell'autenticazione federata  
 La configurazione di WS FAM e SAM avviene mediante l'elemento [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md). L'elemento figlio [\<wsFederation>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) configura i valori predefiniti per le proprietà di WS-FAM, ad esempio le proprietà <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> e <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A>. Questi valori possono essere modificati in base alle singole richieste fornendo i gestori per alcuni degli eventi di WS-FAM, ad esempio <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>. Il gestore di cookie usato da SAM viene configurato tramite l'elemento figlio [\<cookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md). WIF fornisce un gestore di cookie predefinito implementato nella classe <xref:System.IdentityModel.Services.ChunkedCookieHandler> le cui dimensioni del blocco possono essere impostate tramite l'elemento [\<chunkedCookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md). L'elemento `<federationConfiguration>` fa riferimento a un oggetto <xref:System.IdentityModel.Configuration.IdentityConfiguration>, che fornisce la configurazione per altri componenti WIF usati nell'applicazione, ad esempio <xref:System.Security.Claims.ClaimsAuthenticationManager> e <xref:System.Security.Claims.ClaimsAuthorizationManager>. È possibile fare riferimento in modo esplicito alla configurazione di identità specificando un elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) denominato nell'attributo `identityConfigurationName` dell'elemento `<federationConfiguration>`. Se non si fa riferimento in modo esplicito alla configurazione di identità, viene usata la configurazione di identità predefinita.  
  
 Il codice XML seguente mostra una configurazione di un'applicazione relying party ASP.NET. Le sezioni di configurazione <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> e <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> vengono aggiunte nell'elemento `<configSections>`. SAM e WS-FAM vengono aggiunti ai moduli HTTP nell'elemento `<system.webServer>`/`<modules>`. Infine, i componenti WIF vengono configurati negli elementi `<system.identityModel>`/`<identityConfiguration>` e `<system.identityModel.services>`/`<federationConfiguration>`. Questa configurazione specifica il gestore di cookie in blocchi come se fosse il gestore di cookie predefinito e non ci fosse un tipo di gestore di cookie specificato nell'elemento `<cookieHandler>`.  
  
> [!WARNING]
>  Nell'esempio seguente sia l'attributo `requireHttps` dell'elemento `<wsFederation>` che l'attributo `requireSsl` dell'elemento `<cookieHandler>` sono `false`. Ciò comporta un potenziale rischio per la sicurezza. In un ambiente di produzione entrambi questi valori devono essere impostati su `true`.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)
