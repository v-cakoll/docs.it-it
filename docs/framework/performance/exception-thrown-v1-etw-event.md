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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136136"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="d6816-102">Evento ETW di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="d6816-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="d6816-103">Questo evento acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="d6816-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="d6816-104">La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="d6816-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="d6816-105">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d6816-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d6816-106">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d6816-106">Keyword for raising the event</span></span>|<span data-ttu-id="d6816-107">Livello</span><span class="sxs-lookup"><span data-stu-id="d6816-107">Level</span></span>|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` <span data-ttu-id="d6816-108">(0x8000)</span><span class="sxs-lookup"><span data-stu-id="d6816-108">(0x8000)</span></span>|<span data-ttu-id="d6816-109">Avviso (2)</span><span class="sxs-lookup"><span data-stu-id="d6816-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="d6816-110">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d6816-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="d6816-111">event</span><span class="sxs-lookup"><span data-stu-id="d6816-111">Event</span></span>|<span data-ttu-id="d6816-112">ID evento</span><span class="sxs-lookup"><span data-stu-id="d6816-112">Event ID</span></span>|<span data-ttu-id="d6816-113">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d6816-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="d6816-114">80</span><span class="sxs-lookup"><span data-stu-id="d6816-114">80</span></span>|<span data-ttu-id="d6816-115">Viene generata un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="d6816-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="d6816-116">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="d6816-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="d6816-117">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d6816-117">Field name</span></span>|<span data-ttu-id="d6816-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d6816-118">Data type</span></span>|<span data-ttu-id="d6816-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6816-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d6816-120">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="d6816-120">Exception Type</span></span>|<span data-ttu-id="d6816-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d6816-121">win:UnicodeString</span></span>|<span data-ttu-id="d6816-122">Tipo dell'eccezione, ad esempio `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="d6816-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="d6816-123">Messaggio dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="d6816-123">Exception Message</span></span>|<span data-ttu-id="d6816-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d6816-124">win:UnicodeString</span></span>|<span data-ttu-id="d6816-125">Messaggio effettivo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d6816-125">Actual exception message.</span></span>|  
|<span data-ttu-id="d6816-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="d6816-126">EIPCodeThrow</span></span>|<span data-ttu-id="d6816-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="d6816-127">win:Pointer</span></span>|<span data-ttu-id="d6816-128">Puntatore dell'istruzione in cui si è verificata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d6816-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="d6816-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="d6816-129">ExceptionHR</span></span>|<span data-ttu-id="d6816-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d6816-130">win:UInt32</span></span>|<span data-ttu-id="d6816-131">[HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679) dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d6816-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="d6816-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="d6816-132">ExceptionFlags</span></span>|<span data-ttu-id="d6816-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d6816-133">win:UInt16</span></span>|<span data-ttu-id="d6816-134">0x01: HasInnerException. (vedere [eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md) nella documentazione di Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d6816-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="d6816-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="d6816-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="d6816-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="d6816-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="d6816-137">0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) su MSDN).</span><span class="sxs-lookup"><span data-stu-id="d6816-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="d6816-138">0x10: IsCLSCompliant. (un'eccezione che deriva da <xref:System.Exception> è conforme a CLS; in caso contrario, non è conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="d6816-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="d6816-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d6816-139">ClrInstanceID</span></span>|<span data-ttu-id="d6816-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d6816-140">win:UInt16</span></span>|<span data-ttu-id="d6816-141">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d6816-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6816-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6816-142">See also</span></span>

- [<span data-ttu-id="d6816-143">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="d6816-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
