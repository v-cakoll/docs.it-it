---
title: MDA invalidOverlappedToPinvoke
description: Esaminare l'assistente al debug gestito di invalidOverlappedToPinvoke in .NET, che può essere attivato durante un arresto anomalo o un danneggiamento dell'heap inspiegabile.
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
ms.openlocfilehash: 162efd55bf636cf2e8698706bd011379f2f6f11f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051701"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="6198f-103">MDA invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="6198f-103">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="6198f-104">L'assistente al debug gestito `invalidOverlappedToPinvoke` viene attivato quando un puntatore sovrapposto che non è stato creato nell'heap di Garbage Collection viene passato a funzioni Win32 specifiche.</span><span class="sxs-lookup"><span data-stu-id="6198f-104">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6198f-105">Per impostazione predefinita, questo assistente al debug gestito viene attivato solo se la chiamata di pInvoke è definita nel codice e tramite il debugger viene segnalato lo stato JustMyCode di ciascun metodo.</span><span class="sxs-lookup"><span data-stu-id="6198f-105">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="6198f-106">Un debugger che non riconosce JustMyCode, ad esempio MDbg.exe senza estensioni, non attiva questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6198f-106">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="6198f-107">L'assistente al debug gestito può essere abilitato per questi debugger usando un file di configurazione e impostando in modo esplicito `justMyCode="false"` nel file con estensione mda.config `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span><span class="sxs-lookup"><span data-stu-id="6198f-107">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="6198f-108">Sintomi</span><span class="sxs-lookup"><span data-stu-id="6198f-108">Symptoms</span></span>  
 <span data-ttu-id="6198f-109">Arresto anomalo o danneggiamento inspiegabile dell'heap.</span><span class="sxs-lookup"><span data-stu-id="6198f-109">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="6198f-110">Causa</span><span class="sxs-lookup"><span data-stu-id="6198f-110">Cause</span></span>  
 <span data-ttu-id="6198f-111">Un puntatore sovrapposto che non è stato creato nell'heap di Garbage Collection viene passato a funzioni del sistema operativo specifiche.</span><span class="sxs-lookup"><span data-stu-id="6198f-111">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="6198f-112">La tabella seguente mostra le funzioni monitorate dall'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6198f-112">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="6198f-113">Modulo</span><span class="sxs-lookup"><span data-stu-id="6198f-113">Module</span></span>|<span data-ttu-id="6198f-114">Funzione</span><span class="sxs-lookup"><span data-stu-id="6198f-114">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="6198f-115">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-115">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="6198f-116">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-116">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="6198f-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-117">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="6198f-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-118">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="6198f-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-119">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="6198f-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-120">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="6198f-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-121">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="6198f-122">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-122">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="6198f-123">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-123">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="6198f-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-124">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="6198f-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-125">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="6198f-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-126">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="6198f-127">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-127">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="6198f-128">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="6198f-128">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="6198f-129">Il rischio di danneggiamento dell'heap è elevato in questa condizione, perché l'oggetto <xref:System.AppDomain> che effettua la chiamata può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="6198f-129">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="6198f-130">Se <xref:System.AppDomain> viene scaricato, il codice dell'applicazione libera la memoria per il puntatore sovrapposto, causando il danneggiamento al termine dell'operazione, oppure il codice perde la memoria, provocando difficoltà in seguito.</span><span class="sxs-lookup"><span data-stu-id="6198f-130">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="6198f-131">Soluzione</span><span class="sxs-lookup"><span data-stu-id="6198f-131">Resolution</span></span>  
 <span data-ttu-id="6198f-132">Usare un oggetto <xref:System.Threading.Overlapped>, chiamando il metodo <xref:System.Threading.Overlapped.Pack%2A> per ottenere una struttura <xref:System.Threading.NativeOverlapped> che possa essere passata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="6198f-132">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="6198f-133">Se <xref:System.AppDomain> viene scaricato, CLR attende il completamento dell'operazione asincrona prima di liberare il puntatore.</span><span class="sxs-lookup"><span data-stu-id="6198f-133">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6198f-134">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6198f-134">Effect on the Runtime</span></span>  
 <span data-ttu-id="6198f-135">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="6198f-135">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6198f-136">Output</span><span class="sxs-lookup"><span data-stu-id="6198f-136">Output</span></span>  
 <span data-ttu-id="6198f-137">Di seguito è riportato un esempio di output di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6198f-137">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="6198f-138">Configurazione</span><span class="sxs-lookup"><span data-stu-id="6198f-138">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6198f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6198f-139">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="6198f-140">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="6198f-140">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="6198f-141">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="6198f-141">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
