---
title: '&lt;i comportamenti&gt; del flusso di lavoro'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40278c0a3d99dd5c37df1d642b8a2e13e9f62633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;i comportamenti&gt; del flusso di lavoro
Questo elemento contiene il **serviceBehaviors** insieme.  Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro. Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.  
  
 \<System. ServiceModel >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [La configurazione e l'estensione del Runtime dei comportamenti](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
