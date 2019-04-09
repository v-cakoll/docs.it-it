---
title: MDA overlappedFreeError
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
author: mairaw
ms.author: mairaw
ms.openlocfilehash: defd7f90fcac8d1e98104796682058638c9bd799
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127075"
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="b4fda-102">MDA overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="b4fda-102">overlappedFreeError MDA</span></span>
<span data-ttu-id="b4fda-103">L'assistente al debug gestito `overlappedFreeError` viene attivato quando il metodo <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> viene chiamato prima del completamento dell'attività sovrapposta.</span><span class="sxs-lookup"><span data-stu-id="b4fda-103">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b4fda-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="b4fda-104">Symptoms</span></span>  
 <span data-ttu-id="b4fda-105">Violazioni di accesso o danneggiamento dell'heap di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b4fda-105">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b4fda-106">Causa</span><span class="sxs-lookup"><span data-stu-id="b4fda-106">Cause</span></span>  
 <span data-ttu-id="b4fda-107">Una struttura sovrapposta è stata liberata prima del completamento dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="b4fda-107">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="b4fda-108">La funzione che usa il puntatore sovrapposto potrebbe scrivere nella struttura in un secondo momento, dopo che è stata liberata.</span><span class="sxs-lookup"><span data-stu-id="b4fda-108">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="b4fda-109">Ciò può causare il danneggiamento dell'heap perché un altro oggetto potrebbe ora occupare tale area.</span><span class="sxs-lookup"><span data-stu-id="b4fda-109">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="b4fda-110">L'assistente al debug gestito potrebbe non rappresentare un errore se l'operazione sovrapposta non è stata avviata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b4fda-110">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b4fda-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="b4fda-111">Resolution</span></span>  
 <span data-ttu-id="b4fda-112">Assicurarsi che l'operazione di I/O che usa la struttura sovrapposta venga completata prima di chiamare il metodo <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>.</span><span class="sxs-lookup"><span data-stu-id="b4fda-112">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b4fda-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="b4fda-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="b4fda-114">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="b4fda-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b4fda-115">Output</span><span class="sxs-lookup"><span data-stu-id="b4fda-115">Output</span></span>  
 <span data-ttu-id="b4fda-116">Questo assistente al debug gestito produce l'output di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b4fda-116">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="b4fda-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="b4fda-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4fda-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4fda-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b4fda-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="b4fda-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b4fda-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b4fda-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
