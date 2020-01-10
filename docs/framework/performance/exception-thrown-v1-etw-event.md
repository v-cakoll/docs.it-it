---
title: Evento ETW di eccezione generata_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: 80faf6e607755ee79c7ec17f2d7d3d5bdce822b7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716058"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="67d11-102">Evento ETW di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="67d11-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="67d11-103">Questo evento acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="67d11-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="67d11-104">La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="67d11-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="67d11-105">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="67d11-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="67d11-106">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="67d11-106">Keyword for raising the event</span></span>|<span data-ttu-id="67d11-107">Livello</span><span class="sxs-lookup"><span data-stu-id="67d11-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="67d11-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="67d11-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="67d11-109">Avviso (2)</span><span class="sxs-lookup"><span data-stu-id="67d11-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="67d11-110">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="67d11-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="67d11-111">Event</span><span class="sxs-lookup"><span data-stu-id="67d11-111">Event</span></span>|<span data-ttu-id="67d11-112">ID evento</span><span class="sxs-lookup"><span data-stu-id="67d11-112">Event ID</span></span>|<span data-ttu-id="67d11-113">Generato quando</span><span class="sxs-lookup"><span data-stu-id="67d11-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="67d11-114">80</span><span class="sxs-lookup"><span data-stu-id="67d11-114">80</span></span>|<span data-ttu-id="67d11-115">Viene generata un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="67d11-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="67d11-116">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="67d11-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="67d11-117">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="67d11-117">Field name</span></span>|<span data-ttu-id="67d11-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="67d11-118">Data type</span></span>|<span data-ttu-id="67d11-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67d11-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="67d11-120">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="67d11-120">Exception Type</span></span>|<span data-ttu-id="67d11-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="67d11-121">win:UnicodeString</span></span>|<span data-ttu-id="67d11-122">Tipo dell'eccezione, ad esempio `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="67d11-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="67d11-123">Messaggio dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="67d11-123">Exception Message</span></span>|<span data-ttu-id="67d11-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="67d11-124">win:UnicodeString</span></span>|<span data-ttu-id="67d11-125">Messaggio effettivo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67d11-125">Actual exception message.</span></span>|  
|<span data-ttu-id="67d11-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="67d11-126">EIPCodeThrow</span></span>|<span data-ttu-id="67d11-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="67d11-127">win:Pointer</span></span>|<span data-ttu-id="67d11-128">Puntatore dell'istruzione in cui si è verificata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67d11-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="67d11-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="67d11-129">ExceptionHR</span></span>|<span data-ttu-id="67d11-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="67d11-130">win:UInt32</span></span>|<span data-ttu-id="67d11-131">[HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a) dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67d11-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="67d11-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="67d11-132">ExceptionFlags</span></span>|<span data-ttu-id="67d11-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="67d11-133">win:UInt16</span></span>|<span data-ttu-id="67d11-134">0x01: HasInnerException. Vedere [CLR ETW Events](clr-etw-events.md) (Eventi ETW di CLR) nella documentazione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="67d11-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="67d11-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="67d11-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="67d11-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="67d11-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="67d11-137">0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [gestione delle eccezioni di stato danneggiato](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="67d11-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="67d11-138">0x10: IsCLSCompliant. Un'eccezione derivante da <xref:System.Exception> è conforme a CLS. In caso contrario, non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="67d11-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="67d11-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="67d11-139">ClrInstanceID</span></span>|<span data-ttu-id="67d11-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="67d11-140">win:UInt16</span></span>|<span data-ttu-id="67d11-141">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="67d11-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="67d11-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67d11-142">See also</span></span>

- [<span data-ttu-id="67d11-143">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="67d11-143">CLR ETW Events</span></span>](clr-etw-events.md)
