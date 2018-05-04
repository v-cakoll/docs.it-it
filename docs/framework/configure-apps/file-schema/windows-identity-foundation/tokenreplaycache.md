---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<memorizza nella cache >  
\<tokenReplayCache >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|tipo|Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe. Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<memorizza nella cache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra la cache utilizzate da un servizio o una raccolta di gestore del token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 La cache di riproduzione token viene utilizzata per rilevare i token riprodotti. Rilevamento riproduzione token è abilitato per il [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento specifica anche l'ora di scadenza massimo per i token.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrata la configurazione di una cache per il rilevamento riproduzione token personalizzata.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
