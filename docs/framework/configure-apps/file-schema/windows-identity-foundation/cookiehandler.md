---
title: '&lt;cookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fcdf1e89c3b68daa36ee80fe7234737c61a5a3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758139"
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
Configura il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) viene utilizzato per leggere e scrivere i cookie.  
  
 \<IdentityModel >  
\<federationConfiguration >  
\<cookieHandler >  
  
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
|path|Specifica il valore di percorso per i cookie scritti. Il valore predefinito è "AppDomainAppVirtualPath".|  
|modalità|Uno del <xref:System.IdentityModel.Services.CookieHandlerMode> valori che specifica il tipo di gestore di cookie utilizzato per il modulo SAM. Possono essere utilizzati i valori seguenti:<br /><br /> -"Default", ovvero lo stesso come "Chunked".<br />-"Chunked", ovvero viene utilizzata un'istanza di <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Questo gestore cookie assicura che singoli cookie non superi una dimensione massima del set. Per ottenere questo risultato potenzialmente "suddivisione in blocchi" un cookie logico in un numero di cookie in transito.<br />-"Custom", ovvero viene utilizzata un'istanza di una classe personalizzata derivata da <xref:System.IdentityModel.Services.CookieHandler>. Fa riferimento la classe derivata di `<customCookieHandler>` elemento figlio.<br /><br /> Il valore predefinito è "Default".|  
|persistentSessionLifetime|Specifica la durata delle sessioni permanenti. Se è zero, le sessioni temporanee vengono sempre utilizzate. Il valore predefinito è "0:0:0", che specifica una sessione temporanea. Il valore massimo è "365:0:0", che specifica una sessione di 365 giorni. Il valore deve essere specificato in base alla restrizione seguente: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, dove il valore più a sinistra specifica giorni, il valore medio, se presente, specifica le ore e il valore più a destra, se presente, specifica i minuti.|  
|RequireSsl|Specifica se il flag "Secure" viene generato per i cookie scritti. Se questo valore è impostato, i cookie di sessione di accesso sarà disponibili solo tramite HTTPS. Il valore predefinito è "true".|  
|hideFromScript|Controlla se il flag "HttpOnly" viene generato per i cookie scritti. Alcuni browser rispetta questo flag da impedisce l'accesso al valore di cookie di script sul lato client. Il valore predefinito è "true".|  
|dominio|Il valore di dominio per i cookie scritti. Il valore predefinito è "".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Imposta il tipo di gestore cookie personalizzati. Questo elemento deve essere presentano se la `mode` attributo del `<cookieHandler>` elemento è "Personalizzato". Non può essere presente per tutti gli altri valori del `mode` attributo. Il tipo personalizzato deve essere derivato dalla <xref:System.IdentityModel.Services.CookieHandler> classe.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Note  
 Il <xref:System.IdentityModel.Services.CookieHandler> è responsabile della lettura e scrittura cookie non elaborati a HTTP del livello di protocollo. È possibile configurare un <xref:System.IdentityModel.Services.ChunkedCookieHandler> o un gestore di cookie personalizzato derivato dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 Per configurare un gestore di cookie in blocchi, impostare l'attributo mode "Chunked" o "Default". Le dimensioni del blocco predefinito sono 2000 byte, ma è possibile specificare facoltativamente una dimensione di blocco diverso includendo un `<chunkedCookieHandler>` elemento figlio.  
  
 Per configurare un gestore personalizzato cookie, impostare l'attributo mode su "Custom". È necessario specificare anche un `<customCookieHandler>` elemento figlio che fa riferimento al tipo di gestore personalizzato.  
  
 Il `<cookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.CookieHandlerElement> classe. Il gestore di cookie che è stato specificato nella configurazione è disponibile il <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> proprietà del <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto impostato sul <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<cookieHandler>` elemento. In questo esempio, in quanto il `mode` attributo non è specificato, il gestore di cookie predefinito da utilizzare per il modulo SAM. Si tratta di un'istanza di <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Poiché il `<chunkedCookieHandler>` elemento figlio non viene specificato, le dimensioni del blocco predefinito verranno utilizzata. HTTPS non è necessario perché il `requireSsl` è impostato l'attributo `false`.  
  
> [!WARNING]
>  In questo esempio, HTTPS non è necessario scrivere i cookie di sessione. In questo modo il `requireSsl` attributo la `<cookieHandler>` è impostato su `false`. Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione, come possono presentare un rischio per la sicurezza.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
