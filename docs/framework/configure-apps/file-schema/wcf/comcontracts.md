---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69919480"
---
# \<comContracts>
La sezione di configurazione `comContracts` contiene elementi che consentono di specificare varie proprietà di un contratto di servizio COM+ Integration.  
  
## <a name="specifying-namespace-and-contract"></a>Specifica di spazio dei nomi e contratto  
 I contratti di servizio COM+ Integration sono attualmente limitati allo `http://tempuri.org` spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto. È tuttavia possibile specificare alternative usando la sezione `comContracts` nel file di configurazione.  
  
 Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi e il nome del contratto di servizio, oltre a un'opzione per imporre l'uso di associazioni con sessione.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.  
  
 Quando questa sezione è vuota, l'inizializzazione del servizio applica uno spazio dei nomi e un nome del contratto predefiniti presi dall'ID dell'interfaccia COM di supporto.  
  
 Inoltre, è possibile utilizzare l' [\<exposedMethod>](exposedmethod.md) elemento per specificare i metodi COM+ esposti quando l'interfaccia in un componente COM+ viene esposta come un servizio Web. È anche possibile usare [\<persistableTypes>](persistabletypes.md) per specificare i tipi salvatibili usati nell'integrazione. Infine, è possibile utilizzare l' [\<userDefinedType>](userdefinedtype.md) elemento per includere i tipi definiti dall'utente (UDT) da includere nel contratto di servizio.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [Integrazione con applicazioni COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: configurare le impostazioni del servizio COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
