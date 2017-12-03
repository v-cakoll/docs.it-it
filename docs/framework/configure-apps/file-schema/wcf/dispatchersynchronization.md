---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0a6349f50c8810d834d7887daecb6ac9cffb2e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="edf5c-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="edf5c-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="edf5c-103">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="edf5c-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="edf5c-104">\<System. ServiceModel > \<comportamenti > \<endpointBehaviors > \<comportamento ></span><span class="sxs-lookup"><span data-stu-id="edf5c-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="edf5c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edf5c-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="edf5c-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="edf5c-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="edf5c-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="edf5c-107">Attributes and elements</span></span>

<span data-ttu-id="edf5c-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="edf5c-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="edf5c-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="edf5c-109">Attributes</span></span>

| <span data-ttu-id="edf5c-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="edf5c-110">Attribute</span></span>               | <span data-ttu-id="edf5c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edf5c-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="edf5c-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="edf5c-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="edf5c-113">Valore booleano che specifica se il comportamento di invio asincrono è abilitato.</span><span class="sxs-lookup"><span data-stu-id="edf5c-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="edf5c-114">Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.</span><span class="sxs-lookup"><span data-stu-id="edf5c-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="edf5c-115">Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="edf5c-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="edf5c-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="edf5c-116">Child elements</span></span>

<span data-ttu-id="edf5c-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="edf5c-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="edf5c-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="edf5c-118">Parent elements</span></span>

| <span data-ttu-id="edf5c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="edf5c-119">Element</span></span> | <span data-ttu-id="edf5c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edf5c-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="edf5c-121">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="edf5c-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="edf5c-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="edf5c-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="edf5c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edf5c-123">See also</span></span>

 <span data-ttu-id="edf5c-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="edf5c-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
