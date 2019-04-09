---
title: Diagnostica di applicazioni transazionali
ms.date: 03/30/2017
ms.assetid: 4a993492-1088-4d10-871b-0c09916af05f
ms.openlocfilehash: aca5f95e2085dfadf06da35dfd86af72c0b6092d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101712"
---
# <a name="diagnosing-transactional-applications"></a>Diagnostica di applicazioni transazionali
Questo argomento descrive come usare la gestione di Windows Communication Foundation (WCF) e la funzionalità di diagnostica per risolvere i problemi di un'applicazione transazionale.  
  
## <a name="performance-counters"></a>Contatori delle prestazioni  
 WCF fornisce un set standard di contatori delle prestazioni per misurare le prestazioni dell'applicazione transazionale. Per altre informazioni, vedere [Contatori delle prestazioni](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md).  
  
 I contatori delle prestazioni vengono definiti a tre diversi livelli: servizio, endpoint e operazione come descritto nelle tabelle seguenti.  
  
### <a name="service-performance-counters"></a>Contatori delle prestazioni del servizio  
  
|Contatore delle prestazioni|Descrizione|  
|-------------------------|-----------------|  
|Transazioni propagate|Numero di transazioni propagate alle operazioni in questo servizio. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato al servizio.|  
|Transazioni propagate al secondo|Numero di transazioni propagate alle operazioni in questo servizio ogni secondo. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato al servizio.|  
|Operazioni transazionali con commit eseguito|Numero di operazioni transazionali eseguite la cui transazione è stata completata e di cui è stato eseguito il commit del risultato nel servizio. Per le attività completate nell'ambito di tali operazioni viene eseguito il commit completo. Le risorse vengono aggiornate in base alle attività completate nell'operazione.|  
|Operazioni transazionali con commit eseguito al secondo|Numero di operazioni transazionali eseguite la cui transazione è stata completata e di cui è stato eseguito il commit del risultato nel servizio ogni secondo. Per le attività completate nell'ambito di tali operazioni viene eseguito il commit completo. Le risorse vengono aggiornate in base alle attività completate nell'operazione.|  
|Operazioni transazionali interrotte|Numero di operazioni transazionali eseguite la cui transazione è stata completata con il risultato annullato nel servizio. Per le attività completate nell'ambito di tali operazioni viene eseguito il rollback. Viene ripristinato lo stato precedente delle risorse.|  
|Operazioni transazionali interrotte ogni secondo|Numero di operazioni transazionali eseguite la cui transazione è stata completata con il risultato annullato nel servizio ogni secondo. Per le attività completate nell'ambito di tali operazioni viene eseguito il rollback. Viene ripristinato lo stato precedente delle risorse.|  
|Operazioni transazionali incerte|Numero di operazioni transazionali eseguite la cui transazione è stata completata con un risultato in dubbio nel servizio. Le attività completate con un risultato in dubbio sono in stato indeterminato. Le risorse vengono mantenute con risultato in sospeso.|  
|Operazioni transazionali in dubbio al secondo|Numero di operazioni transazionali eseguite la cui transazione è stata completata con un risultato in dubbio nel servizio ogni secondo. Le attività completate con un risultato in dubbio sono in stato indeterminato. Le risorse vengono mantenute con risultato in sospeso.|  
  
### <a name="endpoint-performance-counters"></a>Contatori delle prestazioni dell'endpoint  
  
|Contatore delle prestazioni|Descrizione|  
|-------------------------|-----------------|  
|Transazioni propagate|Numero di transazioni propagate alle operazioni in questo endpoint. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato all'endpoint.|  
|Transazioni propagate al secondo|Numero di transazioni propagate alle operazioni in questo endpoint ogni secondo. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato all'endpoint.|  
  
### <a name="operation-performance-counters"></a>Contatori delle prestazioni per l'operazione  
  
|Contatore delle prestazioni|Descrizione|  
|-------------------------|-----------------|  
|Transazioni propagate|Numero di transazioni propagate alle operazioni in questo endpoint. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato all'endpoint.|  
|Transazioni propagate al secondo|Numero di transazioni propagate alle operazioni in questo endpoint ogni secondo. Questo contatore viene incrementato ogni volta che è presente una transazione nel messaggio inviato all'endpoint.|  
  
## <a name="windows-management-instrumentation"></a>Strumentazione gestione Windows  
 WCF espone dati di ispezione di un servizio in fase di esecuzione tramite un provider di Strumentazione gestione Windows (WMI) di WCF. Per altre informazioni sull'accesso ai dati WMI, vedere [uso di Strumentazione gestione Windows per la diagnostica](../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
 Un numero di proprietà WMI in sola lettura indica le impostazioni della transazione applicate per un servizio. Nella tabelle seguenti vengono elencate tutte queste impostazioni.  
  
 In un servizio, `ServiceBehaviorAttribute` dispone delle proprietà seguenti.  
  
