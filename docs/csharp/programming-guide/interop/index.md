---
title: Interoperabilità (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2965543066b0846a6a4f8a3199590049947122f2
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="7fe99-102">Interoperabilità (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7fe99-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="7fe99-103">L'interoperabilità consente di preservare e sfruttare appieno gli investimenti effettuati in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="7fe99-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="7fe99-104">Il codice eseguito sotto il controllo del Common Language Runtime (CLR) è detto *codice gestito*, mentre quello eseguito all'esterno è detto *codice non gestito*.</span><span class="sxs-lookup"><span data-stu-id="7fe99-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="7fe99-105">Esempi di codice non gestito sono i componenti COM, COM+, C++, i componenti ActiveX e le API Microsoft Win32.</span><span class="sxs-lookup"><span data-stu-id="7fe99-105">COM, COM+, C++ components, ActiveX components, and Microsoft Win32 API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="7fe99-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] consente l'interoperabilità con il codice non gestito tramite i servizi platform invoke, lo spazio dei nomi <xref:System.Runtime.InteropServices>, l'interoperabilità C++ e l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="7fe99-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fe99-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7fe99-107">In This Section</span></span>  
 [<span data-ttu-id="7fe99-108">Cenni preliminari sull'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7fe99-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="7fe99-109">Vengono descritti i metodi per l'interoperabilità tra codice C# gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="7fe99-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="7fe99-110">Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#</span><span class="sxs-lookup"><span data-stu-id="7fe99-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="7fe99-111">Vengono descritte le funzionalità introdotte in Visual C# per facilitare la programmazione di Office.</span><span class="sxs-lookup"><span data-stu-id="7fe99-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="7fe99-112">Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="7fe99-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="7fe99-113">Viene illustrato come usare le proprietà indicizzate per accedere alle proprietà COM con parametri.</span><span class="sxs-lookup"><span data-stu-id="7fe99-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="7fe99-114">Procedura: Usare platform invoke per riprodurre un file audio</span><span class="sxs-lookup"><span data-stu-id="7fe99-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="7fe99-115">Viene descritto come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="7fe99-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="7fe99-116">Procedura dettagliata: Programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="7fe99-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="7fe99-117">Viene illustrato come creare una cartella di lavoro di Excel o un documento di Word contenente un collegamento alla cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7fe99-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="7fe99-118">Esempio di classe COM</span><span class="sxs-lookup"><span data-stu-id="7fe99-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="7fe99-119">Viene illustrato come esporre una classe C# come oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="7fe99-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7fe99-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7fe99-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7fe99-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fe99-121">See Also</span></span>  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7fe99-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7fe99-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7fe99-123">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="7fe99-123">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="7fe99-124">Procedura dettagliata: Programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="7fe99-124">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
