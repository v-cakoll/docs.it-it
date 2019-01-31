---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 6ed37d73440dac22288ae1da526d81b2d0b990a1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286624"
---
# <a name="bufferreceive"></a><span data-ttu-id="e0db1-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="e0db1-101">\<bufferReceive></span></span>
<span data-ttu-id="e0db1-102">Comportamento del servizio che consente a un servizio di usare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="e0db1-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="e0db1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e0db1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e0db1-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e0db1-104">\<behaviors></span></span>  
<span data-ttu-id="e0db1-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e0db1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e0db1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e0db1-106">\<behavior></span></span>  
<span data-ttu-id="e0db1-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="e0db1-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0db1-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0db1-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0db1-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e0db1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e0db1-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e0db1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0db1-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e0db1-111">Attributes</span></span>  
  
|<span data-ttu-id="e0db1-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e0db1-112">Attribute</span></span>|<span data-ttu-id="e0db1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0db1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0db1-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="e0db1-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="e0db1-115">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="e0db1-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="e0db1-116">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="e0db1-116">The default value is 512.</span></span> <span data-ttu-id="e0db1-117">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e0db1-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0db1-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e0db1-118">Child Elements</span></span>  
 <span data-ttu-id="e0db1-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e0db1-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0db1-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e0db1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e0db1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0db1-121">Element</span></span>|<span data-ttu-id="e0db1-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0db1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0db1-123">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e0db1-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e0db1-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="e0db1-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0db1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0db1-125">See also</span></span>
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