|Nome|Tipo|Descrizione|  
|----------|----------|-----------------|  
|ReleaseServiceInstanceOnTransactionComplete|Booleano|Specifica se l'oggetto servizio viene riciclato al completamento della transazione corrente.|  
|TransactionAutoCompleteOnSessionClose|Booleano|Specifica se alla chiusura della sessione corrente vengono completate le transazioni in sospeso.|  
|TransactionIsolationLevel|Stringa che contiene un valore valido dell'enumerazione <xref:System.Transactions.IsolationLevel>.|Specifica il livello di isolamento della transazione supportato dal servizio.|  
|TransactionTimeout|<xref:System.DateTime>|Specifica il periodo di tempo entro il quale deve essere completata una transazione.|  
  
 `ServiceTimeoutsBehavior` dispone della proprietà seguente.  
  
|Nome|Tipo|Descrizione|  
|----------|----------|-----------------|  
|TransactionTimeout|<xref:System.DateTime>|Specifica il periodo di tempo entro il quale deve essere completata una transazione.|  
  
 In un'associazione, `TransactionFlowBindingElement` dispone delle proprietà seguenti.  
  
|Nome|Tipo|Descrizione|  
|----------|----------|-----------------|  
|TransactionProtocol|Stringa che contiene un valore valido del tipo <xref:System.ServiceModel.TransactionProtocol>.|Specifica il protocollo di transazione da utilizzare per la propagazione di una transazione.|  
|TransactionFlow|Booleano|Specifica se è attivato il flusso delle transazioni in ingresso.|  
  
 In un'operazione, `OperationBehaviorAttribute` dispone delle proprietà seguenti:  
  
|Nome|Tipo|Descrizione|  
|----------|----------|-----------------|  
|TransactionAutoComplete|Booleano|Specifica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.|  
|TransactionScopeRequired|Booleano|Specifica se l'operazione richiede una transazione.|  
  
 In un'operazione, `TransactionFlowAttribute` dispone delle proprietà seguenti.  
  
|Nome|Tipo|Descrizione|  
|----------|----------|-----------------|  
|TransactionFlowOption|Stringa che contiene un valore valido dell'enumerazione <xref:System.ServiceModel.TransactionFlowOption>.|Specifica in che misura è richiesto il flusso delle transazioni.|  
  
## <a name="tracing"></a>Traccia  
 Le tracce consentono di controllare e analizzare errori nelle applicazioni transazionali. È possibile attivare la traccia nei modi seguenti:  
  
-   Traccia di WCF standard  
  
     Questo tipo di traccia è equivalente alla traccia di tutte le applicazioni WCF. Per altre informazioni, vedere [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Traccia WS-AtomicTransaction  
  
     Analisi WS-AtomicTransaction può essere abilitata utilizzando la [utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md). Tale traccia consente di comprendere lo stato delle transazioni e di conoscere i partecipanti all'interno di un sistema. Per attivare anche la traccia del modello di servizi interna, è possibile impostare la chiave del Registro di sistema `HKLM\SOFTWARE\Microsoft\WSAT\3.0\ServiceModelDiagnosticTracing` su un valore valido dell'enumerazione <xref:System.Diagnostics.SourceLevels>. È possibile abilitare la registrazione nello stesso modo delle altre applicazioni WCF dei messaggi.  
  
-   `System.Transactions` traccia  
  
     Quando si utilizza il protocollo OleTransactions, i messaggi di protocollo non possono essere tracciati. Il supporto di traccia fornito dall'infrastruttura <xref:System.Transactions>, che utilizza OleTransactions, consente agli utenti di visualizzare gli eventi che si sono verificati nelle transazioni. Per attivare la traccia per un'applicazione <xref:System.Transactions>, includere il codice seguente nel file di configurazione `App.config`.  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
         <sources>  
            <source name="System.Transactions" switchValue="Verbose, ActivityTracing">  
               <listeners>  
                  <add name="Text"  
                     type="System.Diagnostics.XmlWriterTraceListener"  
                     initializeData="SysTx.log"  
                     traceOutputOptions="Callstack" />  
               </listeners>  
            </source>  
         </sources>  
         <trace autoflush="true" indentsize="4">  
         </trace>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     Consente anche la tracciatura WCF, come WCF Usa anche il <xref:System.Transactions> dell'infrastruttura.  
  
## <a name="see-also"></a>Vedere anche

- [Amministrazione e diagnostica](../../../../docs/framework/wcf/diagnostics/index.md)
- [Configurazione delle funzionalità di traccia](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
