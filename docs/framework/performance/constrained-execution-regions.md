---
title: aree di esecuzione vincolate
ms.date: 03/30/2017
helpviewer_keywords:
- constrained execution regions
- CERs
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
ms.openlocfilehash: 3161f77399030c287649ee5757814963b6afb7cf
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247727"
---
# <a name="constrained-execution-regions"></a>aree di esecuzione vincolate
Le aree a esecuzione vincolata rientrano in un meccanismo per la creazione di codice gestito affidabile. Un'area a esecuzione vincolata è un'area in cui Common Language Runtime (CLR) non può generare eccezioni fuori banda che impedirebbero l'esecuzione completa del codice nell'area. All'interno di tale area il codice non può eseguire codice che comporterebbe la generazione di eccezioni fuori banda. Il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> deve precedere immediatamente un blocco `try` e contrassegna i blocchi `catch`, `finally` e `fault` come aree a esecuzione vincolata. Dopo che è stato contrassegnato come area a esecuzione vincolata, il codice può chiamare solo altro codice con contratto di affidabilità efficace e può allocare o effettuare chiamate virtuali a metodi non preparati o non affidabili solo se è in grado di gestire eventuali errori. Per il codice in esecuzione in un'area a esecuzione vincolata, CLR ritarda le interruzioni di thread.  

> [!IMPORTANT]
> CER è supportato solo in .NET Framework. Questo articolo non si applica a .NET Core o .NET 5 e versioni successive.

 In CLR le aree a esecuzione vincolata vengono usate in diversi moduli, in aggiunta a blocchi `try` annotati, in particolare in finalizzatori critici in esecuzione all'interno di classi derivate dalla classe <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> e in codice eseguito tramite il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>.  
  
## <a name="cer-advance-preparation"></a>Preparazione anticipata delle aree a esecuzione vincolata  
 CLR prepara le aree a esecuzione vincolata in anticipo per evitare condizioni di memoria insufficiente. La preparazione anticipata è necessaria perché CLR non causi un condizione di memoria insufficiente durante la compilazione JIT o il caricamento di tipi.  
  
 Lo sviluppatore deve indicare che un'area di codice è un'area a esecuzione vincolata:  
  
- L'area a esecuzione vincolata e i metodi di livello superiore nel grafico chiamate completo che presentano l'attributo <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> vengono preparati in anticipo. L'attributo <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> può solo dichiarare garanzie <xref:System.Runtime.ConstrainedExecution.Cer.Success> o <xref:System.Runtime.ConstrainedExecution.Cer.MayFail>.  
  
- La preparazione anticipata non può essere eseguita per le chiamate che non è possibile determinare in modo statico, ad esempio le chiamate virtuali. In questi casi usare il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>. Se si usa il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>, deve essere applicato l'attributo <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> al codice di pulizia.  
  
## <a name="constraints"></a>Vincoli  
 Gli utenti subiscono alcuni vincoli per il tipo di codice che possono scrivere in un'area a esecuzione vincolata. Il codice non può causare eccezioni fuori banda quali quelle che potrebbero risultare dalle operazioni seguenti:  
  
- Allocazione esplicita.  
  
- Boxing.  
  
- Acquisizione di un blocco.  
  
- Chiamata virtuale a metodi non preparati.  
  
- Chiamata a metodi con un contratto di affidabilità debole o inesistente.  
  
 In .NET Framework versione 2.0 questi vincoli sono linee guida. La diagnostica viene eseguita tramite strumenti di analisi codice.  
  
## <a name="reliability-contracts"></a>Contratti di affidabilità  
 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> è un attributo personalizzato che documenta le garanzie di affidabilità e lo stato di danneggiamento di un metodo specifico.  
  
### <a name="reliability-guarantees"></a>Garanzie di affidabilità  
 Le garanzie di affidabilità, rappresentate da valori di enumerazione <xref:System.Runtime.ConstrainedExecution.Cer>, indicano il grado di affidabilità di un metodo specifico:  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.MayFail>. In condizioni eccezionali il metodo potrebbe avere esito negativo. In questo caso, il metodo segnala al metodo di chiamata se l'esito è stato positivo o negativo. Perché possa segnalare il valore restituito, il metodo deve trovarsi all'interno di un'area a esecuzione vincolata.  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.None>. Il metodo, il tipo o l'assembly non include alcun concetto di area a esecuzione vincolata. Molto probabilmente non è sicuro chiamarlo all'interno di un'area a esecuzione vincolata senza una mitigazione sostanziale dei rischi di danneggiamento dello stato. Non usufruisce dei vantaggi delle garanzie di un'area a esecuzione vincolata. Questo implica quanto segue:  
  
    1. In condizioni eccezionali il metodo potrebbe avere esito negativo.  
  
    2. Il metodo può segnalare o meno l'esito negativo.  
  
    3. Il metodo non è stato scritto per l'uso di un'area a esecuzione vincolata, lo scenario più probabile.  
  
    4. Se un metodo, un tipo o un assembly non è contrassegnato in modo esplicito come Success, viene identificato in modo implicito come <xref:System.Runtime.ConstrainedExecution.Cer.None>.  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.Success>. In condizioni eccezionali è garantito l'esito positivo del metodo. Per ottenere questo livello di affidabilità è sempre necessario costruire un'area a esecuzione vincolata intorno al metodo chiamato, anche se viene chiamato dall'interno di un'area non a esecuzione vincolata. Un metodo ha esito positivo se esegue le azioni previste, anche se l'esito può essere interpretato come positivo in modo soggettivo. Ad esempio, contrassegnare Count con `ReliabilityContractAttribute(Cer.Success)` implica che se Count viene eseguito in un'area a esecuzione vincolata, restituisce sempre il conteggio del numero di elementi in <xref:System.Collections.ArrayList> e non può mai lasciare i campi interni in uno stato indeterminato.  Anche il metodo <xref:System.Threading.Interlocked.CompareExchange%2A>, tuttavia, è contrassegnato con Success, implicando che può essere considerato esito positivo anche il fatto che il valore non possa essere sostituito con un nuovo valore a causa di una race condition.  Il punto chiave è che il metodo si comporta in modo conforme a quanto documentato e che non è necessario scrivere codice di area a esecuzione vincolata per prevedere un comportamento più inusuale di quello prevedibile per codice corretto ma non affidabile.  
  
