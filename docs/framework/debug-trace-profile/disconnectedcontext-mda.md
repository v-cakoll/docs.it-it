---
title: MDA disconnectedContext
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
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
caps.latest.revision: 14
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 818e33b3e332f2170b4dd4f37e5a44ce31188769
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="disconnectedcontext-mda"></a>MDA disconnectedContext
L'assistente al debug gestito `disconnectedContext` è attivato quando CLR tenta la transizione a un apartment o contesto disconnesso durante la gestione di una richiesta relativa a un oggetto COM.  
  
## <a name="symptoms"></a>Sintomi  
 Le chiamate effettuate a un [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) sono recapitate al componente COM sottostante nell'apartment o contesto corrente invece che a quello in cui si trovano. Ciò può provocare il danneggiamento o la perdita di dati, se il componente COM non è a thread multipli, ad esempio nel caso di componenti di tipo apartment a thread singolo. In alternativa, se l'oggetto RCW stesso è un proxy, la chiamata potrebbe provocare la generazione di un'eccezione <xref:System.Runtime.InteropServices.COMException> con HRESULT di tipo RPC_E_WRONG_THREAD.  
  
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
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)

