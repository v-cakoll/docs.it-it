---
title: invalidFunctionPointerInDelegate (MDA)
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb33d2cddab22ad2072354ba543d2cd6a60a668
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218277"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="adbfa-102">invalidFunctionPointerInDelegate (MDA)</span><span class="sxs-lookup"><span data-stu-id="adbfa-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="adbfa-103">L'assistente al debug gestito `invalidFunctionPointerInDelegate` viene attivato quando viene passato un puntatore a funzione non valido per costruire un delegato su un puntatore a funzione nativo.</span><span class="sxs-lookup"><span data-stu-id="adbfa-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="adbfa-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="adbfa-104">Symptoms</span></span>  
 <span data-ttu-id="adbfa-105">Violazioni di accesso o danneggiamento imprevisto della memoria quando viene usato un delegato su un puntatore a funzione.</span><span class="sxs-lookup"><span data-stu-id="adbfa-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="adbfa-106">Causa</span><span class="sxs-lookup"><span data-stu-id="adbfa-106">Cause</span></span>  
 <span data-ttu-id="adbfa-107">È stato specificato un puntatore a funzione non valido.</span><span class="sxs-lookup"><span data-stu-id="adbfa-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="adbfa-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="adbfa-108">Resolution</span></span>  
 <span data-ttu-id="adbfa-109">Specificare un puntatore a funzione valido</span><span class="sxs-lookup"><span data-stu-id="adbfa-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="adbfa-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="adbfa-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="adbfa-111">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="adbfa-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="adbfa-112">Output</span><span class="sxs-lookup"><span data-stu-id="adbfa-112">Output</span></span>  
 <span data-ttu-id="adbfa-113">Il puntatore a funzione non valido.</span><span class="sxs-lookup"><span data-stu-id="adbfa-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="adbfa-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="adbfa-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="adbfa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adbfa-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="adbfa-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="adbfa-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="adbfa-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="adbfa-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
