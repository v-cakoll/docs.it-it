---
title: MDA marshalling
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: f7bb630d3a1e832cf6bf083ce4cf603034248ceb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217326"
---
# <a name="marshaling-mda"></a>MDA marshalling
L'assistente al debug gestito `marshaling` viene attivato quando CLR configura le informazioni di marshalling per un parametro di un metodo o un campo di una struttura. Questo assistente al debug gestito non funziona per gli assembly con compilazione JIT.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito visualizza il tipo del parametro o del campo nei contesti gestiti e non gestiti e la struttura o il metodo contenente il tipo.  Di seguito viene riportato un esempio di output per un campo.  
  
```output
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a>Configurazione  
 La configurazione dell'assistente al debug gestito consente di filtrare le informazioni di marshalling restituite in base ai nomi dei campi o dei metodi coinvolti.  Il seguente esempio mostra l'uso degli elementi `methodFilter`, `fieldFilter`e `match` per specificare i filtri.  L'impostazione dell'attributo `name` su un asterisco (\*) corrisponderà a tutti gli elementi.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
