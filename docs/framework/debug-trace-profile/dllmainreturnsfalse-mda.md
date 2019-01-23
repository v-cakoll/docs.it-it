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
ms.openlocfilehash: c513ba06ac79eb3da229605120c4f59ab8d32665
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554543"
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
