---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919480"
---
# <a name="comcontracts"></a><span data-ttu-id="8693d-101">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="8693d-101">\<comContracts></span></span>
<span data-ttu-id="8693d-102">La sezione di configurazione `comContracts` contiene elementi che consentono di specificare varie proprietà di un contratto di servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="8693d-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="8693d-103">Specifica di spazio dei nomi e contratto</span><span class="sxs-lookup"><span data-stu-id="8693d-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="8693d-104">I `http://tempuri.org` contratti di servizio com+ Integration sono attualmente limitati allo spazio dei nomi e il nome del contratto è derivato dall'interfaccia com di supporto.</span><span class="sxs-lookup"><span data-stu-id="8693d-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="8693d-105">È tuttavia possibile specificare alternative usando la sezione `comContracts` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8693d-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="8693d-106">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi e il nome del contratto di servizio, oltre a un'opzione per imporre l'uso di associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="8693d-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="8693d-107">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="8693d-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="8693d-108">Quando questa sezione è vuota, l'inizializzazione del servizio applica uno spazio dei nomi e un nome del contratto predefiniti presi dall'ID dell'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="8693d-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="8693d-109">Inoltre, è possibile utilizzare l' [ \<elemento > exposedMethod](exposedmethod.md) per specificare i metodi COM+ esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="8693d-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="8693d-110">È anche possibile usare il [ \<> persistableTypes](persistabletypes.md) per specificare i tipi salvativi usati nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="8693d-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="8693d-111">Infine, è possibile usare l' [ \<elemento >](userdefinedtype.md) per includere i tipi definiti dall'utente (UDT) da includere nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="8693d-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8693d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8693d-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="8693d-113">\<> exposedMethod</span><span class="sxs-lookup"><span data-stu-id="8693d-113">\<exposedMethod></span></span>](exposedmethod.md)
- [<span data-ttu-id="8693d-114">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="8693d-114">\<persistableTypes></span></span>](persistabletypes.md)
- [<span data-ttu-id="8693d-115">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="8693d-115">\<userDefinedType></span></span>](userdefinedtype.md)
- [<span data-ttu-id="8693d-116">\<comContract></span><span class="sxs-lookup"><span data-stu-id="8693d-116">\<comContract></span></span>](comcontract.md)
- [<span data-ttu-id="8693d-117">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="8693d-117">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="8693d-118">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="8693d-118">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
