---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252113"
---
# \<chunkedCookieHandler>
Configura <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Questo elemento può essere presente solo se l' `mode` attributo dell' `<cookieHandler>` elemento è "default" o "Chunked".  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|chunkSize|Dimensione massima, in caratteri, dei dati del cookie HTTP per un cookie HTTP. È necessario prestare attenzione quando si modificano le dimensioni del blocco. I Web browser hanno limiti diversi sulle dimensioni dei cookie e sul numero consentito per dominio. Ad esempio, la specifica Netscape originale ha stabilito questi limiti: 300 cookie totali, 4096 byte per intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio. Il valore predefinito è 2000. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> usato da (Sam) per la lettura e la scrittura dei cookie.|  
  
## <a name="remarks"></a>Commenti  
 Quando si specifica un oggetto impostando <xref:System.IdentityModel.Services.ChunkedCookieHandler> l' `mode` attributo dell' `<cookieHandler>` elemento su "default" o "Chunked", è possibile specificare la dimensione del blocco utilizzata dal gestore di cookie per leggere e scrivere cookie includendo un `<chunkedCookieHandler>` elemento figlio e impostando il relativo `chunkSize` attributo. Se l' `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione del blocco predefinita di 2000 byte. Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Custom".  
  
 L' `<chunkedCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene configurato un gestore di cookie Chunked che scrive cookie in blocchi di 3000 byte.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
