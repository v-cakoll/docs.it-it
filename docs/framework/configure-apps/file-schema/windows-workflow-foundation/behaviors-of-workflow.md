---
title: '&lt;i comportamenti&gt; del flusso di lavoro'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b4ad7fb54cc8a03f5dd698055da5a29e719775c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731673"
---
# <a name="ltbehaviorsgt-of-workflow"></a>&lt;i comportamenti&gt; del flusso di lavoro
Questo elemento contiene il **serviceBehaviors** raccolta.  Ogni elemento della raccolta definisce elementi di comportamento utilizzati dai servizi flusso di lavoro. Ogni elemento di comportamento è identificato dal relativo univoco **nome** attributo.  
  
 \<system.ServiceModel>  
  
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
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio flusso di lavoro specifico.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Elemento radice di tutti gli elementi di configurazione del flusso di lavoro.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Configurazione ed estensione del runtime con i comportamenti](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
