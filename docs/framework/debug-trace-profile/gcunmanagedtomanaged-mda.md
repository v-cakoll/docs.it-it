---
title: MDA gcUnmanagedToManaged
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e8d2391ba9ba1d17f2cbce54f52863f74a5dc646
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="eaa4e-102">MDA gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="eaa4e-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="eaa4e-103">L'assistente al debug gestito `gcUnmanagedToManaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="eaa4e-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="eaa4e-104">Symptoms</span></span>  
 <span data-ttu-id="eaa4e-105">Un'applicazione in cui vengono eseguiti componenti utente non gestiti mediante platform invoke e COM sta causando una violazione di accesso non deterministico in CLR.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="eaa4e-106">Causa</span><span class="sxs-lookup"><span data-stu-id="eaa4e-106">Cause</span></span>  
 <span data-ttu-id="eaa4e-107">Se in un'applicazione sono in esecuzione componenti utente non gestiti, è possibile che questi ultimi abbiano danneggiato l'heap sottoposto a Garbage Collection,</span><span class="sxs-lookup"><span data-stu-id="eaa4e-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="eaa4e-108">provocando una violazione di accesso in CLR al tentativo del Garabage Collector di scorrere l'oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="eaa4e-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="eaa4e-109">Resolution</span></span>  
 <span data-ttu-id="eaa4e-110">L'abilitazione di questo assistente riduce il periodo compreso tra il danneggiamento dell'heap sottoposto a Garbage Collection da parte del componente non gestito e la generazione della violazione di accesso mediante l'imposizione di un'operazione di Garbage Collection prima di ogni transizione gestita.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="eaa4e-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="eaa4e-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="eaa4e-112">Viene causata una Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="eaa4e-113">Output</span><span class="sxs-lookup"><span data-stu-id="eaa4e-113">Output</span></span>  
 <span data-ttu-id="eaa4e-114">Questo assistente al debug gestito non produce output.</span><span class="sxs-lookup"><span data-stu-id="eaa4e-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="eaa4e-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="eaa4e-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eaa4e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaa4e-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="eaa4e-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="eaa4e-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="eaa4e-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="eaa4e-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
 [<span data-ttu-id="eaa4e-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="eaa4e-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
