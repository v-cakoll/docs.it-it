---
title: MDA contextSwitchDeadlock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e67c5c47dbe95d7c2b804f0ae87200db489d0306
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="contextswitchdeadlock-mda"></a>MDA contextSwitchDeadlock
L'assistente al debug gestito `contextSwitchDeadlock` viene attivato quando viene rilevato un deadlock durante un tentativo di transizione del contesto COM.  
  
## <a name="symptoms"></a>Sintomi  
 Il sintomo più comune è che una chiamata su un componente COM non gestito dal codice gestito non restituisce risultati.  Un altro sintomo è l'aumento dell'utilizzo della memoria nel tempo.  
  
## <a name="cause"></a>Causa  
 La causa più probabile è che il thread di un apartment a thread singolo non stia distribuendo i messaggi. Il thread dell'apartment a thread singolo potrebbe essere in attesa senza distribuire i messaggi o eseguire operazioni prolungate che non consentono la distribuzione della coda dei messaggi.  
  
 L'aumento dell'utilizzo della memoria nel tempo è determinato dal thread finalizzatore che tenta di chiamare `Release` su un componente COM non gestito e che il componente non restituisca risultati.  Questo impedisce al finalizzatore di recuperare altri oggetti.  
  
 Per impostazione predefinita, il modello di threading per il thread principale delle applicazioni console Visual Basic è l'apartment a thread singolo. L'assistente al debug gestito viene attivato se un thread dell'apartment a thread singolo usa l'interoperabilità COM direttamente o indirettamente tramite Common Language Runtime o un controllo di terze parti.  Per evitare di attivare l'assistente al debug gestito in un'applicazione console Visual Basic, applicare l'attributo <xref:System.MTAThreadAttribute> al metodo principale o modificare l'applicazione affinché distribuisca i messaggi.  
  
 È possibile che l'assistente al debug gestito venga attivato quando vengono soddisfatte tutte le condizioni seguenti:  
  
-   Un'applicazione crea componenti COM da thread dell'apartment a thread singolo direttamente o indirettamente tramite le librerie.  
  
-   L'applicazione è stata interrotta nel debugger e l'utente ha continuato l'applicazione o eseguito un'operazione del passaggio.  
  
-   Il debug non gestito non è abilitato.  
  
 Per stabilire se l'assistente al debug gestito è stato falsamente abilitato, disabilitare tutti i punti di interruzione, riavviare l'applicazione e consentirne l'esecuzione senza interruzioni. Se l'assistente al debug gestito non è attivata, è probabile che l'attivazione iniziale fosse falsa. In questo caso, disabilitare l'assistente al debug gestito per evitare interferenze con la sessione di debug.  
  
> [!NOTE]
>  L'assistente al debug gestito si trova nel set predefinito per [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] e versioni successive. Quando il processo di hosting è abilitato in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], non è possibile disabilitare gli assistenti al debug gestito che si trovano nel set predefinito. Poiché il processo di hosting è abilitato per impostazione predefinita, sarà necessario disabilitarlo in modo esplicito. Per informazioni su come disabilitare gli assistenti al debug gestito, vedere "Abilitazione e disabilitazione degli assistenti al debug gestito" in [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="resolution"></a>Risoluzione  
 Seguire le regole COM relative alla distribuzione di messaggi di apartment a thread singolo.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Fornisce solo dati sui contesti COM.  
  
## <a name="output"></a>Output  
 Messaggio che descrive il contesto corrente e il contesto di destinazione.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
