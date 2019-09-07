---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398008"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="286fe-101">\<> dispatcherSynchronization</span><span class="sxs-lookup"><span data-stu-id="286fe-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="286fe-102">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="286fe-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="286fe-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="286fe-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="286fe-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="286fe-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="286fe-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="286fe-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="286fe-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="286fe-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="286fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="286fe-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="286fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dispatcherSynchronization**</span><span class="sxs-lookup"><span data-stu-id="286fe-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="286fe-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="286fe-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="286fe-110">Type</span><span class="sxs-lookup"><span data-stu-id="286fe-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="286fe-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="286fe-111">Attributes and elements</span></span>  
  
<span data-ttu-id="286fe-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="286fe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="286fe-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="286fe-113">Attributes</span></span>

| <span data-ttu-id="286fe-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="286fe-114">Attribute</span></span>               | <span data-ttu-id="286fe-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="286fe-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="286fe-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="286fe-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="286fe-117">Valore booleano che specifica se il comportamento di invio asincrono è abilitato.</span><span class="sxs-lookup"><span data-stu-id="286fe-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="286fe-118">Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.</span><span class="sxs-lookup"><span data-stu-id="286fe-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="286fe-119">Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="286fe-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="286fe-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="286fe-120">Child elements</span></span>

<span data-ttu-id="286fe-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="286fe-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="286fe-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="286fe-122">Parent elements</span></span>

| <span data-ttu-id="286fe-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="286fe-123">Element</span></span> | <span data-ttu-id="286fe-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="286fe-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="286fe-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="286fe-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="286fe-126">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="286fe-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="286fe-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="286fe-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
