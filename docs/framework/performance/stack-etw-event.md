---
title: Evento ETW di stack
description: Informazioni sull'evento ETW dello stack, che deve essere usato insieme ad altri eventi per generare le analisi dello stack dopo la generazione di un evento.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474137"
---
# <a name="stack-etw-event"></a><span data-ttu-id="37522-103">Evento ETW di stack</span><span class="sxs-lookup"><span data-stu-id="37522-103">Stack ETW Event</span></span>
<span data-ttu-id="37522-104">L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="37522-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="37522-105">Viene registrato quando il provider di runtime è abilitato.</span><span class="sxs-lookup"><span data-stu-id="37522-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="37522-106">Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime.</span><span class="sxs-lookup"><span data-stu-id="37522-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="37522-107">Per questo motivo, è consigliabile usare questo evento con cautela.</span><span class="sxs-lookup"><span data-stu-id="37522-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="37522-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="37522-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="37522-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="37522-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="37522-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="37522-110">Keyword for raising the event</span></span>|<span data-ttu-id="37522-111">Level</span><span class="sxs-lookup"><span data-stu-id="37522-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="37522-112">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="37522-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="37522-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="37522-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="37522-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="37522-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="37522-115">Evento</span><span class="sxs-lookup"><span data-stu-id="37522-115">Event</span></span>|<span data-ttu-id="37522-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="37522-116">Event ID</span></span>|<span data-ttu-id="37522-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="37522-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="37522-118">82</span><span class="sxs-lookup"><span data-stu-id="37522-118">82</span></span>|<span data-ttu-id="37522-119">In combinazione con altri eventi per generare analisi dello stack dopo un evento.</span><span class="sxs-lookup"><span data-stu-id="37522-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="37522-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="37522-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="37522-121">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="37522-121">Field name</span></span>|<span data-ttu-id="37522-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="37522-122">Data Type</span></span>|<span data-ttu-id="37522-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37522-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="37522-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="37522-124">ClrInstanceID</span></span>|<span data-ttu-id="37522-125">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="37522-125">win:Uint16</span></span>|<span data-ttu-id="37522-126">Identificatore di runtime univoco.</span><span class="sxs-lookup"><span data-stu-id="37522-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="37522-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="37522-127">Reserved1</span></span>|<span data-ttu-id="37522-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="37522-128">win:UInt8</span></span>|<span data-ttu-id="37522-129">Riservato.</span><span class="sxs-lookup"><span data-stu-id="37522-129">Reserved.</span></span>|  
|<span data-ttu-id="37522-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="37522-130">Reserved2</span></span>|<span data-ttu-id="37522-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="37522-131">win:UInt8</span></span>|<span data-ttu-id="37522-132">Riservato.</span><span class="sxs-lookup"><span data-stu-id="37522-132">Reserved.</span></span>|  
|<span data-ttu-id="37522-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="37522-133">FrameCount</span></span>|<span data-ttu-id="37522-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="37522-134">win:UInt32</span></span>|<span data-ttu-id="37522-135">Numero di frame nell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="37522-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="37522-136">Stack</span><span class="sxs-lookup"><span data-stu-id="37522-136">Stack</span></span>|<span data-ttu-id="37522-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="37522-137">win:Pointer</span></span>|<span data-ttu-id="37522-138">Colonne di puntatori a istruzioni.</span><span class="sxs-lookup"><span data-stu-id="37522-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37522-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37522-139">See also</span></span>

- [<span data-ttu-id="37522-140">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="37522-140">CLR ETW Events</span></span>](clr-etw-events.md)
