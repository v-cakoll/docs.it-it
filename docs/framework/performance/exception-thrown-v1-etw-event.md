---
title: Evento ETW di eccezione generata_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 865b7b16d5807bd9161855f453128a63c84eab96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400822"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="4d84a-102">Evento ETW di eccezione generata_V1</span><span class="sxs-lookup"><span data-stu-id="4d84a-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="4d84a-103">Questo evento acquisisce informazioni sulle eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="4d84a-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="4d84a-104">La tabella seguente illustra le parole chiave con cui viene generato l'evento e il livello dell'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="4d84a-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="4d84a-105">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4d84a-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4d84a-106">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4d84a-106">Keyword for raising the event</span></span>|<span data-ttu-id="4d84a-107">Livello</span><span class="sxs-lookup"><span data-stu-id="4d84a-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4d84a-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="4d84a-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="4d84a-109">Avviso (2)</span><span class="sxs-lookup"><span data-stu-id="4d84a-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="4d84a-110">La tabella seguente offre informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="4d84a-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="4d84a-111">event</span><span class="sxs-lookup"><span data-stu-id="4d84a-111">Event</span></span>|<span data-ttu-id="4d84a-112">ID evento</span><span class="sxs-lookup"><span data-stu-id="4d84a-112">Event ID</span></span>|<span data-ttu-id="4d84a-113">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4d84a-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="4d84a-114">80</span><span class="sxs-lookup"><span data-stu-id="4d84a-114">80</span></span>|<span data-ttu-id="4d84a-115">Viene generata un'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="4d84a-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="4d84a-116">La tabella seguente mostra i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="4d84a-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="4d84a-117">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4d84a-117">Field name</span></span>|<span data-ttu-id="4d84a-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4d84a-118">Data type</span></span>|<span data-ttu-id="4d84a-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d84a-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4d84a-120">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="4d84a-120">Exception Type</span></span>|<span data-ttu-id="4d84a-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4d84a-121">win:UnicodeString</span></span>|<span data-ttu-id="4d84a-122">Tipo dell'eccezione, ad esempio `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="4d84a-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="4d84a-123">Messaggio dell'eccezione</span><span class="sxs-lookup"><span data-stu-id="4d84a-123">Exception Message</span></span>|<span data-ttu-id="4d84a-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4d84a-124">win:UnicodeString</span></span>|<span data-ttu-id="4d84a-125">Messaggio effettivo dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d84a-125">Actual exception message.</span></span>|  
|<span data-ttu-id="4d84a-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="4d84a-126">EIPCodeThrow</span></span>|<span data-ttu-id="4d84a-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4d84a-127">win:Pointer</span></span>|<span data-ttu-id="4d84a-128">Puntatore dell'istruzione in cui si è verificata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d84a-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="4d84a-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="4d84a-129">ExceptionHR</span></span>|<span data-ttu-id="4d84a-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4d84a-130">win:UInt32</span></span>|<span data-ttu-id="4d84a-131">[HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679) dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d84a-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="4d84a-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="4d84a-132">ExceptionFlags</span></span>|<span data-ttu-id="4d84a-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4d84a-133">win:UInt16</span></span>|<span data-ttu-id="4d84a-134">0x01: HasInnerException. Vedere [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) (Eventi ETW di CLR) nella documentazione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4d84a-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="4d84a-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="4d84a-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="4d84a-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="4d84a-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="4d84a-137">0x08: IsCorruptedStateException. Indica che lo stato del processo è danneggiato. Vedere [Gestione delle eccezioni di stato danneggiato](https://go.microsoft.com/fwlink/?LinkId=179681) su MSDN.</span><span class="sxs-lookup"><span data-stu-id="4d84a-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="4d84a-138">0x10: IsCLSCompliant. Un'eccezione derivante da <xref:System.Exception> è conforme a CLS. In caso contrario, non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="4d84a-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="4d84a-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4d84a-139">ClrInstanceID</span></span>|<span data-ttu-id="4d84a-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4d84a-140">win:UInt16</span></span>|<span data-ttu-id="4d84a-141">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4d84a-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d84a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d84a-142">See Also</span></span>  
 [<span data-ttu-id="4d84a-143">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="4d84a-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
