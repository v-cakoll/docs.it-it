---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251765"
---
# <a name="tokenreplaydetection"></a>\<tokenReplayDetection>
Abilita il rilevamento della riproduzione dei token e specifica l'ora di scadenza per i token.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayDetection**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Type  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|enabled|Valore che specifica se il rilevamento della riproduzione del token è abilitato; "true" per abilitare il rilevamento della riproduzione del token.|  
|expirationPeriod|Oggetto <xref:System.TimeSpan> che specifica l'intervallo di tempo massimo prima che un elemento venga considerato scaduto e rimosso dalla cache.  Per ulteriori informazioni su come specificare <xref:System.TimeSpan> i valori, vedere [valori TimeSpan](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Specifica le impostazioni di identità a livello di servizio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Fornisce la configurazione per una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 Un `<tokenReplayDetection>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento. Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.  
  
 Il tipo della cache di riproduzione dei token viene specificato dall' [ \<elemento > tokenReplayCache](tokenreplaycache.md) .
