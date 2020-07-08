---
title: MDA marshalling
description: Esaminare l'assistente al debug gestito di marshalling, che viene richiamato se CLR configura le informazioni di marshalling per un parametro del metodo o un campo della struttura.
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
ms.openlocfilehash: 77811c526d1770b91b14aa1199dfc7b3177e6c59
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051155"
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
 La configurazione dell'assistente al debug gestito consente di filtrare le informazioni di marshalling restituite in base ai nomi dei campi o dei metodi coinvolti.  Il seguente esempio mostra l'uso degli elementi `methodFilter`, `fieldFilter`e `match` per specificare i filtri.  L'impostazione dell' `name` attributo su un asterisco ( \* ) corrisponderà a tutti gli elementi.  
  
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
