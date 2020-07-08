---
title: invalidFunctionPointerInDelegate (MDA)
description: Esaminare l'assistente al debug gestito invalidFunctionPointerInDelegate, che viene richiamato se viene passato un puntatore a funzione non valido per creare un delegato.
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
ms.openlocfilehash: a17427d117c62ba782af3c9549c84623a3013b06
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051740"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="839ce-103">invalidFunctionPointerInDelegate (MDA)</span><span class="sxs-lookup"><span data-stu-id="839ce-103">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="839ce-104">L'assistente al debug gestito `invalidFunctionPointerInDelegate` viene attivato quando viene passato un puntatore a funzione non valido per costruire un delegato su un puntatore a funzione nativo.</span><span class="sxs-lookup"><span data-stu-id="839ce-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="839ce-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="839ce-105">Symptoms</span></span>  
 <span data-ttu-id="839ce-106">Violazioni di accesso o danneggiamento imprevisto della memoria quando viene usato un delegato su un puntatore a funzione.</span><span class="sxs-lookup"><span data-stu-id="839ce-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="839ce-107">Causa</span><span class="sxs-lookup"><span data-stu-id="839ce-107">Cause</span></span>  
 <span data-ttu-id="839ce-108">È stato specificato un puntatore a funzione non valido.</span><span class="sxs-lookup"><span data-stu-id="839ce-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="839ce-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="839ce-109">Resolution</span></span>  
 <span data-ttu-id="839ce-110">Specificare un puntatore a funzione valido</span><span class="sxs-lookup"><span data-stu-id="839ce-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="839ce-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="839ce-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="839ce-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="839ce-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="839ce-113">Output</span><span class="sxs-lookup"><span data-stu-id="839ce-113">Output</span></span>  
 <span data-ttu-id="839ce-114">Il puntatore a funzione non valido.</span><span class="sxs-lookup"><span data-stu-id="839ce-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="839ce-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="839ce-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="839ce-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="839ce-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="839ce-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="839ce-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="839ce-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="839ce-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
