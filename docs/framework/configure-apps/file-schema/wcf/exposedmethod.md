---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644316"
---
# <a name="exposedmethod"></a><span data-ttu-id="1d453-101">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="1d453-101">\<exposedMethod></span></span>
<span data-ttu-id="1d453-102">Rappresenta un metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1d453-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="1d453-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1d453-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1d453-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="1d453-104">\<comContracts></span></span>  
<span data-ttu-id="1d453-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="1d453-105">\<comContract></span></span>  
<span data-ttu-id="1d453-106">\<metodi ></span><span class="sxs-lookup"><span data-stu-id="1d453-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d453-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d453-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d453-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d453-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1d453-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d453-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d453-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d453-110">Attributes</span></span>  
  
|<span data-ttu-id="1d453-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="1d453-111">Attribute</span></span>|<span data-ttu-id="1d453-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d453-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d453-113">name</span><span class="sxs-lookup"><span data-stu-id="1d453-113">name</span></span>|<span data-ttu-id="1d453-114">Stringa che contiene il metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1d453-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d453-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d453-115">Child Elements</span></span>  
 <span data-ttu-id="1d453-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1d453-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1d453-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d453-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1d453-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d453-118">Element</span></span>|<span data-ttu-id="1d453-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d453-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d453-120">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="1d453-120">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="1d453-121">Una raccolta di [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="1d453-121">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d453-122">Note</span><span class="sxs-lookup"><span data-stu-id="1d453-122">Remarks</span></span>  
 <span data-ttu-id="1d453-123">Lo strumento di configurazione di COM+ Integration (ComSvcConfig.exe) può essere usato per aggiungere metodi specifici da un'interfaccia COM che devono essere visualizzati nel contratto di servizio generato.</span><span class="sxs-lookup"><span data-stu-id="1d453-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="1d453-124">È possibile, ad esempio, usare il comando seguente per aggiungere al contratto di servizio generato i tre metodi denominati dall'interfaccia COM `IFinances` nel componente `ItemOrders`.Financial.</span><span class="sxs-lookup"><span data-stu-id="1d453-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="1d453-125">Quando si esegue anche il ComSvcConfig.exe, quindi genera il contratto di servizio seguente elenca i metodi indicati precedentemente come [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="1d453-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="1d453-126">All'avvio del servizio, il runtime tenta di generare un contratto di servizio analizzando e aggiungendo solo i metodi inclusi nell'elenco degli [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="1d453-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="1d453-127">Per ogni metodo di interfaccia non incluso nel contratto di servizio viene prodotta  una traccia.</span><span class="sxs-lookup"><span data-stu-id="1d453-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d453-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d453-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="1d453-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="1d453-129">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="1d453-130">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="1d453-130">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="1d453-131">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="1d453-131">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
