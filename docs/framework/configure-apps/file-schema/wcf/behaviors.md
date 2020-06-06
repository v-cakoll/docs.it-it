---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139696"
---
# \<behaviors>
Questo elemento definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.  Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi. Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
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
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un endpoint specifico.|  
|[\<serviceBehaviors>](servicebehaviors.md)|Questa sezione di configurazione rappresenta tutti i comportamenti definiti per un servizio specifico.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Commenti  
 È possibile usare l'elemento `<remove>` per rimuovere un determinato comportamento dalla raccolta. A tale scopo, è sufficiente fornire il nome del comportamento da rimuovere nell'attributo `name` dell'elemento `<remove>`.  È inoltre possibile usare l'elemento `<clear>` per garantire che una raccolta di comportamenti venga avviata vuota cancellando tutto il contenuto della raccolta.  
  
## <a name="see-also"></a>Vedi anche

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
