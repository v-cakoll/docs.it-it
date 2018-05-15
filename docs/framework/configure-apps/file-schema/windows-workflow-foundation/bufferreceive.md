---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="95c75-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="95c75-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="95c75-103">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="95c75-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="95c75-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="95c75-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="95c75-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="95c75-105">\<behaviors></span></span>  
<span data-ttu-id="95c75-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="95c75-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="95c75-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="95c75-107">\<behavior></span></span>  
<span data-ttu-id="95c75-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="95c75-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c75-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95c75-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95c75-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="95c75-110">Attributes and Elements</span></span>  
 <span data-ttu-id="95c75-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="95c75-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95c75-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="95c75-112">Attributes</span></span>  
  
|<span data-ttu-id="95c75-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="95c75-113">Attribute</span></span>|<span data-ttu-id="95c75-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95c75-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95c75-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="95c75-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="95c75-116">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="95c75-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="95c75-117">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="95c75-117">The default value is 512.</span></span> <span data-ttu-id="95c75-118">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95c75-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95c75-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="95c75-119">Child Elements</span></span>  
 <span data-ttu-id="95c75-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="95c75-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95c75-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="95c75-121">Parent Elements</span></span>  
  
|<span data-ttu-id="95c75-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="95c75-122">Element</span></span>|<span data-ttu-id="95c75-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95c75-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95c75-124">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="95c75-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="95c75-125">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="95c75-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95c75-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c75-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
