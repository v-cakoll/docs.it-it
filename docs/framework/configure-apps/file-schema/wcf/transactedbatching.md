---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 6167a4ad56a9481a9f695b770605991a0a88d2d9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399406"
---
# \<transactedBatching>

<span data-ttu-id="f1306-101">Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f1306-101">Specifies whether transaction batching is supported for receive operations.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactedBatching>**  

## <a name="syntax"></a><span data-ttu-id="f1306-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1306-102">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1306-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1306-103">Attributes and Elements</span></span>

<span data-ttu-id="f1306-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1306-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1306-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1306-105">Attributes</span></span>

|<span data-ttu-id="f1306-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1306-106">Attribute</span></span>|<span data-ttu-id="f1306-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1306-107">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="f1306-108">Numero intero che specifica il numero massimo di operazioni di ricezione che possono essere raggruppate in una transazione.</span><span class="sxs-lookup"><span data-stu-id="f1306-108">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="f1306-109">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="f1306-109">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f1306-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1306-110">Child Elements</span></span>

<span data-ttu-id="f1306-111">No.</span><span class="sxs-lookup"><span data-stu-id="f1306-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f1306-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1306-112">Parent Elements</span></span>

|<span data-ttu-id="f1306-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1306-113">Element</span></span>|<span data-ttu-id="f1306-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1306-114">Description</span></span>|
|-------------|-----------------|
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f1306-115">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f1306-115">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f1306-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="f1306-116">Remarks</span></span>

<span data-ttu-id="f1306-117">Un trasporto configurato il batch delle transazioni tenta di eseguire il batch di alcune operazioni di ricezione in una transazione.</span><span class="sxs-lookup"><span data-stu-id="f1306-117">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="f1306-118">In tal modo, viene evitato il costo relativamente elevato della creazione di una transazione e del relativo commit in ogni operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f1306-118">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="f1306-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1306-119">Example</span></span>

<span data-ttu-id="f1306-120">Nell'esempio seguente viene illustrato come aggiungere il comportamento di batch transazionale a un servizio in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1306-120">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f1306-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1306-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
