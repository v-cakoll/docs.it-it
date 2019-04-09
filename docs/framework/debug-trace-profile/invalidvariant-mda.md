---
title: MDA invalidVariant
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64f5a4425d70974bae8c4f7bec28041e687fe95f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228484"
---
# <a name="invalidvariant-mda"></a>MDA invalidVariant
L'assistente al debug gestito `invalidVariant` viene attivato quando viene rilevata una struttura `VARIANT` non valida durante una chiamata dal codice nativo o non gestito al codice gestito.  
  
## <a name="symptoms"></a>Sintomi  
 Comportamento imprevisto durante una transizione tra il codice nativo e quello gestito in cui è previsto il marshalling di una struttura `VARIANT` a un oggetto.  
  
## <a name="cause"></a>Causa  
 Il codice nativo passa al codice gestito una struttura `VARIANT` in un formato non corretto.  Il runtime tenta il marshalling di questa struttura `VARIANT` a un oggetto e, se non ritiene valida la struttura `VARIANT`, attiva l'assistente al debug gestito. Tra gli esempi di strutture `VARIANT` non valide sono incluse strutture `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o strutture `VARIANT` con `VARTYPE` VT_VARIANT.  
  
## <a name="resolution"></a>Risoluzione  
 Il codice nativo o non gestito che passa la struttura `VARIANT` deve verificare la correttezza del formato e dell'inizializzazione della struttura `VARIANT`.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non produce effetti sul comportamento del runtime.  
  
## <a name="output"></a>Output  
 Un messaggio dell'assistente al debug gestito in cui è indicato che il runtime ha rilevato una struttura `VARIANT` non valida passata al codice gestito da un modulo non gestito.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
