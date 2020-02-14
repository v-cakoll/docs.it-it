---
title: MDA invalidIUnknown
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 5df9a3f506d8c2de6f1a3125459adc2d59d510bf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217357"
---
# <a name="invalidiunknown-mda"></a>MDA invalidIUnknown
L'assistente al debug gestito `invalidIUnknown` viene attivato quando un puntatore `IUnknown` non valido viene passato dal codice nativo al codice gestito. La ricerca dell'interfaccia `IUnknown` nel puntatore `IUnknown` non riesce.  
  
## <a name="symptoms"></a>Sintomi  
 Si verifica un errore imprevisto durante il marshalling degli argomenti di un puntatore a interfaccia COM.  
  
## <a name="cause"></a>Causa  
 Un'implementazione non valida di `QueryInterface` sull'interfaccia COM passata a CLR.  
  
## <a name="resolution"></a>Risoluzione  
 Correggere l'implementazione di `QueryInterface`.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Descrizione dell'errore.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
