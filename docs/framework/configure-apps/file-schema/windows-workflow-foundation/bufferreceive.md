---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 1d4611d6fee9dad057985f7d8f5ef961d384efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945968"
---
# <a name="bufferreceive"></a><span data-ttu-id="e23d3-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="e23d3-101">\<bufferReceive></span></span>
<span data-ttu-id="e23d3-102">Comportamento del servizio che consente a un servizio di utilizzare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="e23d3-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="e23d3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e23d3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e23d3-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e23d3-104">\<behaviors></span></span>  
<span data-ttu-id="e23d3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e23d3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e23d3-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e23d3-106">\<behavior></span></span>  
<span data-ttu-id="e23d3-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="e23d3-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e23d3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e23d3-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e23d3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e23d3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e23d3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e23d3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e23d3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e23d3-111">Attributes</span></span>  
  
|<span data-ttu-id="e23d3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e23d3-112">Attribute</span></span>|<span data-ttu-id="e23d3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e23d3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e23d3-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="e23d3-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="e23d3-115">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="e23d3-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="e23d3-116">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="e23d3-116">The default value is 512.</span></span> <span data-ttu-id="e23d3-117">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e23d3-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e23d3-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e23d3-118">Child Elements</span></span>  
 <span data-ttu-id="e23d3-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e23d3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e23d3-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e23d3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e23d3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e23d3-121">Element</span></span>|<span data-ttu-id="e23d3-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e23d3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e23d3-123">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e23d3-123">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e23d3-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="e23d3-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e23d3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e23d3-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