### <a name="corruption-levels"></a>Livelli di danneggiamento  
 I livelli di danneggiamento, rappresentati da valori di enumerazione <xref:System.Runtime.ConstrainedExecution.Consistency>, indicano il livello di danneggiamento dello stato in un determinato ambiente:  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>. In condizioni eccezionali, Common Language Runtime (CLR) non garantisce la coerenza dello stato nel dominio dell'applicazione corrente.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance>. In condizioni eccezionali, il metodo garantisce la limitazione del danneggiamento dello stato dell'istanza corrente.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>. In condizioni eccezionali, CLR non garantisce la coerenza dello stato. In altre parole, la condizione potrebbe danneggiare il processo.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState>. In condizioni eccezionali è garantito che il metodo non danneggia lo stato.  
  
## <a name="reliability-trycatchfinally"></a>Blocco Try/catch/finally di affidabilità  
 Il blocco `try/catch/finally` di affidabilità è un meccanismo di gestione delle eccezioni con lo stesso livello di garanzie di prevedibilità della versione non gestita. Il blocco `catch/finally` costituisce l'area a esecuzione vincolata. I metodi nel blocco richiedono la preparazione anticipata e non devono poter essere interrotti.  
  
 In .NET Framework versione 2.0, il codice informa il runtime che un blocco try è affidabile chiamando <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> immediatamente prima di un blocco try. <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>è un membro di <xref:System.Runtime.CompilerServices.RuntimeHelpers>, una classe di supporto del compilatore. Chiamare <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> direttamente durante la sua disponibilità nei compilatori.  
  
## <a name="noninterruptible-regions"></a>Aree non interrompibili  
 Un'area non interrompibile raggruppa un set di istruzioni all'interno di un'area a esecuzione vincolata.  
  
 In .NET Framework versione 2.0, durante la disponibilità tramite il supporto del compilatore, il codice utente crea aree non interrompibili con un'istruzione try/catch/finally affidabile che contiene un blocco try/catch vuoto preceduto da una chiamata al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.  
  
## <a name="critical-finalizer-object"></a>Oggetto finalizzatore critico  
 Un oggetto <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> garantisce che la procedura di Garbage Collection eseguirà il finalizzatore. Al momento dell'allocazione, il finalizzatore e il relativo grafico chiamate vengono preparati in anticipo. Il metodo finalizzatore viene eseguito in un'area a esecuzione vincolata e deve rispettare tutti i vincoli di questo tipo di aree e dei finalizzatori.  
  
 Per tutti i tipi che ereditano da <xref:System.Runtime.InteropServices.SafeHandle> e da <xref:System.Runtime.InteropServices.CriticalHandle> è garantita l'esecuzione dei rispettivi finalizzatori all'interno di un'area a esecuzione vincolata. Implementare <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> in classi derivate da <xref:System.Runtime.InteropServices.SafeHandle> per eseguire il codice necessario per liberare l'handle.  
  
## <a name="code-not-permitted-in-cers"></a>Codice non consentito nelle aree a esecuzione vincolata  
 Nelle aree a esecuzione vincolata non sono consentite le operazioni seguenti:  
  
- Allocazioni esplicite.  
  
- Acquisizione di un blocco.  
  
- Boxing.  
  
- Accesso a matrici multidimensionali.  
  
- Chiamate a metodi tramite reflection.  
  
- <xref:System.Threading.Monitor.Enter%2A> o <xref:System.IO.FileStream.Lock%2A>.  
  
- Controlli di sicurezza. Non eseguire le richieste, limitarsi a collegarle.  
  
- <xref:System.Reflection.Emit.OpCodes.Isinst> e <xref:System.Reflection.Emit.OpCodes.Castclass> per oggetti COM e proxy  
  
- Ottenere o impostare campi in un proxy trasparente.  
  
- Serializzazione.  
  
- Puntatori a funzione e delegati.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per l'ottimizzazione dell'affidabilità](reliability-best-practices.md)
