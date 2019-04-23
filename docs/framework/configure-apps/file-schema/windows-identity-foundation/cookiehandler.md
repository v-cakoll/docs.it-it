---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 5238ea7b96c09fb976a25bc00b952539ddd44b49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115154"
---
# <a name="cookiehandler"></a>\<cookieHandler>
Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) utilizzato per leggere e scrivere i cookie.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Specifica il nome di base per i cookie scritti. Il valore predefinito è "FedAuth".|  
|path|Specifica il valore di percorso per i cookie scritti. Il valore predefinito è "HttpRuntime.AppDomainAppVirtualPath".|  
|modalità|Uno del <xref:System.IdentityModel.Services.CookieHandlerMode> valori che specifica il tipo di gestore di cookie usato da SAM. Possono essere utilizzati i valori seguenti:<br /><br /> -"Default", ovvero lo stesso come "Chunked".<br />-"Chunked", ovvero viene utilizzata un'istanza di <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Questo gestore di cookie che garantisce che singoli cookie non superino una set di dimensioni massime. Per ottenere questo risultato potenzialmente "blocco" un cookie logico in un numero di cookie in transito.<br />-"Custom", viene usata un'istanza di una classe personalizzata derivata da <xref:System.IdentityModel.Services.CookieHandler>. Fa riferimento la classe derivata di `<customCookieHandler>` elemento figlio.<br /><br /> Il valore predefinito è "Default".|  
|persistentSessionLifetime|Specifica la durata delle sessioni persistenti. Se è zero, vengono utilizzate sempre sessioni temporanee. Il valore predefinito è "valore 0:0:0", che specifica una sessione temporanea. Il valore massimo è "365:0:0", che specifica una sessione di 365 giorni. Il valore deve essere specificato in base alla restrizione seguente: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, in cui il valore più a sinistra specifica giorni, il valore medio (se presente) specifica le ore e il valore più a destra, se presente, specifica i minuti.|  
|requireSsl|Specifica se il flag "Secure" viene generato per i cookie scritti. Se questo valore è impostato, i cookie di sessione di accesso sarà disponibili solo tramite HTTPS. Il valore predefinito è "true".|  
|hideFromScript|Controlla se il flag "HttpOnly" viene generato per i cookie scritti. Alcuni web browser rispetta questo flag, mantenendo script lato client il valore del cookie di accesso. Il valore predefinito è "true".|  
|dominio|Il valore di dominio per i cookie scritti. Il valore predefinito è "".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".|  
|[\<customCookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Imposta il tipo di gestore di cookie personalizzato. Questo elemento deve essere presente se la `mode` attributo del `<cookieHandler>` elemento è "Custom". Non può essere presente per tutti gli altri valori del `mode` attributo. Il tipo personalizzato deve derivare dal <xref:System.IdentityModel.Services.CookieHandler> classe.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Note  
 Il <xref:System.IdentityModel.Services.CookieHandler> è responsabile della lettura e scrittura di un cookie non elaborato a HTTP a livello di protocollo. È possibile configurare un <xref:System.IdentityModel.Services.ChunkedCookieHandler> o un gestore di cookie personalizzato derivato dal <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 Per configurare un gestore di cookie chunked, impostare l'attributo mode su "Chunked" o "Default". Le dimensioni del blocco predefinito sono 2000 byte, ma è possibile specificare facoltativamente una dimensione del blocco diverso includendo un `<chunkedCookieHandler>` elemento figlio.  
  
 Per configurare un gestore di cookie personalizzato, impostare l'attributo mode su "Custom". È necessario specificare anche un `<customCookieHandler>` elemento figlio che fa riferimento al tipo del gestore personalizzato.  
  
 Il `<cookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Services.CookieHandlerElement> classe. Il gestore di cookie che è stato specificato nella configurazione è disponibile il <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> proprietà del <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> impostate al <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<cookieHandler>` elemento. In questo esempio, in quanto il `mode` attributo viene omesso, il gestore di cookie predefinito verrà usato da SAM. Si tratta di un'istanza di <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Poiché il `<chunkedCookieHandler>` elemento figlio non viene specificato, le dimensioni del blocco predefinita verranno usata. HTTPS non è necessario perché il `requireSsl` attributo è impostato `false`.  
  
> [!WARNING]
>  In questo esempio, HTTPS non è necessario scrivere i cookie di sessione. Infatti il `requireSsl` attributo la `<cookieHandler>` elemento è impostato su `false`. Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione, come può costituire un rischio di sicurezza.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
