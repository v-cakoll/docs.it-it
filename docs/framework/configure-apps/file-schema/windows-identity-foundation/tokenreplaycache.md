---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e43e79416ddb8862cbc6e52d9d449a02b123af83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.  
  
 \<System. IdentityModel >  
\<identityConfiguration >  
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
|type|Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe. Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
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
