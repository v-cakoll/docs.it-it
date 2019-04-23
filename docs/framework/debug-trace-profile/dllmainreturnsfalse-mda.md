---
title: MDA dllMainReturnsFalse
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd987cea78d082eee26032d5f98a54dc0cd3e1d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072623"
---
# <a name="dllmainreturnsfalse-mda"></a>MDA dllMainReturnsFalse
L'assistente al debug gestito `dllMainReturnsFalse` viene attivato se la funzione `DllMain` gestita di un assembly utente, chiamata per il motivo DLL_PROCESS_ATTACH, restituisce FALSE.  
  
## <a name="symptoms"></a>Sintomi  
 La funzione `DllMain` ha restituito FALSE, che indica che non è stata eseguita correttamente. Questo può causare problemi non determinati perché le funzioni `DllMain` contengono in genere un codice di inizializzazione importante.  
  
## <a name="cause"></a>Causa  
 La funzione `DllMain` viene chiamata con il motivo DLL_PROCESS_ATTACH per l'inizializzazione della DLL nel carico. Se restituisce FALSE, significa che l'inizializzazione della DLL non è riuscita.  
  
## <a name="resolution"></a>Risoluzione  
 Analizzare il codice della funzione `DllMain` della DLL non riuscita e identificare la causa dell'errore di inizializzazione.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Fornisce solo dati sul valore restituito per `DllMain`.  
  
## <a name="output"></a>Output  
 Messaggio indicante che una funzione `DllMain`, chiamata per il motivo DLL_PROCESS_ATTACH, ha restituito FALSE. Si noti che questo assistente al debug gestito viene attivato solo se si implementa `DllMain` nel codice gestito.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
