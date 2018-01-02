---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccb48efcdd1924ade27220a685e146a7f5eeef76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcallbackdebuggt"></a>&lt;callbackDebug&gt;
Specifica il debug del servizio per un oggetto di callback [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<callbackDebug >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|Valore che specifica se oggetti callback del client restituiscono al servizio informazioni sulle eccezioni gestite negli errori SOAP.<br /><br /> Se questo attributo viene impostato su `true` a livello di programmazione, è possibile abilitare il flusso di informazioni sulle eccezioni gestite in un oggetto callback del client nel servizio a fini di debug. **Attenzione:** la restituzione ai client informazioni sulle eccezioni gestite può costituire un rischio di sicurezza. Questo perché i dettagli delle eccezioni espongono informazioni sull'implementazione interna del servizio che potrebbero venire usate da client non autorizzati.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
