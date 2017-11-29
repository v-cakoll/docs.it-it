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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 623ff924e171282c399bddcdc212a0606a3416d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="4db5d-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="4db5d-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="4db5d-103">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="4db5d-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="4db5d-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4db5d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4db5d-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="4db5d-105">\<behaviors></span></span>  
<span data-ttu-id="4db5d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4db5d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4db5d-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="4db5d-107">\<behavior></span></span>  
<span data-ttu-id="4db5d-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="4db5d-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db5d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4db5d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4db5d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4db5d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4db5d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4db5d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4db5d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4db5d-112">Attributes</span></span>  
  
|<span data-ttu-id="4db5d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4db5d-113">Attribute</span></span>|<span data-ttu-id="4db5d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4db5d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4db5d-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="4db5d-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="4db5d-116">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="4db5d-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="4db5d-117">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="4db5d-117">The default value is 512.</span></span> <span data-ttu-id="4db5d-118">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4db5d-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4db5d-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4db5d-119">Child Elements</span></span>  
 <span data-ttu-id="4db5d-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4db5d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4db5d-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4db5d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4db5d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4db5d-122">Element</span></span>|<span data-ttu-id="4db5d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4db5d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4db5d-124">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4db5d-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="4db5d-125">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4db5d-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4db5d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4db5d-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
