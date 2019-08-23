---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 8fcb5ac0c552d1ac2e849c95a5c0757d0c142f3d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926390"
---
# <a name="behaviors"></a>\<comportamenti >
Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.  Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi. Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.|  
|[\<serviceBehaviors>](servicebehaviors.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Note  
 È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta. A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.  È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Configurazione ed estensione del runtime con i comportamenti](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [Configurazione dei comportamenti client](../../../wcf/configuring-client-behaviors.md)
- [Specifica del comportamento in fase di esecuzione dei client](../../../wcf/specifying-client-run-time-behavior.md)
- [Specifica del comportamento in fase di esecuzione del servizio](../../../wcf/specifying-service-run-time-behavior.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
