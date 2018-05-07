---
title: Tracce di diagnostica
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 56f79fb9140785188996cc413eca4dd530037ccd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="diagnostic-traces"></a>Tracce di diagnostica
Le tracce consistono nella pubblicazione di messaggi specifici generati durante l'esecuzione di un'applicazione. Quando si utilizza la tracciatura è necessario disporre di un meccanismo per raccogliere e registrare i messaggi inviati. I messaggi di traccia vengono ricevuti dai listener. Il compito di un listener è raccogliere, archiviare e inviare messaggi di errore. I listener indirizzano l'output di tracciatura a una destinazione appropriata, ad esempio un file di log, una finestra o un file di testo.  
  
 Quando si abilita la tracciatura, il sistema crea e inizializza automaticamente il listener predefinito <xref:System.Diagnostics.DefaultTraceListener>. Se si desidera indirizzare l'output di traccia a origini aggiuntive, è necessario creare e inizializzare listener di traccia aggiuntivi. I listener devono essere creati in base alle proprie esigenze specifiche. Si supponga ad esempio che sia necessario creare un record di testo contenente tutti gli output di traccia. In questo caso occorre creare un listener che, quando abilitato, scriva tutti gli output in un nuovo file di testo. Un altro esempio possibile è la visualizzazione dell'output durante l'esecuzione dell'applicazione. In questo caso occorre invece creare un listener che indirizza tutti gli output a una finestra della console. Il listener <xref:System.Diagnostics.EventLogTraceListener> è in grado di indirizzare l'output di traccia a un registro eventi, mentre il listener <xref:System.Diagnostics.TextWriterTraceListener> può scrivere l'output di traccia in un flusso.  
  
## <a name="enabling-tracing"></a>Abilitazione della traccia  
 Per abilitare le tracce durante l'elaborazione delle transazioni è necessario modificare il file di configurazione dell'applicazione. Di seguito è riportato un esempio.  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"   
                     type="System.Diagnostics.XmlWriterTraceListener"   
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 Le tracce dello spazio dei nomi <xref:System.Transactions> vengono scritte nell'origine "System.Transactions". È possibile utilizzare l'istruzione `add` per specificare il nome e il tipo del listener di traccia che si desidera utilizzare. Nella configurazione dell'esempio, il listener viene denominato "tx" e come tipo da utilizzare viene aggiunto il listener di traccia standard di .NET Framework, ovvero <xref:System.Diagnostics.XmlWriterTraceListener>. Utilizzare l'istruzione `initializeData` per impostare il nome del file di log del listener. È inoltre possibile sostituire un percorso completo con un semplice nome file.  
  
 A ogni tipo di messaggio di traccia viene assegnato un livello che ne indica il grado di importanza. Se il livello di traccia del dominio applicazione è inferiore o uguale al livello di un tipo di evento, il sistema genera un messaggio relativo a tale evento. Il livello di traccia viene controllato in base all'impostazione `switchValue` del file di configurazione. Nella tabella seguente sono definiti i livelli associati ai messaggi di traccia di diagnostica.  
  
|Livello di traccia|Descrizione|  
|-----------------|-----------------|  
|Critico|Si sono verificati errori gravi. Ad esempio:<br /><br /> -Un errore che può causare una perdita immediata delle funzionalità di utente.<br />-Un evento che richiede un amministratore di intervenire per evitare la perdita di funzionalità.<br />-Blocchi di codice.<br />-Il livello di traccia può anche offrire un contesto sufficiente per l'interpretazione di altre tracce critico. Ciò può semplificare l'identificazione della sequenza di operazioni che ha portato all'errore grave.|  
|Error|Si è verificato un errore (ad esempio, un errore di configurazione o un comportamento di rete non valido) che può comportare la perdita di funzionalità dell'utente.|  
|Avviso|È stata rilevata una condizione che in seguito può dare luogo a un errore standard o critico, ad esempio un errore di allocazione o il raggiungimento di un limite. Gli avvisi possono anche essere generati durante la normale elaborazione degli errori del codice utente, ad esempio l'interruzione di una transazione, lo scadere di un timeout o l'esito negativo di un'autenticazione.|  
|Informazioni|Il sistema genera messaggi informativi che semplificano il monitoraggio e la diagnosi dello stato di sistema, la valutazione delle prestazioni o il profiling. Questi messaggi possono ad esempio riguardare gli eventi durata di transazione e integrazione (quali la creazione o il commit di una transazione), l'attraversamento di un confine importante o l'allocazione di risorse significative. Gli sviluppatori possono quindi utilizzare queste informazioni durante la pianificazione delle capacità e la gestione delle prestazioni.|  
  
