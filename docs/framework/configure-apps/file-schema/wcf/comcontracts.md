---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 47a7d862cf85254f88373d582169ff421be2b5b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115830"
---
# <a name="comcontracts"></a>\<comContracts>
La sezione di configurazione `comContracts` contiene elementi che consentono di specificare varie proprietà di un contratto di servizio COM+ Integration.  
  
## <a name="specifying-namespace-and-contract"></a>Specifica di spazio dei nomi e contratto  
 Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto. È tuttavia possibile specificare alternative usando la sezione `comContracts` nel file di configurazione.  
  
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
  
 Inoltre, è possibile usare la [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elemento per specificare metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web. È anche possibile usare la [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) per specificare i tipi persistenti usati nell'integrazione. Infine, è possibile usare la [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) elemento includere definiti tipi utente (UDT) che devono essere inclusi nel contratto di servizio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [\<comContract>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [Integrazione con applicazioni COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: Configurare le impostazioni di servizio COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
