---
title: MDA pInvokeStackImbalance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b33a3edc5780ecf07e7809ca327a304d748110f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pinvokestackimbalance-mda"></a>MDA pInvokeStackImbalance
L'assistente al debug gestito `pInvokeStackImbalance` viene attivato quando CLR rileva che la profondità dello stack dopo una chiamata PInvoke non corrisponde a quella prevista, in base alla convenzione di chiamata specificata nell'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> e alla dichiarazione dei parametri nella firma gestita.  
  
> [!NOTE]
>  L'assistente al debug gestito `pInvokeStackImbalance` viene implementato solo per piattaforme x86 a 32 bit.  
  
> [!NOTE]
>  In .NET Framework versione 3.5, l'assistente al debug gestito `pInvokeStackImbalance` è disabilitato per impostazione predefinita. Quando si usa .NET Framework versione 3.5 con Visual Studio 2005, l'assistente al debug gestito `pInvokeStackImbalance` viene visualizzato nell'elenco **Assistenti al debug gestito** nella finestra di dialogo **Eccezioni** (visualizzata quando si fa clic su **Eccezioni** nel menu **Debug**). Tuttavia, quando si seleziona o si deseleziona la casella di controllo **Generata** per `pInvokeStackImbalance` l'assistente al debug gestito non viene abilitato o disabilitato. L'opzione controlla solo se Visual Studio genera un'eccezione quando viene attivato l'assistente al debug gestito.  
  
## <a name="symptoms"></a>Sintomi  
 Un'applicazione rileva una violazione di accesso o un danneggiamento della memoria durante o dopo una chiamata PInvoke.  
  
## <a name="cause"></a>Causa  
 La firma gestita della chiamata PInvoke potrebbe non corrispondere alla firma non gestita del metodo chiamato.  Questa mancata corrispondenza può essere causata dalla firma gestita che non dichiara il numero corretto di parametri o non specifica le dimensioni appropriate per i parametri.  L'assistente al debug gestito può essere attivato anche perché la convenzione di chiamata specificata dall'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> non corrisponde alla convenzione di chiamata non gestita.  
  
## <a name="resolution"></a>Risoluzione  
 Rivedere la firma PInvoke gestita e la convenzione di chiamata per verificare la corrispondenza con la firma e la convenzione di chiamata della destinazione nativa.  Provare a specificare in modo esplicito la convenzione di chiamata su entrambi i lati, gestito e non gestito. È anche possibile, anche se improbabile, che la funzione non gestita abbia sbilanciato lo stack per altri motivi, ad esempio un bug nel compilatore non gestito.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Forza l'uso del percorso non ottimizzato in CLR per tutte le chiamate PInvoke.  
  
## <a name="output"></a>Output  
 Il messaggio dell'assistente al debug gestito fornisce il nome della chiamata al metodo PInvoke che sta causando lo sbilanciamento dello stack.  Un messaggio di esempio di una chiamata PInvoke al metodo `SampleMethod` è:  
  
```  
A call to PInvoke function 'SampleMethod' has unbalanced the stack.   
This is likely because the managed PInvoke signature does not match   
the unmanaged target signature. Check that the calling convention and   
parameters of the PInvoke signature match the target unmanaged signature.  
```  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeStackImbalance />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
