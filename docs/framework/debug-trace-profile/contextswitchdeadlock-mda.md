---
title: MDA contextSwitchDeadlock
ms.date: 03/30/2017
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
ms.openlocfilehash: e3fc4a2cb35cdcc713ba0ef362071083af08a27b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217562"
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

- Un'applicazione crea componenti COM da thread dell'apartment a thread singolo direttamente o indirettamente tramite le librerie.

- L'applicazione è stata interrotta nel debugger e l'utente ha continuato l'applicazione o eseguito un'operazione del passaggio.

- Il debug non gestito non è abilitato.

Per stabilire se l'assistente al debug gestito è stato falsamente abilitato, disabilitare tutti i punti di interruzione, riavviare l'applicazione e consentirne l'esecuzione senza interruzioni. Se l'assistente al debug gestito non è attivata, è probabile che l'attivazione iniziale fosse falsa. In questo caso, disabilitare l'assistente al debug gestito per evitare interferenze con la sessione di debug.

> [!NOTE]
> Questo assistente al debug gestito si trova nel set predefinito per Visual Studio. Per informazioni su come disabilitare MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).

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

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
