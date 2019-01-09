---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: f56751ea3f8bdc9ecbeff57db835e5fc2edbb73e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148448"
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="1e23d-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="1e23d-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="1e23d-103">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="1e23d-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="1e23d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1e23d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e23d-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="1e23d-105">\<behaviors></span></span>  
<span data-ttu-id="1e23d-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1e23d-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1e23d-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="1e23d-107">\<behavior></span></span>  
<span data-ttu-id="1e23d-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="1e23d-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e23d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e23d-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e23d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e23d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1e23d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e23d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e23d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1e23d-112">Attributes</span></span>  
  
|<span data-ttu-id="1e23d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1e23d-113">Attribute</span></span>|<span data-ttu-id="1e23d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e23d-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="1e23d-115">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="1e23d-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="1e23d-116">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="1e23d-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e23d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e23d-117">Child Elements</span></span>  
 <span data-ttu-id="1e23d-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1e23d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e23d-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e23d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1e23d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e23d-120">Element</span></span>|<span data-ttu-id="1e23d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e23d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e23d-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1e23d-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1e23d-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1e23d-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e23d-124">Note</span><span class="sxs-lookup"><span data-stu-id="1e23d-124">Remarks</span></span>  
 <span data-ttu-id="1e23d-125">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="1e23d-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="1e23d-126">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="1e23d-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e23d-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e23d-127">Example</span></span>  
 <span data-ttu-id="1e23d-128">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1e23d-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
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
  
## <a name="see-also"></a><span data-ttu-id="1e23d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e23d-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
