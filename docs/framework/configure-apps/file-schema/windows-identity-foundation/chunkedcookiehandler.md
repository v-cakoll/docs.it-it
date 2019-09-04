---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252113"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
<xref:System.IdentityModel.Services.ChunkedCookieHandler>Configura. Questo elemento può essere presente solo se l' `mode` attributo `<cookieHandler>` dell'elemento è "default" o "Chunked".  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cookieHandler**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> chunkedCookieHandler**  
  
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
|chunkSize|Dimensione massima, in caratteri, dei dati del cookie HTTP per un cookie HTTP. È necessario prestare attenzione quando si modificano le dimensioni del blocco. I Web browser hanno limiti diversi sulle dimensioni dei cookie e sul numero consentito per dominio. Ad esempio, la specifica Netscape originale ha stabilito questi limiti: 300 cookie totali, 4096 byte per intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio. Il valore predefinito è 2000. Richiesto.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura l'oggetto <xref:System.IdentityModel.Services.CookieHandler> usato da <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) per la lettura e la scrittura dei cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> oggetto impostando `mode` l'attributo dell' `<cookieHandler>` elemento su "default" o "Chunked", è possibile specificare la dimensione del blocco utilizzata dal gestore di cookie per leggere e scrivere cookie includendo `<chunkedCookieHandler>` un elemento figlio e impostazione del `chunkSize` relativo attributo. Se l' `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione del blocco predefinita di 2000 byte. Impossibile specificare questo elemento quando l' `mode` attributo è impostato su "Custom".  
  
 L' `<chunkedCookieHandler>` elemento è rappresentato <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> dalla classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene configurato un gestore di cookie Chunked che scrive cookie in blocchi di 3000 byte.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
