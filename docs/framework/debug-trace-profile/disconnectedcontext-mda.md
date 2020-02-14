---
title: MDA disconnectedContext
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 3d04e304a6b30fe6fd4deeda5a97007f11ee7b13
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216540"
---
# <a name="disconnectedcontext-mda"></a>MDA disconnectedContext
L'assistente al debug gestito `disconnectedContext` è attivato quando CLR tenta la transizione a un apartment o contesto disconnesso durante la gestione di una richiesta relativa a un oggetto COM.  
  
## <a name="symptoms"></a>Sintomi  
 Le chiamate effettuate a un [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) sono recapitate al componente COM sottostante nell'apartment o contesto corrente invece che a quello in cui si trovano. Ciò può provocare il danneggiamento o la perdita di dati, se il componente COM non è a thread multipli, ad esempio nel caso di componenti di tipo apartment a thread singolo. In alternativa, se l'oggetto RCW stesso è un proxy, la chiamata potrebbe provocare la generazione di un'eccezione <xref:System.Runtime.InteropServices.COMException> con HRESULT di tipo RPC_E_WRONG_THREAD.  
  
## <a name="cause"></a>Causa  
 L'apartment o contesto OLE è stato arrestato quando CLR ha tentato di eseguirvi la transizione. Nella maggior parte dei casi, ciò è dovuto dall'arresto di apartment STA prima del rilascio completo di tutti i componenti COM di proprietà dell'apartment. Questo può essere il risultato di una chiamata esplicita da codice utente a un oggetto RCW oppure può verificarsi quando CLR sta modificando il componente COM, ad esempio quando CLR rilascia il componente COM dopo che l'oggetto RCW associato è stato sottoposto a Garbage Collection.  
  
## <a name="resolution"></a>Risoluzione  
 Per evitare questo problema, assicurarsi che il thread proprietario dell'apartment STA non termini prima che l'applicazione abbia completato le operazioni relative a tutti gli oggetti presenti nell'apartment. Anche nel caso dei contesti, è necessario assicurarsi che non siano arrestati prima che l'applicazione abbia completato le operazioni relative a tutti i componenti COM presenti nel contesto.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Fornisce solo dati sul contesto disconnesso.  
  
## <a name="output"></a>Output  
 Fornisce il cookie del contesto dell'apartment o del contesto disconnesso.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
