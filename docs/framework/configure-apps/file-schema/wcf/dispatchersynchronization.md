---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925848"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="e00f9-101">\<> dispatcherSynchronization</span><span class="sxs-lookup"><span data-stu-id="e00f9-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="e00f9-102">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e00f9-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="e00f9-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e00f9-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e00f9-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="e00f9-104">\<behaviors></span></span>  
<span data-ttu-id="e00f9-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e00f9-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="e00f9-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="e00f9-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e00f9-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e00f9-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="e00f9-108">Type</span><span class="sxs-lookup"><span data-stu-id="e00f9-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e00f9-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e00f9-109">Attributes and elements</span></span>  
  
<span data-ttu-id="e00f9-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e00f9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e00f9-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e00f9-111">Attributes</span></span>

| <span data-ttu-id="e00f9-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e00f9-112">Attribute</span></span>               | <span data-ttu-id="e00f9-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e00f9-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="e00f9-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="e00f9-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="e00f9-115">Valore booleano che specifica se il comportamento di invio asincrono è abilitato.</span><span class="sxs-lookup"><span data-stu-id="e00f9-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="e00f9-116">Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.</span><span class="sxs-lookup"><span data-stu-id="e00f9-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="e00f9-117">Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="e00f9-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="e00f9-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e00f9-118">Child elements</span></span>

<span data-ttu-id="e00f9-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e00f9-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e00f9-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e00f9-120">Parent elements</span></span>

| <span data-ttu-id="e00f9-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e00f9-121">Element</span></span> | <span data-ttu-id="e00f9-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e00f9-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="e00f9-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e00f9-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e00f9-124">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e00f9-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e00f9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e00f9-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
