---
title: Evento ETW di eccezione generata_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723017"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="c865e-102">Evento ETW di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="c865e-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="c865e-103">Questo evento acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="c865e-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="c865e-104">La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="c865e-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="c865e-105">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c865e-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c865e-106">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c865e-106">Keyword for raising the event</span></span>|<span data-ttu-id="c865e-107">Livello</span><span class="sxs-lookup"><span data-stu-id="c865e-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c865e-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="c865e-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="c865e-109">Avviso (2)</span><span class="sxs-lookup"><span data-stu-id="c865e-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="c865e-110">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c865e-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="c865e-111">event</span><span class="sxs-lookup"><span data-stu-id="c865e-111">Event</span></span>|<span data-ttu-id="c865e-112">ID evento</span><span class="sxs-lookup"><span data-stu-id="c865e-112">Event ID</span></span>|<span data-ttu-id="c865e-113">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c865e-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="c865e-114">80</span><span class="sxs-lookup"><span data-stu-id="c865e-114">80</span></span>|<span data-ttu-id="c865e-115">Viene generata un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="c865e-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="c865e-116">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="c865e-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="c865e-117">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c865e-117">Field name</span></span>|<span data-ttu-id="c865e-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c865e-118">Data type</span></span>|<span data-ttu-id="c865e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c865e-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c865e-120">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="c865e-120">Exception Type</span></span>|<span data-ttu-id="c865e-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c865e-121">win:UnicodeString</span></span>|<span data-ttu-id="c865e-122">Tipo dell'eccezione, ad esempio `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="c865e-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="c865e-123">Messaggio dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="c865e-123">Exception Message</span></span>|<span data-ttu-id="c865e-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c865e-124">win:UnicodeString</span></span>|<span data-ttu-id="c865e-125">Messaggio effettivo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c865e-125">Actual exception message.</span></span>|  
|<span data-ttu-id="c865e-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="c865e-126">EIPCodeThrow</span></span>|<span data-ttu-id="c865e-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c865e-127">win:Pointer</span></span>|<span data-ttu-id="c865e-128">Puntatore dell'istruzione in cui si è verificata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c865e-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="c865e-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="c865e-129">ExceptionHR</span></span>|<span data-ttu-id="c865e-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c865e-130">win:UInt32</span></span>|<span data-ttu-id="c865e-131">[HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679) dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c865e-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="c865e-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="c865e-132">ExceptionFlags</span></span>|<span data-ttu-id="c865e-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c865e-133">win:UInt16</span></span>|<span data-ttu-id="c865e-134">0x01: HasInnerException. (vedere [eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md) nella documentazione di Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c865e-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="c865e-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="c865e-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="c865e-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="c865e-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="c865e-137">0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) su MSDN).</span><span class="sxs-lookup"><span data-stu-id="c865e-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="c865e-138">0x10: IsCLSCompliant. (un'eccezione che deriva da <xref:System.Exception> è conforme a CLS; in caso contrario, non è conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="c865e-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="c865e-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c865e-139">ClrInstanceID</span></span>|<span data-ttu-id="c865e-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c865e-140">win:UInt16</span></span>|<span data-ttu-id="c865e-141">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c865e-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c865e-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c865e-142">See also</span></span>

- [<span data-ttu-id="c865e-143">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="c865e-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
