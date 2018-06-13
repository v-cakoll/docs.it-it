---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 193b783e44fe4386d3575e180dc5baa6a7f9a8be
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758373"
---
# <a name="ltchunkedcookiehandlergt"></a>&lt;chunkedCookieHandler&gt;
Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".  
  
 \<IdentityModel >  
\<federationConfiguration >  
\<cookieHandler >  
\<chunkedCookieHandler >  
  
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
|chunkSize|Dimensione massima in caratteri, di dati dei cookie HTTP per di un cookie HTTP. È necessario prestare attenzione quando si modifica la dimensione del blocco. Browser Web hanno limiti diversi sulle dimensioni dei cookie e il numero consentito per ogni dominio. Ad esempio, la specifica Netscape originale stipulata questi limiti: 300 cookie totali, pari a 4.096 byte per ogni intestazione cookie (inclusi i metadati, non solo il valore del cookie) e 20 cookie per dominio. Il valore predefinito è 2000. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura il <xref:System.IdentityModel.Services.CookieHandler> che il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) viene utilizzato per leggere e scrivere i cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> impostando il `mode` attributo del `<cookieHandler>` elemento da "Default" o "Chunked", è possibile specificare le dimensioni del blocco utilizzata dal gestore di cookie per leggere e scrivere i cookie includendo un `<chunkedCookieHandler>` elemento figlio e l'impostazione relativa `chunkSize` attributo. Se il `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione di blocco predefinito di 2000 byte. Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Custom".  
  
 Il `<chunkedCookieHandler>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di configurare un gestore di cookie in blocchi che scrive i cookie in blocchi di 3000 byte.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
