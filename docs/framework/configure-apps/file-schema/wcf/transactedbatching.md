---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 12369f1053638583a3864fab396869d0e7045732
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918670"
---
# <a name="transactedbatching"></a><span data-ttu-id="6a8f4-101">\<> transactedBatching</span><span class="sxs-lookup"><span data-stu-id="6a8f4-101">\<transactedBatching></span></span>

<span data-ttu-id="6a8f4-102">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="6a8f4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6a8f4-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="6a8f4-104">\<comportamenti > </span><span class="sxs-lookup"><span data-stu-id="6a8f4-104">\<behaviors></span></span>\
<span data-ttu-id="6a8f4-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="6a8f4-105">\<endpointBehaviors></span></span>\
<span data-ttu-id="6a8f4-106">\<comportamento > </span><span class="sxs-lookup"><span data-stu-id="6a8f4-106">\<behavior></span></span>\
<span data-ttu-id="6a8f4-107">\<> transactedBatching</span><span class="sxs-lookup"><span data-stu-id="6a8f4-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="6a8f4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a8f4-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6a8f4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6a8f4-109">Attributes and Elements</span></span>

<span data-ttu-id="6a8f4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a8f4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6a8f4-111">Attributes</span></span>

|<span data-ttu-id="6a8f4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="6a8f4-112">Attribute</span></span>|<span data-ttu-id="6a8f4-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6a8f4-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="6a8f4-114">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="6a8f4-115">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6a8f4-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6a8f4-116">Child Elements</span></span>

<span data-ttu-id="6a8f4-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6a8f4-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6a8f4-118">Parent Elements</span></span>

|<span data-ttu-id="6a8f4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a8f4-119">Element</span></span>|<span data-ttu-id="6a8f4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a8f4-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a8f4-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6a8f4-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6a8f4-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6a8f4-123">Note</span><span class="sxs-lookup"><span data-stu-id="6a8f4-123">Remarks</span></span>

<span data-ttu-id="6a8f4-124">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="6a8f4-125">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="6a8f4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a8f4-126">Example</span></span>

<span data-ttu-id="6a8f4-127">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a8f4-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
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

## <a name="see-also"></a><span data-ttu-id="6a8f4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a8f4-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
