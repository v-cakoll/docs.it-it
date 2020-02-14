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

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
