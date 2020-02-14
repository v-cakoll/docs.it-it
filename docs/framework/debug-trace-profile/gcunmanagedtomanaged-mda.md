---
title: MDA gcUnmanagedToManaged
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: dd4080870ae88da8d4e2055369cd36f3981f2eac
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216448"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="66801-102">MDA gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="66801-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="66801-103">L'assistente al debug gestito `gcUnmanagedToManaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="66801-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="66801-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="66801-104">Symptoms</span></span>  
 <span data-ttu-id="66801-105">Un'applicazione in cui vengono eseguiti componenti utente non gestiti mediante platform invoke e COM sta causando una violazione di accesso non deterministico in CLR.</span><span class="sxs-lookup"><span data-stu-id="66801-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="66801-106">Causa</span><span class="sxs-lookup"><span data-stu-id="66801-106">Cause</span></span>  
 <span data-ttu-id="66801-107">Se in un'applicazione sono in esecuzione componenti utente non gestiti, è possibile che questi ultimi abbiano danneggiato l'heap sottoposto a Garbage Collection,</span><span class="sxs-lookup"><span data-stu-id="66801-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="66801-108">provocando una violazione di accesso in CLR al tentativo del Garabage Collector di scorrere l'oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="66801-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="66801-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="66801-109">Resolution</span></span>  
 <span data-ttu-id="66801-110">L'abilitazione di questo assistente riduce il periodo compreso tra il danneggiamento dell'heap sottoposto a Garbage Collection da parte del componente non gestito e la generazione della violazione di accesso mediante l'imposizione di un'operazione di Garbage Collection prima di ogni transizione gestita.</span><span class="sxs-lookup"><span data-stu-id="66801-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="66801-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="66801-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="66801-112">Viene causata una Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="66801-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="66801-113">Output</span><span class="sxs-lookup"><span data-stu-id="66801-113">Output</span></span>  
 <span data-ttu-id="66801-114">Questo assistente al debug gestito non produce output.</span><span class="sxs-lookup"><span data-stu-id="66801-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="66801-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="66801-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66801-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66801-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="66801-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="66801-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="66801-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="66801-118">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="66801-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="66801-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
