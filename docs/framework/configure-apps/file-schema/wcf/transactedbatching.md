---
title: '&lt;transactedBatching&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edeb10a1a7fa540b3f3e6ef4bf1a4a820fbc1b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="e7a6a-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="e7a6a-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="e7a6a-103">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="e7a6a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7a6a-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-105">\<behaviors></span></span>  
<span data-ttu-id="e7a6a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e7a6a-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-107">\<behavior></span></span>  
<span data-ttu-id="e7a6a-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a6a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7a6a-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7a6a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e7a6a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7a6a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7a6a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e7a6a-112">Attributes</span></span>  
  
|<span data-ttu-id="e7a6a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e7a6a-113">Attribute</span></span>|<span data-ttu-id="e7a6a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7a6a-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="e7a6a-115">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="e7a6a-116">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7a6a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e7a6a-117">Child Elements</span></span>  
 <span data-ttu-id="e7a6a-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7a6a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e7a6a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7a6a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7a6a-120">Element</span></span>|<span data-ttu-id="e7a6a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7a6a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7a6a-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e7a6a-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e7a6a-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7a6a-124">Note</span><span class="sxs-lookup"><span data-stu-id="e7a6a-124">Remarks</span></span>  
 <span data-ttu-id="e7a6a-125">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="e7a6a-126">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a6a-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7a6a-127">Example</span></span>  
 <span data-ttu-id="e7a6a-128">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7a6a-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
        </baseAddresses>  
      </host>  
  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />  
  
      <!-- the mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="endpointBehavior">  
        <transactedBatching maxBatchSize="10" />  
      </behavior>  
    </endpointBehaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7a6a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7a6a-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
