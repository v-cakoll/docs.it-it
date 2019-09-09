---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399406"
---
# <a name="transactedbatching"></a><span data-ttu-id="c4310-101">\<> transactedBatching</span><span class="sxs-lookup"><span data-stu-id="c4310-101">\<transactedBatching></span></span>

<span data-ttu-id="c4310-102">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="c4310-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="c4310-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4310-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4310-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c4310-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c4310-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c4310-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c4310-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c4310-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="c4310-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c4310-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="c4310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transactedBatching**</span><span class="sxs-lookup"><span data-stu-id="c4310-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c4310-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4310-109">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c4310-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c4310-110">Attributes and Elements</span></span>

<span data-ttu-id="c4310-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c4310-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4310-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c4310-112">Attributes</span></span>

|<span data-ttu-id="c4310-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c4310-113">Attribute</span></span>|<span data-ttu-id="c4310-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c4310-114">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="c4310-115">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="c4310-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="c4310-116">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="c4310-116">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c4310-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c4310-117">Child Elements</span></span>

<span data-ttu-id="c4310-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c4310-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c4310-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c4310-119">Parent Elements</span></span>

|<span data-ttu-id="c4310-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4310-120">Element</span></span>|<span data-ttu-id="c4310-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4310-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c4310-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c4310-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c4310-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c4310-123">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c4310-124">Note</span><span class="sxs-lookup"><span data-stu-id="c4310-124">Remarks</span></span>

<span data-ttu-id="c4310-125">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="c4310-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="c4310-126">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="c4310-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="c4310-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4310-127">Example</span></span>

<span data-ttu-id="c4310-128">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c4310-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c4310-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4310-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
