---
title: Evento ETW di eccezione generata_V1
description: Visualizzare informazioni dettagliate sull'evento ExceptionThrown_V1 ETW. I dati dell'evento, ad esempio i nomi dei campi, i tipi di dati e le descrizioni vengono forniti per le eccezioni generate.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f800a43d0ed2a82bc51a5e3a028b5fa1870df3fb
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309456"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="81f53-104">Evento ETW di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="81f53-104">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="81f53-105">Questo evento acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="81f53-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="81f53-106">La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="81f53-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="81f53-107">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="81f53-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="81f53-108">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="81f53-108">Keyword for raising the event</span></span>|<span data-ttu-id="81f53-109">Livello</span><span class="sxs-lookup"><span data-stu-id="81f53-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="81f53-110">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="81f53-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="81f53-111">Avviso (2)</span><span class="sxs-lookup"><span data-stu-id="81f53-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="81f53-112">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="81f53-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="81f53-113">Evento</span><span class="sxs-lookup"><span data-stu-id="81f53-113">Event</span></span>|<span data-ttu-id="81f53-114">ID evento</span><span class="sxs-lookup"><span data-stu-id="81f53-114">Event ID</span></span>|<span data-ttu-id="81f53-115">Generato quando</span><span class="sxs-lookup"><span data-stu-id="81f53-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="81f53-116">80</span><span class="sxs-lookup"><span data-stu-id="81f53-116">80</span></span>|<span data-ttu-id="81f53-117">Viene generata un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="81f53-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="81f53-118">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="81f53-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="81f53-119">Nome campo</span><span class="sxs-lookup"><span data-stu-id="81f53-119">Field name</span></span>|<span data-ttu-id="81f53-120">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="81f53-120">Data type</span></span>|<span data-ttu-id="81f53-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81f53-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="81f53-122">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="81f53-122">Exception Type</span></span>|<span data-ttu-id="81f53-123">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="81f53-123">win:UnicodeString</span></span>|<span data-ttu-id="81f53-124">Tipo dell'eccezione, ad esempio `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="81f53-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="81f53-125">Messaggio dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="81f53-125">Exception Message</span></span>|<span data-ttu-id="81f53-126">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="81f53-126">win:UnicodeString</span></span>|<span data-ttu-id="81f53-127">Messaggio effettivo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81f53-127">Actual exception message.</span></span>|  
|<span data-ttu-id="81f53-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="81f53-128">EIPCodeThrow</span></span>|<span data-ttu-id="81f53-129">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="81f53-129">win:Pointer</span></span>|<span data-ttu-id="81f53-130">Puntatore dell'istruzione in cui si è verificata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81f53-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="81f53-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="81f53-131">ExceptionHR</span></span>|<span data-ttu-id="81f53-132">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="81f53-132">win:UInt32</span></span>|<span data-ttu-id="81f53-133">[HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a) dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81f53-133">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="81f53-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="81f53-134">ExceptionFlags</span></span>|<span data-ttu-id="81f53-135">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="81f53-135">win:UInt16</span></span>|<span data-ttu-id="81f53-136">0x01: HasInnerException. Vedere [CLR ETW Events](clr-etw-events.md) (Eventi ETW di CLR) nella documentazione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81f53-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="81f53-137">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="81f53-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="81f53-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="81f53-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="81f53-139">0x08: IsCorruptedStateException (indica che lo stato del processo è danneggiato; vedere [gestione delle eccezioni di stato danneggiato](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="81f53-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="81f53-140">0x10: IsCLSCompliant. Un'eccezione derivante da <xref:System.Exception> è conforme a CLS. In caso contrario, non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="81f53-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="81f53-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="81f53-141">ClrInstanceID</span></span>|<span data-ttu-id="81f53-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="81f53-142">win:UInt16</span></span>|<span data-ttu-id="81f53-143">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="81f53-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81f53-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81f53-144">See also</span></span>

- [<span data-ttu-id="81f53-145">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="81f53-145">CLR ETW Events</span></span>](clr-etw-events.md)
