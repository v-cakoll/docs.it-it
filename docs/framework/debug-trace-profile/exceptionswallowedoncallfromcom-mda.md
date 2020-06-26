---
title: MDA exceptionSwallowedOnCallFromCom
description: Esaminare l'assistente al debug gestito di exceptionSwallowedOnCallFromCOM in .NET. Questo assistente al debug gestito si verifica se è stata generata un'eccezione, ma non esiste un modo efficace per segnalarlo.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 434f06cf953147d5c245e625db997bed6dbef700
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415953"
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
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
