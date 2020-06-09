---
title: Diagnostica di applicazioni transazionali
ms.date: 03/30/2017
ms.assetid: 4a993492-1088-4d10-871b-0c09916af05f
ms.openlocfilehash: fb3a83083e876cf697621ba70dcf7dd67636f83a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599217"
---
# <a name="diagnosing-transactional-applications"></a>Diagnostica di applicazioni transazionali
In questo argomento viene descritto come utilizzare la funzionalità di gestione e diagnostica Windows Communication Foundation (WCF) per risolvere i problemi relativi a un'applicazione transazionale.  
  
## <a name="performance-counters"></a>Contatori delle prestazioni  
 WCF fornisce un set standard di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione transazionale. Per altre informazioni, vedere [i contatori delle prestazioni](../diagnostics/performance-counters/index.md).  
  
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
  
## <a name="windows-management-instrumentation"></a>Strumentazione gestione Windows (WMI)  
 WCF espone i dati di ispezione di un servizio in fase di esecuzione tramite un provider WCF Strumentazione gestione Windows (WMI). Per ulteriori informazioni sull'accesso ai dati WMI, vedere [utilizzo di Strumentazione gestione Windows per la diagnostica](../diagnostics/wmi/index.md).  
  
 Un numero di proprietà WMI in sola lettura indica le impostazioni della transazione applicate per un servizio. Nella tabelle seguenti vengono elencate tutte queste impostazioni.  
  
 In un servizio, `ServiceBehaviorAttribute` dispone delle proprietà seguenti.  
  
|Nome|Type|Descrizione|  
|----------|----------|-----------------|  
|ReleaseServiceInstanceOnTransactionComplete|Boolean|Specifica se l'oggetto servizio viene riciclato al completamento della transazione corrente.|  
|TransactionAutoCompleteOnSessionClose|Boolean|Specifica se alla chiusura della sessione corrente vengono completate le transazioni in sospeso.|  
|TransactionIsolationLevel|Stringa che contiene un valore valido dell'enumerazione <xref:System.Transactions.IsolationLevel>.|Specifica il livello di isolamento della transazione supportato dal servizio.|  
|TransactionTimeout|<xref:System.DateTime>|Specifica il periodo di tempo entro il quale deve essere completata una transazione.|  
  
 `ServiceTimeoutsBehavior` dispone della proprietà seguente.  
  
|Nome|Type|Descrizione|  
|----------|----------|-----------------|  
|TransactionTimeout|<xref:System.DateTime>|Specifica il periodo di tempo entro il quale deve essere completata una transazione.|  
  
 In un'associazione, `TransactionFlowBindingElement` dispone delle proprietà seguenti.  
  
|Nome|Type|Descrizione|  
|----------|----------|-----------------|  
|TransactionProtocol|Stringa che contiene un valore valido del tipo <xref:System.ServiceModel.TransactionProtocol>.|Specifica il protocollo di transazione da utilizzare per la propagazione di una transazione.|  
|TransactionFlow|Boolean|Specifica se è attivato il flusso delle transazioni in ingresso.|  
  
 In un'operazione, `OperationBehaviorAttribute` dispone delle proprietà seguenti:  
  
|Nome|Type|Descrizione|  
|----------|----------|-----------------|  
|TransactionAutoComplete|Boolean|Specifica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.|  
|TransactionScopeRequired|Boolean|Specifica se l'operazione richiede una transazione.|  
  
 In un'operazione, `TransactionFlowAttribute` dispone delle proprietà seguenti.  
  
|Nome|Type|Descrizione|  
|----------|----------|-----------------|  
|TransactionFlowOption|Stringa che contiene un valore valido dell'enumerazione <xref:System.ServiceModel.TransactionFlowOption>.|Specifica in che misura è richiesto il flusso delle transazioni.|  
  
## <a name="tracing"></a>Traccia  
 Le tracce consentono di controllare e analizzare errori nelle applicazioni transazionali. È possibile attivare la traccia nei modi seguenti:  
  
- Traccia WCF standard  
  
     Questo tipo di traccia equivale alla traccia di qualsiasi applicazione WCF. Per altre informazioni, vedere [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md).  
  
- Traccia WS-AtomicTransaction  
  
     È possibile abilitare la traccia WS-AtomicTransaction tramite l' [utilità di configurazione WS-AtomicTransaction (wsatConfig. exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md). Tale traccia consente di comprendere lo stato delle transazioni e di conoscere i partecipanti all'interno di un sistema. Per attivare anche la traccia del modello di servizi interna, è possibile impostare la chiave del Registro di sistema `HKLM\SOFTWARE\Microsoft\WSAT\3.0\ServiceModelDiagnosticTracing` su un valore valido dell'enumerazione <xref:System.Diagnostics.SourceLevels>. È possibile abilitare la registrazione dei messaggi in modo analogo alle altre applicazioni WCF.  
  
- Traccia `System.Transactions`  
  
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
  
     In questo modo viene abilitata anche la traccia WCF, perché WCF utilizza anche l' <xref:System.Transactions> infrastruttura.  
  
## <a name="see-also"></a>Vedere anche

- [Amministrazione e diagnostica](../diagnostics/index.md)
- [Configurazione delle funzionalità di traccia](../diagnostics/tracing/configuring-tracing.md)
- [Utilità di configurazione WS-AtomicTransaction (wsatConfig.exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
