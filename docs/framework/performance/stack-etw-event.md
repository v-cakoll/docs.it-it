---
title: Evento ETW di stack
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7cba2bd1dd5b83e29c7a6c192a1a7e5e2d33ecc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076477"
---
# <a name="stack-etw-event"></a><span data-ttu-id="d5f18-102">Evento ETW di stack</span><span class="sxs-lookup"><span data-stu-id="d5f18-102">Stack ETW Event</span></span>
<span data-ttu-id="d5f18-103">L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="d5f18-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="d5f18-104">Viene registrato quando il provider di runtime è abilitato.</span><span class="sxs-lookup"><span data-stu-id="d5f18-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="d5f18-105">Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime.</span><span class="sxs-lookup"><span data-stu-id="d5f18-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="d5f18-106">Per questo motivo, è consigliabile usare questo evento con cautela.</span><span class="sxs-lookup"><span data-stu-id="d5f18-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="d5f18-107">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="d5f18-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="d5f18-108">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d5f18-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d5f18-109">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d5f18-109">Keyword for raising the event</span></span>|<span data-ttu-id="d5f18-110">Livello</span><span class="sxs-lookup"><span data-stu-id="d5f18-110">Level</span></span>|  
|-----------------------------------|-----------|  
|`StackKeyword` <span data-ttu-id="d5f18-111">(0x40000000)</span><span class="sxs-lookup"><span data-stu-id="d5f18-111">(0x40000000)</span></span>|<span data-ttu-id="d5f18-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="d5f18-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="d5f18-113">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d5f18-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d5f18-114">event</span><span class="sxs-lookup"><span data-stu-id="d5f18-114">Event</span></span>|<span data-ttu-id="d5f18-115">ID evento</span><span class="sxs-lookup"><span data-stu-id="d5f18-115">Event ID</span></span>|<span data-ttu-id="d5f18-116">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d5f18-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="d5f18-117">82</span><span class="sxs-lookup"><span data-stu-id="d5f18-117">82</span></span>|<span data-ttu-id="d5f18-118">In combinazione con altri eventi per generare analisi dello stack dopo un evento.</span><span class="sxs-lookup"><span data-stu-id="d5f18-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="d5f18-119">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d5f18-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d5f18-120">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d5f18-120">Field name</span></span>|<span data-ttu-id="d5f18-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d5f18-121">Data Type</span></span>|<span data-ttu-id="d5f18-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5f18-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d5f18-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d5f18-123">ClrInstanceID</span></span>|<span data-ttu-id="d5f18-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="d5f18-124">win:Uint16</span></span>|<span data-ttu-id="d5f18-125">Identificatore di runtime univoco.</span><span class="sxs-lookup"><span data-stu-id="d5f18-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="d5f18-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="d5f18-126">Reserved1</span></span>|<span data-ttu-id="d5f18-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="d5f18-127">win:UInt8</span></span>|<span data-ttu-id="d5f18-128">Riservato.</span><span class="sxs-lookup"><span data-stu-id="d5f18-128">Reserved.</span></span>|  
|<span data-ttu-id="d5f18-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="d5f18-129">Reserved2</span></span>|<span data-ttu-id="d5f18-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="d5f18-130">win:UInt8</span></span>|<span data-ttu-id="d5f18-131">Riservato.</span><span class="sxs-lookup"><span data-stu-id="d5f18-131">Reserved.</span></span>|  
|<span data-ttu-id="d5f18-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="d5f18-132">FrameCount</span></span>|<span data-ttu-id="d5f18-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d5f18-133">win:UInt32</span></span>|<span data-ttu-id="d5f18-134">Numero di frame nell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="d5f18-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="d5f18-135">Stack</span><span class="sxs-lookup"><span data-stu-id="d5f18-135">Stack</span></span>|<span data-ttu-id="d5f18-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="d5f18-136">win:Pointer</span></span>|<span data-ttu-id="d5f18-137">Colonne di puntatori a istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d5f18-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5f18-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5f18-138">See also</span></span>

- [<span data-ttu-id="d5f18-139">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="d5f18-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
