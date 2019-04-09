---
title: MDA memberInfoCacheCreation
ms.date: 03/30/2017
helpviewer_keywords:
- member info cache creation
- MemberInfoCacheCreation MDA
- reflection, run-time errors
- MDAs (managed debugging assistants), cache
- cache [.NET Framework], reflection
- managed debugging assistants (MDAs), cache
- MemberInfo cache
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90f59f4d593a8aa077a6710cc0f5c1747ac1a3ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103766"
---
# <a name="memberinfocachecreation-mda"></a><span data-ttu-id="83a79-102">MDA memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="83a79-102">memberInfoCacheCreation MDA</span></span>
<span data-ttu-id="83a79-103">L'assistente al debug gestito `memberInfoCacheCreation` viene attivato al momento della creazione di una cache <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="83a79-103">The `memberInfoCacheCreation` managed debugging assistant (MDA) is activated when a <xref:System.Reflection.MemberInfo> cache is created.</span></span> <span data-ttu-id="83a79-104">Si tratta di un'indicazione chiara di un programma che usa funzionalità di reflection onerose a livello di risorse.</span><span class="sxs-lookup"><span data-stu-id="83a79-104">This is a strong indication of a program that is making use of resource-expensive reflection features.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="83a79-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="83a79-105">Symptoms</span></span>  
 <span data-ttu-id="83a79-106">Il working set di un programma aumenta perché il programma usa la reflection con uso intensivo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="83a79-106">A program's working set increases because the program is using resource-expensive reflection.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="83a79-107">Causa</span><span class="sxs-lookup"><span data-stu-id="83a79-107">Cause</span></span>  
 <span data-ttu-id="83a79-108">Le operazioni di reflection che richiamano oggetti <xref:System.Reflection.MemberInfo> sono considerate onerose a livello di risorse perché devono leggere i metadati archiviati in pagine ad accesso sporadico e in genere indicano che il programma usa un qualche tipo di scenario di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="83a79-108">Reflection operations that involve <xref:System.Reflection.MemberInfo> objects are considered resource expensive because they must read metadata that is stored in cold pages and in general they indicate the program is using some type of late-bound scenario.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="83a79-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="83a79-109">Resolution</span></span>  
 <span data-ttu-id="83a79-110">Per determinare se il programma usa la reflection, è possibile abilitare questo assistente al debug gestito e quindi eseguire il codice in un debugger o collegare un debugger quando viene attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="83a79-110">You can determine where reflection is being used in your program by enabling this MDA and then running your code in a debugger or attaching with a debugger when the MDA is activated.</span></span> <span data-ttu-id="83a79-111">In un debugger si otterrà un'analisi dello stack che mostra la posizione in cui è stata creata la cache <xref:System.Reflection.MemberInfo> e da tale informazione è possibile determinare dove il programma usa la reflection.</span><span class="sxs-lookup"><span data-stu-id="83a79-111">Under a debugger you will get a stack trace showing where the <xref:System.Reflection.MemberInfo> cache was created and from there you can determine where your program is using reflection.</span></span>  
  
 <span data-ttu-id="83a79-112">La risoluzione dipende dagli obiettivi del codice.</span><span class="sxs-lookup"><span data-stu-id="83a79-112">The resolution is dependent on the objectives of the code.</span></span> <span data-ttu-id="83a79-113">Questo assistente al debug gestito segnala che il programma ha uno scenario di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="83a79-113">This MDA alerts you that your program has a late-bound scenario.</span></span> <span data-ttu-id="83a79-114">È possibile valutare la sostituzione con uno scenario di associazione anticipata oppure esaminare le prestazioni dello scenario di associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="83a79-114">You might want to determine if you can substitute an early-bound scenario or consider the performance of the late bound scenario.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="83a79-115">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="83a79-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="83a79-116">Questo assistente al debug gestito viene attivato ogni volta che viene creata una cache <xref:System.Reflection.MemberInfo>.</span><span class="sxs-lookup"><span data-stu-id="83a79-116">This MDA is activated for every <xref:System.Reflection.MemberInfo> cache that is created.</span></span> <span data-ttu-id="83a79-117">L'impatto sulle prestazioni è trascurabile.</span><span class="sxs-lookup"><span data-stu-id="83a79-117">The performance impact is negligible.</span></span>  
  
## <a name="output"></a><span data-ttu-id="83a79-118">Output</span><span class="sxs-lookup"><span data-stu-id="83a79-118">Output</span></span>  
 <span data-ttu-id="83a79-119">L'assistente al debug gestito genera un messaggio che indica che la cache <xref:System.Reflection.MemberInfo> è stata creata.</span><span class="sxs-lookup"><span data-stu-id="83a79-119">The MDA outputs a message indicating the <xref:System.Reflection.MemberInfo> cache was created.</span></span> <span data-ttu-id="83a79-120">Usare un debugger per ottenere un'analisi dello stack che mostra le posizioni in cui il programma usa la reflection.</span><span class="sxs-lookup"><span data-stu-id="83a79-120">Use a debugger to get a stack trace showing where your program is using reflection.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="83a79-121">Configurazione</span><span class="sxs-lookup"><span data-stu-id="83a79-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="83a79-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="83a79-122">Example</span></span>  
 <span data-ttu-id="83a79-123">Questo codice di esempio attiverà l'assistente al debug gestito `memberInfoCacheCreation`.</span><span class="sxs-lookup"><span data-stu-id="83a79-123">This sample code will activate the `memberInfoCacheCreation` MDA.</span></span>  
  
```csharp
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="83a79-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83a79-124">See also</span></span>

- <xref:System.Reflection.MemberInfo>
- [<span data-ttu-id="83a79-125">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="83a79-125">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
