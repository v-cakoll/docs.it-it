---
title: Interoperabilità - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: e53465066cf27a5f46c66ac73ee242370be23395
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84242007"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="d924a-102">Interoperabilità (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d924a-102">Interoperability (C# Programming Guide)</span></span>

<span data-ttu-id="d924a-103">L'interoperabilità consente di preservare e sfruttare appieno gli investimenti effettuati in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="d924a-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="d924a-104">Il codice eseguito sotto il controllo del Common Language Runtime (CLR) è detto *codice gestito*, mentre quello eseguito all'esterno è detto *codice non gestito*.</span><span class="sxs-lookup"><span data-stu-id="d924a-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="d924a-105">Esempi di codice non gestito sono i componenti COM, COM+, C++, i componenti ActiveX e le API Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d924a-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
<span data-ttu-id="d924a-106">.NET consente l'interoperabilità con codice non gestito tramite platform invoke servizi, lo <xref:System.Runtime.InteropServices> spazio dei nomi, l'interoperabilità C++ e l'interoperabilità COM (interoperabilità COM).</span><span class="sxs-lookup"><span data-stu-id="d924a-106">.NET enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d924a-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d924a-107">In This Section</span></span>  
 [<span data-ttu-id="d924a-108">Cenni preliminari sull'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="d924a-108">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="d924a-109">Vengono descritti i metodi per l'interoperabilità tra codice C# gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="d924a-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="d924a-110">Come accedere agli oggetti di interoperabilità di Office usando le funzionalità di C#</span><span class="sxs-lookup"><span data-stu-id="d924a-110">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="d924a-111">Vengono descritte le funzionalità introdotte in Visual C# per facilitare la programmazione di Office.</span><span class="sxs-lookup"><span data-stu-id="d924a-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="d924a-112">Come usare proprietà indicizzate nella programmazione dell'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="d924a-112">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="d924a-113">Viene illustrato come usare le proprietà indicizzate per accedere alle proprietà COM con parametri.</span><span class="sxs-lookup"><span data-stu-id="d924a-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="d924a-114">Come usare platform invoke per riprodurre un file WAV</span><span class="sxs-lookup"><span data-stu-id="d924a-114">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="d924a-115">Viene descritto come usare i servizi platform invoke per riprodurre un file audio con estensione wav nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="d924a-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="d924a-116">Procedura dettagliata: Programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="d924a-116">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="d924a-117">Viene illustrato come creare una cartella di lavoro di Excel o un documento di Word contenente un collegamento alla cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d924a-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="d924a-118">Esempio di classe COM</span><span class="sxs-lookup"><span data-stu-id="d924a-118">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="d924a-119">Viene illustrato come esporre una classe C# come oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="d924a-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d924a-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d924a-120">C# Language Specification</span></span>  

<span data-ttu-id="d924a-121">Per altre informazioni, vedere [Concetti di base](~/_csharplang/spec/unsafe-code.md) nella [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="d924a-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="d924a-122">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="d924a-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d924a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d924a-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d924a-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d924a-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d924a-125">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="d924a-125">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="d924a-126">Procedura dettagliata: Programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="d924a-126">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
