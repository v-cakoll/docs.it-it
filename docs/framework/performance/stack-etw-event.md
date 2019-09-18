---
title: Evento ETW di stack
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dc23f5105b589d5b74c9ea6b7f40b84c2b04e6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046164"
---
# <a name="stack-etw-event"></a><span data-ttu-id="a87f7-102">Evento ETW di stack</span><span class="sxs-lookup"><span data-stu-id="a87f7-102">Stack ETW Event</span></span>
<span data-ttu-id="a87f7-103">L'evento di stack deve essere usato in combinazione con altri eventi per generare analisi dello stack dopo la generazione di un evento.</span><span class="sxs-lookup"><span data-stu-id="a87f7-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="a87f7-104">Viene registrato quando il provider di runtime è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a87f7-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="a87f7-105">Si tratto di un evento molto frequente perché viene generato ogni volta che viene generato un altro evento di runtime.</span><span class="sxs-lookup"><span data-stu-id="a87f7-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="a87f7-106">Per questo motivo, è consigliabile usare questo evento con cautela.</span><span class="sxs-lookup"><span data-stu-id="a87f7-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="a87f7-107">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="a87f7-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="a87f7-108">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a87f7-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a87f7-109">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a87f7-109">Keyword for raising the event</span></span>|<span data-ttu-id="a87f7-110">Level</span><span class="sxs-lookup"><span data-stu-id="a87f7-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a87f7-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="a87f7-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="a87f7-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="a87f7-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="a87f7-113">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="a87f7-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a87f7-114">event</span><span class="sxs-lookup"><span data-stu-id="a87f7-114">Event</span></span>|<span data-ttu-id="a87f7-115">ID evento</span><span class="sxs-lookup"><span data-stu-id="a87f7-115">Event ID</span></span>|<span data-ttu-id="a87f7-116">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a87f7-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="a87f7-117">82</span><span class="sxs-lookup"><span data-stu-id="a87f7-117">82</span></span>|<span data-ttu-id="a87f7-118">In combinazione con altri eventi per generare analisi dello stack dopo un evento.</span><span class="sxs-lookup"><span data-stu-id="a87f7-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="a87f7-119">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a87f7-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a87f7-120">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a87f7-120">Field name</span></span>|<span data-ttu-id="a87f7-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a87f7-121">Data Type</span></span>|<span data-ttu-id="a87f7-122">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a87f7-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a87f7-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a87f7-123">ClrInstanceID</span></span>|<span data-ttu-id="a87f7-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="a87f7-124">win:Uint16</span></span>|<span data-ttu-id="a87f7-125">Identificatore di runtime univoco.</span><span class="sxs-lookup"><span data-stu-id="a87f7-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="a87f7-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="a87f7-126">Reserved1</span></span>|<span data-ttu-id="a87f7-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="a87f7-127">win:UInt8</span></span>|<span data-ttu-id="a87f7-128">Riservato.</span><span class="sxs-lookup"><span data-stu-id="a87f7-128">Reserved.</span></span>|  
|<span data-ttu-id="a87f7-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="a87f7-129">Reserved2</span></span>|<span data-ttu-id="a87f7-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="a87f7-130">win:UInt8</span></span>|<span data-ttu-id="a87f7-131">Riservato.</span><span class="sxs-lookup"><span data-stu-id="a87f7-131">Reserved.</span></span>|  
|<span data-ttu-id="a87f7-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="a87f7-132">FrameCount</span></span>|<span data-ttu-id="a87f7-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a87f7-133">win:UInt32</span></span>|<span data-ttu-id="a87f7-134">Numero di frame nell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="a87f7-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="a87f7-135">Stack</span><span class="sxs-lookup"><span data-stu-id="a87f7-135">Stack</span></span>|<span data-ttu-id="a87f7-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="a87f7-136">win:Pointer</span></span>|<span data-ttu-id="a87f7-137">Colonne di puntatori a istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a87f7-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a87f7-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a87f7-138">See also</span></span>

- [<span data-ttu-id="a87f7-139">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="a87f7-139">CLR ETW Events</span></span>](clr-etw-events.md)
