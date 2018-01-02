---
title: '&lt;bufferReceive&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b5b6176e7c5b982bc9f41b13c669af104bf784f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="c6b09-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="c6b09-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="c6b09-103">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="c6b09-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="c6b09-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c6b09-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6b09-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="c6b09-105">\<behaviors></span></span>  
<span data-ttu-id="c6b09-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c6b09-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c6b09-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="c6b09-107">\<behavior></span></span>  
<span data-ttu-id="c6b09-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="c6b09-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b09-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6b09-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6b09-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c6b09-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c6b09-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c6b09-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6b09-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c6b09-112">Attributes</span></span>  
  
|<span data-ttu-id="c6b09-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c6b09-113">Attribute</span></span>|<span data-ttu-id="c6b09-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6b09-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6b09-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="c6b09-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="c6b09-116">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="c6b09-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="c6b09-117">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="c6b09-117">The default value is 512.</span></span> <span data-ttu-id="c6b09-118">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c6b09-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6b09-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c6b09-119">Child Elements</span></span>  
 <span data-ttu-id="c6b09-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c6b09-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6b09-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c6b09-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c6b09-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6b09-122">Element</span></span>|<span data-ttu-id="c6b09-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6b09-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6b09-124">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c6b09-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c6b09-125">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c6b09-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6b09-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6b09-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
