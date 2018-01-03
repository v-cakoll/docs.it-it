---
title: MDA invalidOverlappedToPinvoke
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 395601c6aaff39bf2acb01ae36d306e57566aa4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="fe162-102">MDA invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="fe162-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="fe162-103">L'assistente al debug gestito `invalidOverlappedToPinvoke` viene attivato quando un puntatore sovrapposto che non è stato creato nell'heap di Garbage Collection viene passato a funzioni Win32 specifiche.</span><span class="sxs-lookup"><span data-stu-id="fe162-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe162-104">Per impostazione predefinita, questo assistente al debug gestito viene attivato solo se la chiamata di pInvoke è definita nel codice e tramite il debugger viene segnalato lo stato JustMyCode di ciascun metodo.</span><span class="sxs-lookup"><span data-stu-id="fe162-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="fe162-105">Un debugger che non riconosce JustMyCode, ad esempio MDbg.exe senza estensioni, non attiva questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="fe162-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="fe162-106">L'assistente al debug gestito può essere abilitato per questi debugger usando un file di configurazione e impostando in modo esplicito `justMyCode="false"` nel file con estensione mda.config `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span><span class="sxs-lookup"><span data-stu-id="fe162-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fe162-107">Sintomi</span><span class="sxs-lookup"><span data-stu-id="fe162-107">Symptoms</span></span>  
 <span data-ttu-id="fe162-108">Arresto anomalo o danneggiamento inspiegabile dell'heap.</span><span class="sxs-lookup"><span data-stu-id="fe162-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fe162-109">Causa</span><span class="sxs-lookup"><span data-stu-id="fe162-109">Cause</span></span>  
 <span data-ttu-id="fe162-110">Un puntatore sovrapposto che non è stato creato nell'heap di Garbage Collection viene passato a funzioni del sistema operativo specifiche.</span><span class="sxs-lookup"><span data-stu-id="fe162-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="fe162-111">La tabella seguente mostra le funzioni monitorate dall'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="fe162-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="fe162-112">Modulo</span><span class="sxs-lookup"><span data-stu-id="fe162-112">Module</span></span>|<span data-ttu-id="fe162-113">Funzione</span><span class="sxs-lookup"><span data-stu-id="fe162-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="fe162-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="fe162-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="fe162-116">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="fe162-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="fe162-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="fe162-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="fe162-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="fe162-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="fe162-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="fe162-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="fe162-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="fe162-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="fe162-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="fe162-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="fe162-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="fe162-128">Il rischio di danneggiamento dell'heap è elevato in questa condizione, perché l'oggetto <xref:System.AppDomain> che effettua la chiamata può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="fe162-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="fe162-129">Se <xref:System.AppDomain> viene scaricato, il codice dell'applicazione libera la memoria per il puntatore sovrapposto, causando il danneggiamento al termine dell'operazione, oppure il codice perde la memoria, provocando difficoltà in seguito.</span><span class="sxs-lookup"><span data-stu-id="fe162-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fe162-130">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="fe162-130">Resolution</span></span>  
 <span data-ttu-id="fe162-131">Usare un oggetto <xref:System.Threading.Overlapped>, chiamando il metodo <xref:System.Threading.Overlapped.Pack%2A> per ottenere una struttura <xref:System.Threading.NativeOverlapped> che possa essere passata alla funzione.</span><span class="sxs-lookup"><span data-stu-id="fe162-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="fe162-132">Se <xref:System.AppDomain> viene scaricato, CLR attende il completamento dell'operazione asincrona prima di liberare il puntatore.</span><span class="sxs-lookup"><span data-stu-id="fe162-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fe162-133">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="fe162-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="fe162-134">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="fe162-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fe162-135">Output</span><span class="sxs-lookup"><span data-stu-id="fe162-135">Output</span></span>  
 <span data-ttu-id="fe162-136">Di seguito è riportato un esempio di output di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="fe162-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="fe162-137">Configurazione</span><span class="sxs-lookup"><span data-stu-id="fe162-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe162-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe162-138">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="fe162-139">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="fe162-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="fe162-140">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="fe162-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
