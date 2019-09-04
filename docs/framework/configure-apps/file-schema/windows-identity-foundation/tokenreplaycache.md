---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251777"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache>
Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memorizza nella cache >** ](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayCache**  
  
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
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Tipo che deriva dalla <xref:System.IdentityModel.Tokens.TokenReplayCache> classe. Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti ai tipi personalizzati].
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.|  
  
## <a name="remarks"></a>Note  
 La cache di riproduzione dei token viene utilizzata per rilevare i token riprodotti. Il rilevamento riproduzione token è abilitato dall'elemento [ >tokenReplayDetection,chespecificaanchelascadenzamassimaperitoken\<](tokenreplaydetection.md) .  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per il rilevamento dei token riprodotti.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
