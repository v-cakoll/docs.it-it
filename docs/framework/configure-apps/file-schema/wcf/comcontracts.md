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
<span data-ttu-id="6bb01-101">La sezione di configurazione `comContracts` contiene elementi che consentono di specificare varie proprietà di un contratto di servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="6bb01-101">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="6bb01-102">Specifica di spazio dei nomi e contratto</span><span class="sxs-lookup"><span data-stu-id="6bb01-102">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="6bb01-103">I contratti di servizio COM+ Integration sono attualmente limitati allo `http://tempuri.org` spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto.</span><span class="sxs-lookup"><span data-stu-id="6bb01-103">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="6bb01-104">È tuttavia possibile specificare alternative usando la sezione `comContracts` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6bb01-104">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="6bb01-105">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi e il nome del contratto di servizio, oltre a un'opzione per imporre l'uso di associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="6bb01-105">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="6bb01-106">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="6bb01-106">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="6bb01-107">Quando questa sezione è vuota, l'inizializzazione del servizio applica uno spazio dei nomi e un nome del contratto predefiniti presi dall'ID dell'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="6bb01-107">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="6bb01-108">Inoltre, è possibile utilizzare l' [\<exposedMethod>](exposedmethod.md) elemento per specificare i metodi COM+ esposti quando l'interfaccia in un componente COM+ viene esposta come un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="6bb01-108">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="6bb01-109">È anche possibile usare [\<persistableTypes>](persistabletypes.md) per specificare i tipi salvatibili usati nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="6bb01-109">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="6bb01-110">Infine, è possibile utilizzare l' [\<userDefinedType>](userdefinedtype.md) elemento per includere i tipi definiti dall'utente (UDT) da includere nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="6bb01-110">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb01-111">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6bb01-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [<span data-ttu-id="6bb01-112">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="6bb01-112">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="6bb01-113">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="6bb01-113">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
