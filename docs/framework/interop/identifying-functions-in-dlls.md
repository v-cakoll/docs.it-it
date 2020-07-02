---
title: Identificazione delle funzioni nelle DLL
description: Identificare le funzioni nelle DLL. L'identità di una funzione DLL è costituita da un nome di funzione o ordinale e dal nome del file DLL in cui è possibile trovare l'implementazione.
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
ms.openlocfilehash: 054d1351a9ee6adab17117c9f423aa26d0d9ed59
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622731"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="2433d-104">Identificazione delle funzioni nelle DLL</span><span class="sxs-lookup"><span data-stu-id="2433d-104">Identifying Functions in DLLs</span></span>
<span data-ttu-id="2433d-105">L'identità di una funzione di una DLL è costituita dagli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2433d-105">The identity of a DLL function consists of the following elements:</span></span>  
  
- <span data-ttu-id="2433d-106">Nome della funzione o numero ordinale</span><span class="sxs-lookup"><span data-stu-id="2433d-106">Function name or ordinal</span></span>  
  
- <span data-ttu-id="2433d-107">Nome del file DLL in cui si può trovare l'implementazione</span><span class="sxs-lookup"><span data-stu-id="2433d-107">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="2433d-108">Ad esempio, specificando la funzione **MessageBox** in User32.dll, vengono identificate la funzione (**MessageBox**) e la sua posizione (User32.dll, User32 o user32).</span><span class="sxs-lookup"><span data-stu-id="2433d-108">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="2433d-109">L'Application Programming Interface di Microsoft Windows (API Windows) può contenere due versioni di ogni funzione che gestisce i caratteri e le stringhe: una versione ANSI con caratteri a 1 byte e una versione Unicode con caratteri a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="2433d-109">The Microsoft Windows application programming interface (Windows API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="2433d-110">Se non è specificato, il set di caratteri, rappresentato dal campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, usa come impostazione predefinita la versione ANSI.</span><span class="sxs-lookup"><span data-stu-id="2433d-110">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="2433d-111">Alcune funzioni possono includere più di due versioni.</span><span class="sxs-lookup"><span data-stu-id="2433d-111">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="2433d-112">**MessageBoxA** è il punto di ingresso ANSI per la funzione **MessageBox**, mentre **MessageBoxW** è la versione Unicode.</span><span class="sxs-lookup"><span data-stu-id="2433d-112">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="2433d-113">Per elencare i nomi di funzione per una DLL specifica, ad esempio user32.dll, è possibile eseguire numerosi strumenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2433d-113">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="2433d-114">Ad esempio, è possibile usare `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` per ottenere i nomi di funzione.</span><span class="sxs-lookup"><span data-stu-id="2433d-114">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="2433d-115">È possibile rinominare una funzione non gestita con qualsiasi nome desiderato all'interno del codice, a condizione di eseguire il mapping del nuovo nome al punto di ingresso originale nella DLL.</span><span class="sxs-lookup"><span data-stu-id="2433d-115">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="2433d-116">Per istruzioni su come rinominare una funzione DLL non gestita in codice sorgente gestito, vedere [Specifica di un punto di ingresso](specifying-an-entry-point.md).</span><span class="sxs-lookup"><span data-stu-id="2433d-116">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="2433d-117">Platform invoke consente di controllare una parte significativa del sistema operativo chiamando funzioni nell'API Windows e altre DLL.</span><span class="sxs-lookup"><span data-stu-id="2433d-117">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Windows API and other DLLs.</span></span> <span data-ttu-id="2433d-118">Oltre all'API Windows, sono disponibili molte altre API e DLL tramite platform invoke.</span><span class="sxs-lookup"><span data-stu-id="2433d-118">In addition to the Windows API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="2433d-119">La tabella seguente descrive diverse DLL di uso comune nell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="2433d-119">The following table describes several commonly used DLLs in the Windows API.</span></span>  
  
|<span data-ttu-id="2433d-120">DLL</span><span class="sxs-lookup"><span data-stu-id="2433d-120">DLL</span></span>|<span data-ttu-id="2433d-121">Descrizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="2433d-121">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="2433d-122">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="2433d-122">GDI32.dll</span></span>|<span data-ttu-id="2433d-123">Funzioni Graphics Device Interface (GDI) per l'output del dispositivo, ad esempio per il disegno e la gestione dei tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="2433d-123">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="2433d-124">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="2433d-124">Kernel32.dll</span></span>|<span data-ttu-id="2433d-125">Funzioni del sistema operativo di basso livello per la gestione delle memoria e delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2433d-125">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="2433d-126">User32.dll</span><span class="sxs-lookup"><span data-stu-id="2433d-126">User32.dll</span></span>|<span data-ttu-id="2433d-127">Funzioni di gestione di Windows per la gestione dei messaggi, i timer, i menu e le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="2433d-127">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="2433d-128">Per la documentazione completa dell'API Windows, vedere l'SDK della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="2433d-128">For complete documentation on the Windows API, see the Platform SDK.</span></span> <span data-ttu-id="2433d-129">Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="2433d-129">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2433d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2433d-130">See also</span></span>

- [<span data-ttu-id="2433d-131">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="2433d-131">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="2433d-132">Specifica di un punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="2433d-132">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="2433d-133">Creazione di una classe che contenga le funzioni di DLL</span><span class="sxs-lookup"><span data-stu-id="2433d-133">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="2433d-134">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="2433d-134">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="2433d-135">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="2433d-135">Calling a DLL Function</span></span>](calling-a-dll-function.md)