## <a name="trace-codes"></a>Codici di traccia  
 Nella tabella seguente sono elencati i codici di traccia generati dall'infrastruttura <xref:System.Transactions>. La tabella include l'identificatore della tabella di traccia, il <xref:System.Diagnostics.EventTypeFilter.EventType%2A> il livello di enumerazione per la traccia e i dati aggiuntivi contenuti nel **TraceRecord** per la traccia. Inoltre, il livello di traccia corrispondente della traccia viene inoltre archiviato nel **TraceRecord**.  
  
|TraceCode|EventType|Dati aggiuntivi in TraceRecord|  
|---------------|---------------|-------------------------------|  
|TransactionCreated|Info|TransactionTraceId|  
|TransactionPromoted|Info|TransactionTraceId della transazione locale, TransactionTraceId della transazione distribuita|  
|EnlistmentCreated|Info|TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions|  
|EnlistmentCallbackNegative|Avviso|TransactionTraceId, EnlistmentTraceId<br /><br /> Callback (forcerollback/aborted/indoubt)|  
|TransactionRollbackCalled|Avviso|TransactionTraceId|  
|TransactionAborted|Avviso|TransactionTraceId|  
|TransactionInDoubt|Avviso|TransactionTraceId|  
|TransactionScopeCreated|Info|TransactionScopeResult. Risultati possibili:<br /><br /> -Nuova transazione.<br />-Transaction è stato passato.<br />-Transazione dipendente passato.<br />-Utilizzo di transazione corrente.<br />-Nessuna transazione.<br /><br /> nuovo TransactionTraceId corrente|  
|TransactionScopeDisposed|Info|TransactionTraceId dell'ambito transazione corrente "previsto".|  
|TransactionScopeIncomplete|Avviso|TransactionTraceId dell'ambito transazione corrente "previsto".|  
|TransactionScopeNestedIncorrectly|Avviso|TransactionTraceId dell'ambito transazione corrente "previsto".|  
|TransactionScopeCurrentTransactionChanged|Avviso|vecchio TransactionTraceId corrente, altro TransactionTraceId|  
|TransactionScopeTimeout|Avviso|TransactionTraceId dell'ambito transazione corrente "previsto".|  
|DependentCloneCreated|Info|TransactionTraceId, tipo di transazione dipendente creata (RollbackIfNotComplete/BlockCommitUntilComplete)|  
|DependentCloneComplete|Info|TransactionTraceId|  
|RecoveryComplete|Info|GUID del gestore di risorse (dalla base)|  
|Reenlist|Info|GUID del gestore di risorse (dalla base)|  
|TransactionSerialized|Info|TransactionTraceId.|  
|TransactionException|Error|Messaggio eccezione|  
|InvalidOperationException|Error|Messaggio eccezione|  
|InternalError|Critico|Messaggio eccezione|  
|TransferEvent||Quando una transazione viene deserializzata o promossa da transazione dello spazio dei nomi <xref:System.Transactions> a transazione distribuita, il sistema scrive l'ActivityID corrente ricavato dal contesto ExecutionContext e l'ID della transazione distribuita.<br /><br /> Quando il gestore DTC esegue il callback al codice gestito, l'ID della transazione distribuita viene impostato per la durata del callback come ActivityID del contesto ExecutionContext.|  
|ConfiguredDefaultTimeoutAdjusted|Avviso|Nessun dato aggiuntivo|  
|TransactionTimeout|Avviso|TransactionTraceId della transazione per cui è scaduto il timeout.|  
  
 L'XML Schema di ognuno degli elementi di dati aggiuntivi precedenti presenta il formato seguente.  
  
### <a name="transactiontraceidentifier"></a>TransactionTraceIdentifier  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a>EnlistmentTraceIdentifier  
 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a>Identificatore del gestore di risorse  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a>Problemi di sicurezza relativi alle tracce  
 Quando un amministratore attivare la traccia, le informazioni riservate potrebbero scrivere un log di traccia che è visibile pubblicamente per impostazione predefinita. Per limitare qualsiasi rischio di protezione, è consigliabile archiviare il log di traccia in una posizione sicura controllata dalle autorizzazioni di accesso di sistema di condivisione e file.
