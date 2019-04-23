---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174512"
---
# <a name="exposedmethod"></a>\<exposedMethod>
Rappresenta un metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
\<metodi >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa che contiene il metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<exposedMethods>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Una raccolta di [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.|  
  
## <a name="remarks"></a>Note  
 Lo strumento di configurazione di COM+ Integration (ComSvcConfig.exe) può essere usato per aggiungere metodi specifici da un'interfaccia COM che devono essere visualizzati nel contratto di servizio generato.  
  
 È possibile, ad esempio, usare il comando seguente per aggiungere al contratto di servizio generato i tre metodi denominati dall'interfaccia COM `IFinances` nel componente `ItemOrders`.Financial.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Quando si esegue anche il ComSvcConfig.exe, quindi genera il contratto di servizio seguente elenca i metodi indicati precedentemente come [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 All'avvio del servizio, il runtime tenta di generare un contratto di servizio analizzando e aggiungendo solo i metodi inclusi nell'elenco degli [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi. Per ogni metodo di interfaccia non incluso nel contratto di servizio viene prodotta  una traccia.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Integrazione con applicazioni COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: Configurare le impostazioni di servizio COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
