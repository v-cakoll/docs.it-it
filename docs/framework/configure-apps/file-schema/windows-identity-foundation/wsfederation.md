---
title: '&lt;wsFederation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e4779baa24e172affad2ed5e04451ad791d7cdf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
Fornisce la configurazione per il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<System >  
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
|authenticationType|URI che specifica il tipo di autenticazione. Imposta il parametro wauth richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wauth non è incluso nella richiesta.|  
|validità minima|La massima durata desiderata delle richieste di autenticazione, in minuti. Imposta il parametro wfresh richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è zero. Parametro facoltativo. **Avviso:** nella prossima versione di .NET Framework 4.5, il `freshness` attributo sarà di tipo `xs:string` e il valore predefinito sarà `null`.|  
|protezione homeRealm|L'area di autenticazione principale del provider di identità (IP) da utilizzare per l'autenticazione. Imposta il parametro whr richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro whr non è incluso nella richiesta.|  
|issuer|L'URI dell'emittente del token previsto. Imposta la base richieste di URL di WS-Federation e richieste di disconnessione necessari.|  
|persistentCookiesOnPassiveRedirects|Specifica se i cookie permanenti vengono eseguiti sull'autenticazione. Parametro facoltativo. Il valore predefinito è "false", non vengono emessi i cookie.|  
|passiveRedirectEnabled|Specifica se il WSFAM è abilitato per reindirizzare automaticamente le richieste non autorizzate per un servizio token di sicurezza. Parametro facoltativo. Il valore predefinito è "true", verranno reindirizzate automaticamente le richieste non autorizzate.|  
|criteri|URL che specifica il percorso del relativo al criterio da utilizzare per le richieste di accesso. Il valore predefinito è una stringa vuota. Imposta il parametro wp richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wp non è incluso nella richiesta.|  
|realm|L'URI dell'area di autenticazione richiesta. (Un URI che identifica la relying party (RP) al servizio token di sicurezza (STS)). Imposta il parametro di richiesta wtrealm WS-Federation sign-in richiesta. Obbligatorio.|  
|risposta|Un URL che identifica l'indirizzo in corrispondenza del quale si desidera ricevere le risposte dal servizio Token sicurezza (STS) all'applicazione relying party (RP). Imposta il parametro wreply richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreply non è incluso nella richiesta.|  
|richiesta|La richiesta di rilascio dei token. Imposta il parametro wreq richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreq non è incluso nella richiesta. Escluso il wreq o il parametro wreqptr nella richiesta implica che il servizio token di sicurezza riconosce il tipo di token da emettere.|  
|requestPtr|Un URL che specifica il percorso della richiesta di rilascio dei token. Imposta il parametro wreqptr richiesta. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreqptr non è incluso nella richiesta. Escluso il wreq o il parametro wreqptr nella richiesta implica che il servizio token di sicurezza riconosce il tipo di token da emettere.|  
|requireHttps|Specifica se la comunicazione con il servizio token di sicurezza (STS) deve usare il protocollo HTTPS. Parametro facoltativo. Il valore predefinito è "true", è necessario utilizzare HTTPS.|  
|risorsa|Un URI che identifica la risorsa di cui si accede, relying party (RP), all'al servizio token di sicurezza (STS). Parametro facoltativo. Imposta il parametro wres richiesta di accesso di WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wres non è incluso nella richiesta. **Nota:** wres è un parametro legacy. Specificare il `realm` attributo invece di utilizzare il parametro wtrealm.|  
|signInQueryString|Fornisce un punto di estensibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessuna parametri aggiuntivi devono essere inclusi nella richiesta. I parametri vengono specificati come un frammento di stringa di query utilizzando il formato seguente: `"param1=value1&param2=value2&param3=value3"` e così via. **Nota:** In un file di configurazione di "&" carattere nella stringa di query deve essere specificata utilizzando il relativo riferimento all'entità, `&`.|  
|signOutQueryString|Fornisce un punto di estensibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessuna parametri aggiuntivi devono essere inclusi nella richiesta. I parametri vengono specificati come un frammento di stringa di query utilizzando il formato seguente: `"param1=value1&param2=value2&param3=value3"` e così via. **Nota:** In un file di configurazione di "&" carattere nella stringa di query deve essere specificata utilizzando il relativo riferimento all'entità, `&`.|  
|signOutReply|Specifica l'URL a cui il client deve essere reindirizzato dal servizio token di sicurezza (STS) durante la disconnessione tramite il protocollo WS-Federation passivo. Imposta il parametro wreply su una richiesta di disconnessione WS-Federation. Parametro facoltativo. Il valore predefinito è una stringa vuota, che specifica che nessuna parametri aggiuntivi devono essere inclusi nella richiesta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `<wsFederation>` elemento per configurare le impostazioni predefinite dei parametri di WS-Federation e il comportamento predefinito per il WSFAM. Le impostazioni dei parametri di WS-Federation definiti nel `<wsFederation>` elemento set equivalente proprietà esposte dalla <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> classe. Queste proprietà rimangono invariati per ogni richiesta emessa dal WSFAM. È possibile modificare i parametri di WS-Federation in modo dinamico durante una richiesta di elaborazione mediante l'aggiunta di gestori eventi per gli eventi esposti dal WSFAM; ad esempio, il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> evento. Per ulteriori informazioni, vedere la documentazione per la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> classe.  
  
 Il `<wsFederation>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.WSFederationElement> classe. L'oggetto di configurazione è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> classe. Un singolo <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> istanza è impostata sul <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto cui si accede tramite il <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce la configurazione per il WSFAM.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<wsFederation>` elemento che specifica le impostazioni per il WSFAM.  
  
> [!WARNING]
>  In questo esempio, il WSFAM non è necessario utilizzare il protocollo HTTPS. In questo modo il `requireHttps` attributo la `<wsFederation>` viene impostato `false`. Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione, come possono presentare un rischio per la sicurezza.  
  
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
