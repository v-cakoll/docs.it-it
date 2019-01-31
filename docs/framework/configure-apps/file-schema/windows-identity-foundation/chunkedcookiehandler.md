---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 383ce39816ec7d3f2567765549b537073ee7e081
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277030"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
Configura il <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Questo elemento può essere presente solo se il `mode` attributo del `<cookieHandler>` elemento è "Default" o "Chunked".  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<chunkedCookieHandler>  
  
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
|chunkSize|Le dimensioni massime, in caratteri, i dati di cookie HTTP per di un cookie HTTP. È necessario prestare attenzione quando si modifica la dimensione del blocco. Web browser hanno diversi limiti sulle dimensioni del cookie e il numero consentito per ogni dominio. Ad esempio, la specifica di Netscape originale stipulata questi limiti: Totale 300 cookie, 4096 byte per ogni intestazione del cookie (inclusi i metadati, non solo il valore del cookie) e i 20 cookie per ogni dominio. Il valore predefinito è 2000. Obbligatorio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Consente di configurare il <xref:System.IdentityModel.Services.CookieHandler> che la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) utilizzato per leggere e scrivere i cookie.|  
  
## <a name="remarks"></a>Note  
 Quando si specifica un <xref:System.IdentityModel.Services.ChunkedCookieHandler> impostando la `mode` attributo delle `<cookieHandler>` elemento "Default" o "Chunked", è possibile specificare la dimensione di blocco che il gestore di cookie viene utilizzato per leggere e scrivere i cookie, includendo un `<chunkedCookieHandler>` elemento figlio e l'impostazione relativa `chunkSize` attributo. Se il `<chunkedCookieHandler>` elemento non è presente, viene utilizzata la dimensione di blocco predefinito di 2000 byte. Questo elemento non può essere specificato quando il `mode` attributo è impostato su "Custom".  
  
 Il `<chunkedCookieHandler>` elemento è rappresentato dal <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente configura un gestore di cookie chunked che scrive i cookie in blocchi di 3000 byte.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
