---
title: '&lt;wsFederation&gt;'
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 66596bbc7171a33318b835a552b7fb364d6833f7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580401"
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
Fornisce la configurazione per il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<IdentityModel >  
\<federationConfiguration >  
\<wsFederation >  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|AuthenticationType|URI che specifica il tipo di autenticazione. Imposta il parametro wauth di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wauth non è incluso nella richiesta.|  
|impostazione della validità|La durata massima desiderata delle richieste di autenticazione, in pochi minuti. Imposta il parametro wfresh di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è zero. Facoltativo. **Avviso:** nella prossima versione di .NET Framework 4.5, le `freshness` attributo sarà di tipo `xs:string` e il relativo valore predefinito sarà `null`.|  
|protezione homeRealm|L'area di autenticazione principale del provider di identità (IP) da usare per l'autenticazione. Imposta il parametro whr di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro whr non è incluso nella richiesta.|  
|issuer|L'URI dell'emittente del token previsto. Imposta la base URL di WS-Federation le richieste di accesso e le richieste di disconnessione necessari.|  
|persistentCookiesOnPassiveRedirects|Specifica se i cookie permanenti vengono eseguiti sull'autenticazione. Facoltativo. Il valore predefinito è "false", non vengono emessi cookie.|  
|passiveRedirectEnabled|Specifica se il WSFAM è abilitato per reindirizzare automaticamente le richieste non autorizzate a un servizio token di sicurezza. Facoltativo. Il valore predefinito è "true", vengono automaticamente reindirizzate le richieste non autorizzate.|  
|criteri|URL che specifica il percorso dei criteri pertinente da utilizzare nelle richieste di accesso. Il valore predefinito è una stringa vuota. Imposta il parametro wp di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wp non è incluso nella richiesta.|  
|realm|L'URI dell'area di autenticazione richiedente. (Un URI che identifica la relying party (RP) al servizio token di sicurezza (STS)). Imposta il parametro wtrealm WS-Federation sign-in richiesta della richiesta. Obbligatorio.|  
|Risposta|URL che identifica l'indirizzo in corrispondenza del quale l'applicazione relying party (RP) desidera ricevere le risposte dal servizio Token sicurezza (STS). Imposta il parametro wreply di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreply non è incluso nella richiesta.|  
|richiesta|La richiesta di rilascio dei token. Imposta il parametro wreq di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreq non è incluso nella richiesta. Escludendo le wreq o il parametro wreqptr nella richiesta implica che il servizio token di sicurezza sa quale tipo di token da emettere.|  
|requestPtr|URL che specifica il percorso della richiesta di rilascio dei token. Imposta il parametro wreqptr della richiesta. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreqptr non è incluso nella richiesta. Escludendo le wreq o il parametro wreqptr nella richiesta implica che il servizio token di sicurezza sa quale tipo di token da emettere.|  
|requireHttps|Specifica se la comunicazione con il servizio token di sicurezza (STS) deve utilizzare il protocollo HTTPS. Facoltativo. Il valore predefinito è "true", è necessario usare HTTPS.|  
|risorsa|Un URI che identifica la risorsa accede, la relying party (RP), delle per il servizio token di sicurezza (STS). Facoltativo. Imposta il parametro wres di richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wres non è incluso nella richiesta. **Nota:** wres è un parametro legacy. Specificare il `realm` attributo da usare invece il parametro wtrealm.|  
|signInQueryString|Fornisce un punto di estensibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessun parametri aggiuntivi da includere nella richiesta. I parametri vengono specificati come un frammento di stringa di query usando il formato seguente: `"param1=value1&param2=value2&param3=value3"` e così via. **Nota:** In un file di configurazione di "&" carattere nella stringa di query deve essere specificata tramite il relativo riferimento di entità, `&`.|  
|signOutQueryString|Fornisce un punto di estensibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessun parametri aggiuntivi da includere nella richiesta. I parametri vengono specificati come un frammento di stringa di query usando il formato seguente: `"param1=value1&param2=value2&param3=value3"` e così via. **Nota:** In un file di configurazione di "&" carattere nella stringa di query deve essere specificata tramite il relativo riferimento di entità, `&`.|  
|signOutReply|Specifica l'URL a cui il client deve essere reindirizzato dal servizio token di sicurezza (STS) durante la disconnessione passiva con il protocollo WS-Federation. Imposta il parametro wreply su una richiesta di disconnessione WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessun parametri aggiuntivi da includere nella richiesta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Note  
 È possibile usare il `<wsFederation>` elemento per configurare le impostazioni predefinite dei parametri di WS-Federation e il comportamento predefinito per il WSFAM. Le impostazioni dei parametri di WS-Federation definite sotto il `<wsFederation>` elemento set equivalente proprietà esposte dal <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> classe. Queste proprietà rimangono gli stessi per ogni richiesta emessa dal WSFAM. È possibile modificare i parametri di WS-Federation in modo dinamico durante l'elaborazione aggiungendo gestori eventi per gli eventi esposti da WSFAM; della richiesta ad esempio, il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> evento. Per altre informazioni, vedere la documentazione per il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> classe.  
  
 Il `<wsFederation>` elemento è rappresentato dal <xref:System.IdentityModel.Services.Configuration.WSFederationElement> classe. L'oggetto di configurazione stesso è rappresentato dal <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> classe. Un singolo <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> istanza è nastavit il <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto a cui si accede tramite il <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce la configurazione per il WSFAM.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<wsFederation>` elemento che specifica le impostazioni per il WSFAM.  
  
> [!WARNING]
>  In questo esempio, il WSFAM non deve usare HTTPS. Infatti il `requireHttps` dell'attributo sul `<wsFederation>` l'elemento viene impostato `false`. Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione, come può costituire un rischio di sicurezza.  
  
```xml
<wsFederation passiveRedirectEnabled="true"   
              issuer="http://localhost:15839/wsFederationSTS/Issue"   
              realm="http://localhost:50969/"   
              reply="http://localhost:50969/"   
              requireHttps="false"   
              signOutReply="http://localhost:50969/SignedOutPage.html"   
              signOutQueryString="Param1=value2&Param2=value2"   
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
