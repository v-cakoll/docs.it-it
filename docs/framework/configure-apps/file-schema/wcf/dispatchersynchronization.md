---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555388"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="54eb4-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="54eb4-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="54eb4-103">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="54eb4-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="54eb4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="54eb4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="54eb4-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="54eb4-105">\<behaviors></span></span>  
<span data-ttu-id="54eb4-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="54eb4-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="54eb4-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54eb4-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54eb4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54eb4-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="54eb4-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="54eb4-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54eb4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54eb4-110">Attributes and elements</span></span>  
  
<span data-ttu-id="54eb4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54eb4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54eb4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="54eb4-112">Attributes</span></span>

| <span data-ttu-id="54eb4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="54eb4-113">Attribute</span></span>               | <span data-ttu-id="54eb4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54eb4-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="54eb4-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="54eb4-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="54eb4-116">Valore booleano che specifica se il comportamento di invio asincrono è abilitato.</span><span class="sxs-lookup"><span data-stu-id="54eb4-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="54eb4-117">Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.</span><span class="sxs-lookup"><span data-stu-id="54eb4-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="54eb4-118">Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="54eb4-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="54eb4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54eb4-119">Child elements</span></span>

<span data-ttu-id="54eb4-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="54eb4-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54eb4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54eb4-121">Parent elements</span></span>

| <span data-ttu-id="54eb4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="54eb4-122">Element</span></span> | <span data-ttu-id="54eb4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54eb4-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="54eb4-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="54eb4-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="54eb4-125">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="54eb4-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="54eb4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54eb4-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
