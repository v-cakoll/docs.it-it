---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 2103c32112b6c5554d7b510f486d4cbb1349f35d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747950"
---
# <a name="ltcallbackdebuggt"></a>&lt;callbackDebug&gt;
Specifica il debug del servizio per un oggetto di callback Windows Communication Foundation (WCF).  
  
 \<system.ServiceModel>  
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
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>
