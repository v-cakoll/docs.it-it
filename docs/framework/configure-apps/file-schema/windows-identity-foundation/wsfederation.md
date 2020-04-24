---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152463"
---
# <a name="wsfederation"></a>\<> di wsFederation
Fornisce la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> configurazione per (WSFAM).  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<System. identityModel. Services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>federationConfiguration**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di wsFederation**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Description|  
|---------------|-----------------|  
|authenticationType|URI che specifica il tipo di autenticazione. Imposta il parametro wauth della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wauth non è incluso nella richiesta.|  
|aggiornamento|La durata massima desiderata delle richieste di autenticazione, in minuti. Imposta il parametro wfresh della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è zero. Facoltativo. **Avviso:**  Nella prossima versione di .NET Framework 4,5, l' `freshness` attributo sarà di tipo `xs:string` e il valore predefinito sarà. `null`|  
|homeRealm|Area di autenticazione principale del provider di identità (IdP) da usare per l'autenticazione. Imposta il parametro whr della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro whr non è incluso nella richiesta.|  
|autorità di certificazione|URI dell'emittente del token previsto. Imposta l'URL di base delle richieste di accesso WS-Federation e richieste di disconnessione obbligatorie.|  
|persistentCookiesOnPassiveRedirects|Specifica se i cookie permanenti vengono emessi per l'autenticazione. Facoltativo. Il valore predefinito è "false" e i cookie non vengono emessi.|  
|passiveRedirectEnabled|Specifica se WSFAM è abilitato per il reindirizzamento automatico di richieste non autorizzate a un servizio token di accesso. Facoltativo. Il valore predefinito è "true", le richieste non autorizzate vengono reindirizzate automaticamente.|  
|policy|URL che specifica la posizione dei criteri rilevanti da usare per le richieste di accesso. Il valore predefinito è una stringa vuota. Imposta il parametro wp della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro WP non è incluso nella richiesta.|  
|realm|URI dell'area di autenticazione richiedente. URI che identifica il relying party (RP) per il servizio token di sicurezza (STS). Imposta il parametro della richiesta di accesso WS-Federation della richiesta wtrealm. Obbligatorio.|  
|risposta|URL che identifica l'indirizzo a cui l'applicazione del componente desidera ricevere le risposte dal servizio token di sicurezza (STS). Imposta il parametro wreply della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreply non è incluso nella richiesta.|  
|richiesta|Richiesta di rilascio di token. Imposta il parametro wreq della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreq non è incluso nella richiesta. Se non si include il wreq o il parametro wreqptr nella richiesta, il servizio token di servizio è in grado di riconoscere il tipo di token da emettere.|  
|requestPtr|URL che specifica il percorso della richiesta di pubblicazione token. Imposta il parametro wreqptr della richiesta. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wreqptr non è incluso nella richiesta. Se non si include il wreq o il parametro wreqptr nella richiesta, il servizio token di servizio è in grado di riconoscere il tipo di token da emettere.|  
|requireHttps|Specifica se la comunicazione con il servizio token di sicurezza (STS) deve usare il protocollo HTTPS. Facoltativo. Il valore predefinito è "true". è necessario usare HTTPS.|  
|risorse|URI che identifica la risorsa a cui si accede, il componente e il servizio token di sicurezza (STS). Facoltativo. Imposta il parametro wres della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che il parametro wres non è incluso nella richiesta. **Nota:** WRES è un parametro legacy. Specificare l' `realm` attributo per usare invece il parametro wtrealm.|  
|signInQueryString|Fornisce un punto di estendibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che non deve essere incluso alcun parametro aggiuntivo nella richiesta. I parametri vengono specificati come frammento di stringa di query usando il formato `"param1=value1&param2=value2&param3=value3"` seguente: e così via. **Nota:**  In un file di configurazione è necessario specificare il carattere ' &' nella stringa di query usando il relativo riferimento `&`all'entità,.|  
|signOutQueryString|Fornisce un punto di estendibilità per specificare i parametri di query definiti dall'applicazione nell'URL della richiesta di accesso WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che non deve essere incluso alcun parametro aggiuntivo nella richiesta. I parametri vengono specificati come frammento di stringa di query usando il formato `"param1=value1&param2=value2&param3=value3"` seguente: e così via. **Nota:**  In un file di configurazione è necessario specificare il carattere ' &' nella stringa di query usando il relativo riferimento `&`all'entità,.|  
|signOutReply|Specifica l'URL a cui il client deve essere reindirizzato dal servizio token di sicurezza (STS) durante la disconnessione passiva tramite il protocollo WS-Federation. Imposta il parametro wreply su una richiesta di disconnessione WS-Federation. Facoltativo. Il valore predefinito è una stringa vuota, che specifica che non deve essere incluso alcun parametro aggiuntivo nella richiesta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>federationConfiguration](federationconfiguration.md)|Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam).|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile utilizzare l' `<wsFederation>` elemento per configurare le impostazioni predefinite dei parametri WS-Federation e il comportamento predefinito per WSFAM. Le impostazioni dei parametri WS-Federation definite `<wsFederation>` sotto le proprietà equivalenti del set <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> di elementi esposte dalla classe. Queste proprietà rimangono invariate per ogni richiesta rilasciata da WSFAM. È possibile modificare i parametri di WS-Federation in modo dinamico durante l'elaborazione della richiesta aggiungendo gestori eventi per gli eventi esposti da WSFAM; ad esempio, l' <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> evento. Per ulteriori informazioni, vedere la documentazione relativa alla <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> classe.  
  
 L' `<wsFederation>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.WSFederationElement> classe. L'oggetto di configurazione stesso è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> classe. Una singola <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> istanza viene impostata sull' <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto a cui si accede tramite la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce la configurazione per WSFAM.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene `<wsFederation>` mostrato un elemento che specifica le impostazioni per WSFAM.  
  
> [!WARNING]
> In questo esempio, WSFAM non è necessario per usare HTTPS. Questo è dovuto al `requireHttps` fatto che l' `<wsFederation>` attributo dell'elemento `false`è impostato. Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione perché può presentare un rischio per la sicurezza.  
  
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

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
