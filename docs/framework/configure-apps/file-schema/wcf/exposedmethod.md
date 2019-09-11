---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855300"
---
# <a name="exposedmethod"></a><span data-ttu-id="e914e-101">\<> exposedMethod</span><span class="sxs-lookup"><span data-stu-id="e914e-101">\<exposedMethod></span></span>
<span data-ttu-id="e914e-102">Rappresenta un metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e914e-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="e914e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e914e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e914e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e914e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e914e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comcontratti >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="e914e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="e914e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> comContract**](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="e914e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="e914e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> exposedMethods**](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="e914e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="e914e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> exposedMethod**</span><span class="sxs-lookup"><span data-stu-id="e914e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e914e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e914e-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e914e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e914e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e914e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e914e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e914e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e914e-112">Attributes</span></span>  
  
|<span data-ttu-id="e914e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e914e-113">Attribute</span></span>|<span data-ttu-id="e914e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e914e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e914e-115">name</span><span class="sxs-lookup"><span data-stu-id="e914e-115">name</span></span>|<span data-ttu-id="e914e-116">Stringa che contiene il metodo COM+ esposto quando l'interfaccia di un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="e914e-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e914e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e914e-117">Child Elements</span></span>  
 <span data-ttu-id="e914e-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e914e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e914e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e914e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e914e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e914e-120">Element</span></span>|<span data-ttu-id="e914e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e914e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e914e-122">\<> exposedMethods</span><span class="sxs-lookup"><span data-stu-id="e914e-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="e914e-123">Raccolta di elementi di [ \<> exposedMethod](exposedmethod.md) .</span><span class="sxs-lookup"><span data-stu-id="e914e-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e914e-124">Note</span><span class="sxs-lookup"><span data-stu-id="e914e-124">Remarks</span></span>  
 <span data-ttu-id="e914e-125">Lo strumento di configurazione di COM+ Integration (ComSvcConfig.exe) può essere usato per aggiungere metodi specifici da un'interfaccia COM che devono essere visualizzati nel contratto di servizio generato.</span><span class="sxs-lookup"><span data-stu-id="e914e-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="e914e-126">È possibile, ad esempio, usare il comando seguente per aggiungere al contratto di servizio generato i tre metodi denominati dall'interfaccia COM `IFinances` nel componente `ItemOrders`.Financial.</span><span class="sxs-lookup"><span data-stu-id="e914e-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="e914e-127">Quando si esegue anche ComSvcConfig. exe, viene generato il contratto di servizio seguente che elenca i metodi indicati in precedenza come [ \<exposedMethod >](exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="e914e-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="e914e-128">Al momento dell'inizializzazione del servizio, il runtime tenta di generare un contratto di servizio riflettendo e aggiungendo solo i metodi inclusi nell'elenco di [ \<exposedMethod >](exposedmethod.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="e914e-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="e914e-129">Per ogni metodo di interfaccia non incluso nel contratto di servizio viene prodotta  una traccia.</span><span class="sxs-lookup"><span data-stu-id="e914e-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e914e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e914e-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="e914e-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="e914e-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="e914e-132">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="e914e-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="e914e-133">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="e914e-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
