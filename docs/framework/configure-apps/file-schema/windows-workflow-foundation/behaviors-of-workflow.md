---
title: <behaviors> del flusso di lavoro
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790299"
---
# <a name="behaviors-of-workflow"></a>\<i comportamenti > del flusso di lavoro
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
