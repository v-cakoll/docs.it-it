---
title: Evento ETW di stack
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1107c6608fe5136eb6159b1d4f0a438e95c4dabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="stack-etw-event"></a><span data-ttu-id="27f58-102">Evento ETW di stack</span><span class="sxs-lookup"><span data-stu-id="27f58-102">Stack ETW Event</span></span>
<span data-ttu-id="27f58-103">L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="27f58-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="27f58-104">Viene registrato quando il provider di runtime è abilitato.</span><span class="sxs-lookup"><span data-stu-id="27f58-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="27f58-105">Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime.</span><span class="sxs-lookup"><span data-stu-id="27f58-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="27f58-106">Per questo motivo, è consigliabile usare questo evento con cautela.</span><span class="sxs-lookup"><span data-stu-id="27f58-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="27f58-107">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="27f58-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="27f58-108">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="27f58-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="27f58-109">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="27f58-109">Keyword for raising the event</span></span>|<span data-ttu-id="27f58-110">Livello</span><span class="sxs-lookup"><span data-stu-id="27f58-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="27f58-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="27f58-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="27f58-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="27f58-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="27f58-113">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="27f58-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="27f58-114">Evento</span><span class="sxs-lookup"><span data-stu-id="27f58-114">Event</span></span>|<span data-ttu-id="27f58-115">ID evento</span><span class="sxs-lookup"><span data-stu-id="27f58-115">Event ID</span></span>|<span data-ttu-id="27f58-116">Generato quando</span><span class="sxs-lookup"><span data-stu-id="27f58-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="27f58-117">82</span><span class="sxs-lookup"><span data-stu-id="27f58-117">82</span></span>|<span data-ttu-id="27f58-118">In combinazione con altri eventi per generare analisi dello stack dopo un evento.</span><span class="sxs-lookup"><span data-stu-id="27f58-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="27f58-119">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="27f58-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="27f58-120">Nome campo</span><span class="sxs-lookup"><span data-stu-id="27f58-120">Field name</span></span>|<span data-ttu-id="27f58-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="27f58-121">Data Type</span></span>|<span data-ttu-id="27f58-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27f58-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="27f58-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="27f58-123">ClrInstanceID</span></span>|<span data-ttu-id="27f58-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="27f58-124">win:Uint16</span></span>|<span data-ttu-id="27f58-125">Identificatore di runtime univoco.</span><span class="sxs-lookup"><span data-stu-id="27f58-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="27f58-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="27f58-126">Reserved1</span></span>|<span data-ttu-id="27f58-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="27f58-127">win:UInt8</span></span>|<span data-ttu-id="27f58-128">Riservato.</span><span class="sxs-lookup"><span data-stu-id="27f58-128">Reserved.</span></span>|  
|<span data-ttu-id="27f58-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="27f58-129">Reserved2</span></span>|<span data-ttu-id="27f58-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="27f58-130">win:UInt8</span></span>|<span data-ttu-id="27f58-131">Riservato.</span><span class="sxs-lookup"><span data-stu-id="27f58-131">Reserved.</span></span>|  
|<span data-ttu-id="27f58-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="27f58-132">FrameCount</span></span>|<span data-ttu-id="27f58-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="27f58-133">win:UInt32</span></span>|<span data-ttu-id="27f58-134">Numero di frame nell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="27f58-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="27f58-135">Stack</span><span class="sxs-lookup"><span data-stu-id="27f58-135">Stack</span></span>|<span data-ttu-id="27f58-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="27f58-136">win:Pointer</span></span>|<span data-ttu-id="27f58-137">Colonne di puntatori a istruzioni.</span><span class="sxs-lookup"><span data-stu-id="27f58-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27f58-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27f58-138">See Also</span></span>  
 [<span data-ttu-id="27f58-139">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="27f58-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
