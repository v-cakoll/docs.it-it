---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855300"
---
# \<exposedMethod>
<span data-ttu-id="44a7d-101">Rappresenta un metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="44a7d-101">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**  
  
## <a name="syntax"></a><span data-ttu-id="44a7d-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44a7d-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44a7d-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44a7d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="44a7d-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44a7d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44a7d-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="44a7d-105">Attributes</span></span>  
  
|<span data-ttu-id="44a7d-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="44a7d-106">Attribute</span></span>|<span data-ttu-id="44a7d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a7d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44a7d-108">name</span><span class="sxs-lookup"><span data-stu-id="44a7d-108">name</span></span>|<span data-ttu-id="44a7d-109">Stringa che contiene il metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="44a7d-109">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44a7d-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44a7d-110">Child Elements</span></span>  
 <span data-ttu-id="44a7d-111">No.</span><span class="sxs-lookup"><span data-stu-id="44a7d-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44a7d-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44a7d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="44a7d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="44a7d-113">Element</span></span>|<span data-ttu-id="44a7d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a7d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<exposedMethods>](exposedmethods.md)|<span data-ttu-id="44a7d-115">Raccolta di [\<exposedMethod>](exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="44a7d-115">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44a7d-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="44a7d-116">Remarks</span></span>  
 <span data-ttu-id="44a7d-117">Lo strumento di configurazione di COM+ Integration (ComSvcConfig.exe) può essere usato per aggiungere metodi specifici da un'interfaccia COM che devono essere visualizzati nel contratto di servizio generato.</span><span class="sxs-lookup"><span data-stu-id="44a7d-117">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="44a7d-118">È possibile, ad esempio, usare il comando seguente per aggiungere al contratto di servizio generato i tre metodi denominati dall'interfaccia COM `IFinances` nel componente `ItemOrders`.Financial.</span><span class="sxs-lookup"><span data-stu-id="44a7d-118">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="44a7d-119">Quando si esegue anche ComSvcConfig. exe, viene generato il contratto di servizio seguente che elenca i metodi indicati in precedenza come [\<exposedMethod>](exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="44a7d-119">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="44a7d-120">Al momento dell'inizializzazione del servizio, il runtime tenta di generare un contratto di servizio riflettendo e aggiungendo solo i metodi inclusi nell'elenco di [\<exposedMethod>](exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="44a7d-120">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="44a7d-121">Per ogni metodo di interfaccia non incluso nel contratto di servizio viene prodotta  una traccia.</span><span class="sxs-lookup"><span data-stu-id="44a7d-121">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a7d-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="44a7d-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="44a7d-123">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="44a7d-123">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="44a7d-124">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="44a7d-124">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
