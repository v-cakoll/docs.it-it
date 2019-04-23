---
title: MDA gcManagedToUnmanaged
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bb4779e300df71a5d075a322bcac8398ce42f34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204276"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="1b1b2-102">MDA gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="1b1b2-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="1b1b2-103">L'assistente al debug gestito `gcManagedToUnmanaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice gestito al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1b1b2-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="1b1b2-104">Symptoms</span></span>  
 <span data-ttu-id="1b1b2-105">Un componente utente non gestito genera una violazione di accesso quando si cerca di usare un oggetto gestito esposto a COM.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="1b1b2-106">L'oggetto COM appare come rilasciato</span><span class="sxs-lookup"><span data-stu-id="1b1b2-106">The COM object appears to have been released.</span></span> <span data-ttu-id="1b1b2-107">e la violazione di accesso è non deterministica.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1b1b2-108">Causa</span><span class="sxs-lookup"><span data-stu-id="1b1b2-108">Cause</span></span>  
 <span data-ttu-id="1b1b2-109">Se un componente non gestito non esegue correttamente il conteggio dei riferimenti a un oggetto COM gestito, il runtime potrebbe eseguire una Garbage Collection di un oggetto gestito esposto a COM mentre il componente gestito contiene ancora un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="1b1b2-110">Il runtime chiama il metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante le Garbage Collection. In questo modo, se il componente utente usa l'oggetto prima che si verifichi la Garbage Collection, non sarà ancora stato sottoposto all'operazione.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="1b1b2-111">Da ciò deriva il non determinismo.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1b1b2-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1b1b2-112">Resolution</span></span>  
 <span data-ttu-id="1b1b2-113">L'attivazione di questo assistente consente di ridurre il periodo compreso tra il momento in cui l'oggetto è disponibile per la Garbage Collection e la chiamata di <xref:System.Runtime.InteropServices.Marshal.Release%2A> rendendo possibile tenere traccia del componente non gestito che tenta per primo di accedere all'oggetto sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1b1b2-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="1b1b2-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="1b1b2-115">Viene causata una Garbage Collection ogni volta che un thread passa dal codice gestito al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1b1b2-116">Output</span><span class="sxs-lookup"><span data-stu-id="1b1b2-116">Output</span></span>  
 <span data-ttu-id="1b1b2-117">Questo assistente al debug gestito non produce output.</span><span class="sxs-lookup"><span data-stu-id="1b1b2-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1b1b2-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="1b1b2-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b1b2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1b2-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="1b1b2-120">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="1b1b2-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1b1b2-121">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="1b1b2-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
- [<span data-ttu-id="1b1b2-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="1b1b2-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
