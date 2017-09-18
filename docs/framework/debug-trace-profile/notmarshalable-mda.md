---
title: notMarshalable (MDA)
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
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1dcce60b18169e1ca7c87440cec7e36e08634461
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="notmarshalable-mda"></a>notMarshalable (MDA)
L'assistente al debug gestito `notMarshalable` viene attivato quando Common Language Runtime rileva un puntatore a interfaccia COM senza un proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.  
  
## <a name="symptoms"></a>Sintomi  
 Le chiamate non vengono eseguite oppure vengono eseguite nel contesto errato per i puntatori a interfaccia COM.  
  
## <a name="cause"></a>Causa  
 Nessun proxy/stub registrato valido oppure un'implementazione non corretta dell'interfaccia `IMarshal` durante il marshalling dell'interfaccia tra i vari contesti.  
  
## <a name="resolution"></a>Risoluzione  
 Assicurarsi di disporre di uno stub proxy registrato e che l'implementazione dell'interfaccia `IMarshal` sia valida.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto sull'ambiente di esecuzione.  
  
## <a name="output"></a>Output  
 Messaggio che descrive il problema.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)

