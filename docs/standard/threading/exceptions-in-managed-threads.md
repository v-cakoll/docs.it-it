---
title: Eccezioni in thread gestiti
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET Framework],unhandled exceptions
- threading [.NET Framework],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: 6c14c60b30f8f70aa5e888ed45d6f867154e18d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159650"
---
# <a name="exceptions-in-managed-threads"></a>Eccezioni in thread gestiti
A partire da .NET Framework versione 2.0, Common Language Runtime consente alla maggior parte delle eccezioni non gestite nei thread di proseguire normalmente. Nella maggior parte dei casi questo significa che l'eccezione non gestita provoca l'interruzione dell'applicazione.  
  
> [!NOTE]
> Si tratta di una cambiamento significativo rispetto alle versioni 1.0 e 1.1 di .NET Framework, che forniscono una barriera per numerose eccezioni non gestite, ad esempio, eccezioni non gestite nel pool di thread. Vedere [Cambiamenti rispetto alle versioni precedenti](#ChangeFromPreviousVersions) più avanti in questo argomento.  
  
 Common Language Runtime fornisce una barriera per determinate eccezioni non gestite usate per controllare il flusso del programma:  
  
- Viene generata un'eccezione <xref:System.Threading.ThreadAbortException> in un thread perché è stato chiamato il metodo <xref:System.Threading.Thread.Abort%2A>.  
  
- Viene generata un'eccezione <xref:System.AppDomainUnloadedException> in un thread perché è in corso lo scaricamento del dominio dell'applicazione in cui è in esecuzione il thread.  
  
- Common Language Runtime o un processo host termina il thread generando un'eccezione interna.  
  
 Se una qualsiasi di queste eccezioni viene gestita nei thread creati da Common Language Runtime, l'eccezione termina il thread, ma Common Language Runtime non consente all'eccezione di proseguire.  
  
 Se queste eccezioni vengono gestite nel thread principale o in thread immessi nel runtime dal codice non gestito, esse proseguono normalmente con una conseguente chiusura dell'applicazione.  
  
> [!NOTE]
> È possibile che il runtime generi un'eccezione non gestita prima che qualsiasi codice gestito abbia avuto la possibilità di installare un gestore di eccezioni. Anche se il codice gestito non può gestire tale eccezione, all'eccezione è consentito proseguire normalmente.  
  
## <a name="exposing-threading-problems-during-development"></a>Esposizione di problemi di threading durante lo sviluppo  
 Quando nei thread si verifica un errore in modo silenzioso ma l'applicazione non viene terminata, è possibile che vengano rilevati gravi problemi di programmazione. Si tratta di un problema specifico dei servizi e delle altre applicazioni eseguite per periodi prolungati. In caso di errore dei thread, il programma viene gradualmente danneggiato. L'errore può influire negativamente sulle prestazioni dell'applicazione o l'applicazione potrebbe bloccarsi.  
  
 Consentire alle eccezioni non gestite nei thread di proseguire normalmente finché il sistema operativo non termina il programma permette di esporre tali problemi durante le fasi di sviluppo e test. I report di errore relativi alle chiusure dei programmi supportano il debug.  
  
<a name="ChangeFromPreviousVersions"></a>
## <a name="change-from-previous-versions"></a>Cambiamenti dalle versioni precedenti  
 Il cambiamento più significativo riguarda i thread gestiti. In .NET Framework versioni 1.0 e 1.1, Common Language Runtime fornisce una barriera per le eccezioni non gestite nelle situazioni seguenti:  
  
- Non esiste alcun equivalente di un'eccezione non gestita in un pool di thread. Quando un'attività genera un'eccezione non gestibile, il runtime consente di stampare la traccia dello stack eccezione nella console e quindi restituisce il thread al pool di thread.  
  
- Non esiste alcun equivalente di un'eccezione non gestita in un thread creato con il metodo <xref:System.Threading.Thread.Start%2A> della classe <xref:System.Threading.Thread>. Quando un codice in esecuzione su un thread simile genera un'eccezione non gestibile, il runtime consente di stampare la traccia dello stack eccezione nella console e quindi termina normalmente il thread.  
  
- Non esiste alcun equivalente di un'eccezione non gestita nel thread finalizzatore. Se un finalizzatore genera un'eccezione non gestibile, il runtime consente di stampare la traccia dello stack eccezione nella console e consente quindi al thread finalizzatore di riprendere l'esecuzione dei finalizzatori.  
  
 Lo stato in primo piano o in background di un thread gestito non influisce su tale comportamento.  
  
 Per le eccezioni non gestite nei thread di origine nel codice non gestito, la differenza è più complessa. La finestra di dialogo dell'associazione JIT del runtime ha la precedenza sulla finestra di dialogo del sistema operativo per le eccezioni gestite o native nei thread passati attraverso il codice nativo. Il processo viene terminato in tutti i casi.  
  
### <a name="migrating-code"></a>Migrazione del codice  
 In generale, il cambiamento metterà in evidenza i problemi di programmazione in precedenza non riconosciuti in modo che possano essere risolti. In alcuni casi, tuttavia, i programmatori potrebbero aver sfruttato la barriera di runtime, ad esempio per interrompere i thread. A seconda della situazione, è necessario considerare una delle seguenti strategie di migrazione:  
  
- Ristrutturare il codice in modo che il thread venga chiuso normalmente quando viene ricevuto un segnale.  
  
- Usare il metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> per interrompere il thread.  
  
- Se un thread deve essere arrestato in modo che la terminazione del processo possa continuare, spostare il thread in background in modo che venga terminato automaticamente all'uscita dal processo.  
  
 In tutti i casi, la strategia deve rispettare le linee guida di progettazione per le eccezioni. Vedere [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md).  
  
### <a name="application-compatibility-flag"></a>Contrassegno della compatibilità delle applicazioni  
 Come misura di compatibilità temporanea, gli amministratori possono inserire un contrassegno di compatibilità nella sezione `<runtime>` del file di configurazione dell'applicazione. In questo modo Common Language Runtime può ripristinare il comportamento delle versioni 1.0 e 1.1.  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a>Override dell'host  
 In .NET Framework versione 2.0 un host non gestito può sfruttare l'interfaccia [ICLRPolicyManager](../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) nell'API di hosting per eseguire l'override del criterio predefinito dell'eccezione non gestita di Common Language Runtime. La funzione [ICLRPolicyManager:: SetUnhandledExceptionPolicy](../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) viene usata per impostare il criterio per le eccezioni non gestite.  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni di base sul threading gestito](../../../docs/standard/threading/managed-threading-basics.md)
