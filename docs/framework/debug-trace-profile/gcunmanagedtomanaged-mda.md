---
title: MDA gcUnmanagedToManaged
description: Esaminare l'assistente al debug gestito di gcManagedToUnmanaged in .NET. Questo assistente al debug gestito può essere attivato a causa del danneggiamento dell'heap di Garbage Collection durante la transizione al codice
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
ms.openlocfilehash: 320d55224e6a204d330447d6c68eabe0fa6cf892
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415901"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="dd4b1-104">MDA gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="dd4b1-104">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="dd4b1-105">L'assistente al debug gestito `gcUnmanagedToManaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="dd4b1-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="dd4b1-106">Symptoms</span></span>  
 <span data-ttu-id="dd4b1-107">Un'applicazione in cui vengono eseguiti componenti utente non gestiti mediante platform invoke e COM sta causando una violazione di accesso non deterministico in CLR.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="dd4b1-108">Causa</span><span class="sxs-lookup"><span data-stu-id="dd4b1-108">Cause</span></span>  
 <span data-ttu-id="dd4b1-109">Se in un'applicazione sono in esecuzione componenti utente non gestiti, è possibile che questi ultimi abbiano danneggiato l'heap sottoposto a Garbage Collection,</span><span class="sxs-lookup"><span data-stu-id="dd4b1-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="dd4b1-110">provocando una violazione di accesso in CLR al tentativo del Garabage Collector di scorrere l'oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="dd4b1-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="dd4b1-111">Resolution</span></span>  
 <span data-ttu-id="dd4b1-112">L'abilitazione di questo assistente riduce il periodo compreso tra il danneggiamento dell'heap sottoposto a Garbage Collection da parte del componente non gestito e la generazione della violazione di accesso mediante l'imposizione di un'operazione di Garbage Collection prima di ogni transizione gestita.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="dd4b1-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="dd4b1-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="dd4b1-114">Viene causata una Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="dd4b1-115">Output</span><span class="sxs-lookup"><span data-stu-id="dd4b1-115">Output</span></span>  
 <span data-ttu-id="dd4b1-116">Questo assistente al debug gestito non produce output.</span><span class="sxs-lookup"><span data-stu-id="dd4b1-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="dd4b1-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="dd4b1-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd4b1-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dd4b1-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="dd4b1-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="dd4b1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="dd4b1-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="dd4b1-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="dd4b1-121">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="dd4b1-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
