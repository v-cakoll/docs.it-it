---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 853dc9817d080e59ac7a792576eda862bd0b1f1d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252035"
---
# \<cookieHandler>
Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> usato da (Sam) per la lettura e la scrittura dei cookie.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cookieHandler>**  
  
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
|path|Specifica il valore del percorso per tutti i cookie scritti. Il valore predefinito è "HttpRuntime. AppDomainAppVirtualPath".|  
|mode|Uno dei <xref:System.IdentityModel.Services.CookieHandlerMode> valori di che specifica il tipo di gestore di cookie utilizzato da Sam. È possibile utilizzare i valori seguenti:<br /><br /> -"Default", uguale a "Chunked".<br />-"Chunked" — usa un'istanza della <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Questo gestore di cookie garantisce che i singoli cookie non superino la dimensione massima impostata. Questo consente di eseguire questa operazione suddividendo potenzialmente un cookie logico in un numero di cookie in transito.<br />-"Custom": usa un'istanza di una classe personalizzata derivata da <xref:System.IdentityModel.Services.CookieHandler> . L'elemento figlio fa riferimento alla classe derivata `<customCookieHandler>` .<br /><br /> Il valore predefinito è "default".|  
|persistentSessionLifetime|Specifica la durata delle sessioni permanenti. Se zero, vengono utilizzate sempre sessioni temporanee. Il valore predefinito è "0:0:0", che specifica una sessione temporanea. Il valore massimo è "365:0:0", che specifica una sessione di 365 giorni. Il valore deve essere specificato in base alla restrizione seguente: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />` , dove il valore più a sinistra specifica Days, il valore intermedio (se presente) specifica le ore e il valore più a destra (se presente) specifica i minuti.|  
|requireSsl|Specifica se il flag "protetto" viene emesso per tutti i cookie scritti. Se questo valore è impostato, i cookie della sessione di accesso saranno disponibili solo tramite HTTPS. Il valore predefinito è "true".|  
|hideFromScript|Controlla se il flag "HttpOnly" viene emesso per tutti i cookie scritti. Alcuni Web browser rispettano questo flag mantenendo lo script sul lato client dall'accesso al valore del cookie. Il valore predefinito è "true".|  
|dominio|Valore del dominio per tutti i cookie scritti. Il valore predefinito è "".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|Configura <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Questo elemento può essere presente solo se l' `mode` attributo dell' `<cookieHandler>` elemento è "default" o "Chunked".|  
|[\<customCookieHandler>](customcookiehandler.md)|Imposta il tipo di gestore di cookie personalizzato. Questo elemento deve essere presente se l' `mode` attributo dell' `<cookieHandler>` elemento è "Custom". Non può essere presente per tutti gli altri valori dell' `mode` attributo. Il tipo personalizzato deve derivare dalla <xref:System.IdentityModel.Services.CookieHandler> classe.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam).|  
  
## <a name="remarks"></a>Commenti  
 <xref:System.IdentityModel.Services.CookieHandler>È responsabile della lettura e della scrittura di cookie non elaborati a livello di protocollo http. È possibile configurare un <xref:System.IdentityModel.Services.ChunkedCookieHandler> gestore di cookie personalizzato derivato dalla <xref:System.IdentityModel.Services.CookieHandler> classe.  
  
 Per configurare un gestore di cookie in blocchi, impostare l'attributo mode su "Chunked" o "default". Le dimensioni predefinite del blocco sono pari a 2000 byte, ma è possibile specificare facoltativamente una dimensione del blocco diversa includendo un `<chunkedCookieHandler>` elemento figlio.  
  
 Per configurare un gestore di cookie personalizzato, impostare l'attributo mode su "Custom". È inoltre necessario specificare un `<customCookieHandler>` elemento figlio che fa riferimento al tipo del gestore personalizzato.  
  
 L' `<cookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.CookieHandlerElement> classe. Il gestore di cookie specificato nella configurazione è disponibile dalla <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> proprietà dell' <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto impostato nella <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Proprietà.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato un `<cookieHandler>` elemento. In questo esempio, poiché l' `mode` attributo non è specificato, il gestore di cookie predefinito verrà usato da Sam. Si tratta di un'istanza della <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe. Poiché l' `<chunkedCookieHandler>` elemento figlio non è specificato, verranno usate le dimensioni predefinite del blocco. HTTPS non sarà necessario perché l' `requireSsl` attributo è impostato `false` .  
  
> [!WARNING]
> In questo esempio, HTTPS non è necessario per scrivere cookie di sessione. Questo è dovuto al fatto `requireSsl` che l'attributo dell' `<cookieHandler>` elemento è impostato su `false` . Questa impostazione non è consigliata per la maggior parte degli ambienti di produzione perché può presentare un rischio per la sicurezza.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
