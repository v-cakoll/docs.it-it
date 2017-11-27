---
title: MDA exceptionSwallowedOnCallFromCom
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d68e3f8659b0d5fe212c58443fe9a8b42f9cef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="exceptionswallowedoncallfromcom-mda"></a>MDA exceptionSwallowedOnCallFromCom
L'assistente al debug gestito `exceptionSwallowedOnCallFromCOM` viene attivato alla generazione di un'eccezione da parte del codice Common Language Runtime (CLR) chiamato da COM mediante un metodo che non presenta un tipo restituito HRESULT non gestito.  
  
## <a name="symptoms"></a>Sintomi  
 Il valore restituito per una chiamata a un componente gestito da COM corrisponde a FALSE o a 0. In alternativa, se il metodo presenta un tipo restituito void, potrebbero non esservi indicazioni relative alla generazione di un'eccezione durante l'esecuzione del metodo. In tal caso, l'eccezione verrà intercettata senza avviso e l'esecuzione tornerà al chiamante COM.  
  
## <a name="cause"></a>Causa  
 È stata generata un'eccezione, ma non esiste un modo valido per segnalarla.  
  
## <a name="resolution"></a>Risoluzione  
 Messaggio esclusivamente informativo. Non indica necessariamente la presenza di un bug.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Si limita a restituire dati relativi alle eccezioni intercettate senza avviso.  
  
## <a name="output"></a>Output  
 Messaggio informativo contenente il nome del metodo, il nome del tipo e il messaggio dell'eccezione.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
