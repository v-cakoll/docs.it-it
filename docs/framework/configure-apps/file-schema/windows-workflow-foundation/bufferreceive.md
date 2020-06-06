---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398839"
---
# \<bufferReceive>
<span data-ttu-id="b0633-101">Comportamento del servizio che consente a un servizio di utilizzare l'elaborazione di ricezione memorizzata nel buffer per far sì che un servizio flusso di lavoro elabori messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="b0633-101">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**  
  
## <a name="syntax"></a><span data-ttu-id="b0633-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0633-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0633-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b0633-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b0633-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b0633-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0633-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="b0633-105">Attributes</span></span>  
  
|<span data-ttu-id="b0633-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="b0633-106">Attribute</span></span>|<span data-ttu-id="b0633-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0633-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0633-108">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="b0633-108">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="b0633-109">Integer che specifica il numero massimo di messaggi in sospeso consentiti per ogni canale.</span><span class="sxs-lookup"><span data-stu-id="b0633-109">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="b0633-110">Il valore predefinito è 512.</span><span class="sxs-lookup"><span data-stu-id="b0633-110">The default value is 512.</span></span> <span data-ttu-id="b0633-111">Questa proprietà limita il numero di messaggi non ordinati che possono essere ricevuti da un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0633-111">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0633-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b0633-112">Child Elements</span></span>  
 <span data-ttu-id="b0633-113">No.</span><span class="sxs-lookup"><span data-stu-id="b0633-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0633-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b0633-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b0633-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0633-115">Element</span></span>|<span data-ttu-id="b0633-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0633-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0633-117">\<behavior>di\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b0633-117">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b0633-118">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="b0633-118">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0633-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0633-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
