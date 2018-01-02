---
title: Elemento &lt;synchronousReceive&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63923121ae96b85bd192899a8d8ad285a3ad5b2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsynchronousreceivegt-element"></a>Elemento &lt;synchronousReceive&gt;
Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client. Non prevede attributi o elementi figlio.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<synchronousReceive >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="remarks"></a>Note  
 Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona. In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] viene emesso un nuovo thread per la distribuzione per ogni canale accettato. Se esistono molti canali, sussiste la possibilità di esaurire i thread.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
