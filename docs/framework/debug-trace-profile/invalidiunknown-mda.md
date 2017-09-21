---
title: MDA invalidIUnknown
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 970d4dddd473fc671da510cb76b35eca94c55af9
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

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
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)

