---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 1e8ce41a27bd328c861f2f376a89c57bcd035389
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281294"
---
# <a name="transactedbatching"></a><span data-ttu-id="f374e-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="f374e-101">\<transactedBatching></span></span>
<span data-ttu-id="f374e-102">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f374e-102">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="f374e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f374e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f374e-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f374e-104">\<behaviors></span></span>  
<span data-ttu-id="f374e-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f374e-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="f374e-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f374e-106">\<behavior></span></span>  
<span data-ttu-id="f374e-107">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="f374e-107">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f374e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f374e-108">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f374e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f374e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f374e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f374e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f374e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="f374e-111">Attributes</span></span>  
  
|<span data-ttu-id="f374e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="f374e-112">Attribute</span></span>|<span data-ttu-id="f374e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f374e-113">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="f374e-114">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="f374e-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="f374e-115">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="f374e-115">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f374e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f374e-116">Child Elements</span></span>  
 <span data-ttu-id="f374e-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f374e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f374e-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f374e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f374e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f374e-119">Element</span></span>|<span data-ttu-id="f374e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f374e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f374e-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f374e-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f374e-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f374e-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f374e-123">Note</span><span class="sxs-lookup"><span data-stu-id="f374e-123">Remarks</span></span>  
 <span data-ttu-id="f374e-124">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="f374e-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="f374e-125">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f374e-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f374e-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="f374e-126">Example</span></span>  
 <span data-ttu-id="f374e-127">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f374e-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f374e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f374e-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
