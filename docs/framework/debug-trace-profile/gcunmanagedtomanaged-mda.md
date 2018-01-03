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
ms.workload: dotnet
ms.openlocfilehash: 3bc02f12a49ef65614114a056f9263f9ef7f5322
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gcunmanagedtomanaged-mda"></a>MDA gcUnmanagedToManaged
L'assistente al debug gestito `gcUnmanagedToManaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.  
  
## <a name="symptoms"></a>Sintomi  
 Un'applicazione in cui vengono eseguiti componenti utente non gestiti mediante platform invoke e COM sta causando una violazione di accesso non deterministico in CLR.  
  
## <a name="cause"></a>Causa  
 Se in un'applicazione sono in esecuzione componenti utente non gestiti, è possibile che questi ultimi abbiano danneggiato l'heap sottoposto a Garbage Collection, provocando una violazione di accesso in CLR al tentativo del Garabage Collector di scorrere l'oggetto grafico.  
  
## <a name="resolution"></a>Risoluzione  
 L'abilitazione di questo assistente riduce il periodo compreso tra il danneggiamento dell'heap sottoposto a Garbage Collection da parte del componente non gestito e la generazione della violazione di accesso mediante l'imposizione di un'operazione di Garbage Collection prima di ogni transizione gestita.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Viene causata una Garbage Collection ogni volta che un thread passa dal codice non gestito al codice gestito.  
  
## <a name="output"></a>Output  
 Questo assistente al debug gestito non produce output.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
