---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ecef8049a980f662cce4c421f62ccd3703400d69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="fc1cd-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="fc1cd-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="fc1cd-103">Rappresenta un metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="fc1cd-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc1cd-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-105">\<comContracts></span></span>  
<span data-ttu-id="fc1cd-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-106">\<comContract></span></span>  
<span data-ttu-id="fc1cd-107">\<metodi ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1cd-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc1cd-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc1cd-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fc1cd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fc1cd-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc1cd-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="fc1cd-111">Attributes</span></span>  
  
|<span data-ttu-id="fc1cd-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="fc1cd-112">Attribute</span></span>|<span data-ttu-id="fc1cd-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc1cd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc1cd-114">name</span><span class="sxs-lookup"><span data-stu-id="fc1cd-114">name</span></span>|<span data-ttu-id="fc1cd-115">Stringa che contiene il metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc1cd-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fc1cd-116">Child Elements</span></span>  
 <span data-ttu-id="fc1cd-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc1cd-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fc1cd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fc1cd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc1cd-119">Element</span></span>|<span data-ttu-id="fc1cd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc1cd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc1cd-121">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="fc1cd-122">Una raccolta di [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc1cd-123">Note</span><span class="sxs-lookup"><span data-stu-id="fc1cd-123">Remarks</span></span>  
 <span data-ttu-id="fc1cd-124">Lo strumento di configurazione di COM+ Integration (ComSvcConfig.exe) può essere usato per aggiungere metodi specifici da un'interfaccia COM che devono essere visualizzati nel contratto di servizio generato.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="fc1cd-125">È possibile, ad esempio, usare il comando seguente per aggiungere al contratto di servizio generato i tre metodi denominati dall'interfaccia COM `IFinances` nel componente `ItemOrders`.Financial.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="fc1cd-126">Quando si esegue anche ComSvcConfig.exe, quindi genera il contratto di servizio seguente elenca i metodi indicati in precedenza come [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="fc1cd-127">In fase di inizializzazione del servizio, il runtime tenta di generare un contratto di servizio analizzando e aggiungendo solo i metodi inclusi nell'elenco di [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="fc1cd-128">Per ogni metodo di interfaccia non incluso nel contratto di servizio viene prodotta  una traccia.</span><span class="sxs-lookup"><span data-stu-id="fc1cd-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1cd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc1cd-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="fc1cd-130">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="fc1cd-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="fc1cd-131">L'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="fc1cd-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="fc1cd-132">Procedura: configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="fc1cd-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
