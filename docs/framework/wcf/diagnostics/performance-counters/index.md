---
title: Contatori delle prestazioni di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: a9bddcbd907e37d9bdf757b1999946c99e10440c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855634"
---
# <a name="wcf-performance-counters"></a>Contatori delle prestazioni di WCF
Windows Communication Foundation (WCF) include un ampio set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione.  
  
## <a name="enabling-performance-counters"></a>Attivazione dei contatori delle prestazioni  
 È possibile abilitare i contatori delle prestazioni per un servizio WCF tramite il file di configurazione app. config del servizio WCF come indicato di seguito:  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 L'attributo `performanceCounters` può essere impostato per attivare un tipo specifico di contatori delle prestazioni. I valori validi sono:  
  
- Tutti Sono abilitati tutti i contatori di categoria (ServiceModelService, ServiceModelEndpoint e ServiceModelOperation).  
  
- ServiceOnly: Sono abilitati solo i contatori di categoria ServiceModelService. Rappresenta il valore predefinito.  
  
- Off I contatori delle prestazioni ServiceModel * sono disabilitati.  
  
 Se si desidera abilitare i contatori delle prestazioni per tutte le applicazioni WCF, è possibile inserire le impostazioni di configurazione nel file Machine. config.  Per ulteriori informazioni sulla configurazione di memoria sufficiente per i contatori delle prestazioni nel computer, vedere la sezione **aumento della dimensione della memoria per i contatori delle prestazioni** .  
  
 Se si usano punti di estendibilità WCF, ad esempio invoker di operazioni personalizzati, è necessario creare anche i propri contatori delle prestazioni. Questo perché se si implementa un punto di estendibilità, WCF potrebbe non emettere più i dati del contatore delle prestazioni standard nel percorso predefinito. Se non si implementa il supporto manuale dei contatori delle prestazioni, è possibile che i dati previsti di questi ultimi non vengano visualizzati.  
  
 È inoltre possibile abilitare contatori delle prestazioni nel codice nel modo seguente:  
  
```csharp
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a>Visualizzazione dei dati relativi alle prestazioni  
 Per visualizzare i dati acquisiti dai contatori delle prestazioni è possibile usare lo strumento Performance Monitor (Perfmon.exe) di Windows. Per avviare questo strumento, passare a **Start**, quindi fare clic su **Esegui** e `perfmon.exe` digitare nella finestra di dialogo.  
  
> [!NOTE]
> Le istanze del contatore delle prestazioni possono essere rilasciate prima che gli ultimi messaggi siano stati elaborati dal Dispatcher dell'endpoint. In questo caso è possibile che i dati relativi alle prestazioni non vengano acquisiti per alcuni messaggi.  
  
## <a name="increasing-memory-size-for-performance-counters"></a>Aumento della dimensione della memoria per i contatori delle prestazioni  
 WCF utilizza una memoria condivisa separata per le categorie dei contatori delle prestazioni.  
  
 Per impostazione predefinita, la memoria condivisa separata è impostata su un quarto della dimensione della memoria globale dei contatori delle prestazioni. La dimensione della memoria globale predefinita dei contatori delle prestazioni è di 524.288 byte. Pertanto, le tre categorie di contatori delle prestazioni WCF hanno una dimensione predefinita di circa 128 KB. A seconda delle caratteristiche di runtime delle applicazioni WCF in un computer, è possibile che la memoria del contatore delle prestazioni sia esaurita. Quando si verifica questo problema, WCF scrive un errore nel registro eventi dell'applicazione. Il contenuto dell'errore indica che un contatore delle prestazioni non è stato caricato e che la voce contiene l'eccezione "System. InvalidOperationException: Memoria insufficiente per la visualizzazione del file dei contatori personalizzati ". Se è attivata l'analisi al livello dell'errore, l'errore viene anche analizzato. Se la memoria del contatore delle prestazioni è esaurita, continuare a eseguire le applicazioni WCF con i contatori delle prestazioni abilitati potrebbe causare un calo delle prestazioni. In questo caso l'amministratore del computer dovrà configurare il computer per l'allocazione di memoria sufficiente a supportare il numero massimo di contatori delle prestazioni che possono essere presenti in qualsiasi momento.  
  
 È possibile modificare la quantità di memoria del contatore delle prestazioni per le categorie WCF nel registro di sistema. A tale scopo, è necessario aggiungere un nuovo valore DWORD denominato `FileMappingSize` ai tre percorsi specificati di seguito e impostarlo sul valore desiderato espresso in byte. Riavviare il computer per rendere effettive le modifiche.  
  
- HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance  
  
- HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance  
  
- HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance  
  
 Quando numerosi oggetti (ad esempio, ServiceHost) vengono eliminati ma rimangono in attesa di essere sottoposti all'operazione di Garbage Collection, il contatore delle prestazioni `PrivateBytes` registra un valore insolitamente elevato. Per risolvere questo problema è possibile aggiungere contatori specifici dell'applicazione o usare l'attributo `performanceCounters` per attivare soltanto i contatori a livello di servizio.  
  
## <a name="types-of-performance-counters"></a>Tipi di contatori delle prestazioni  
 I contatori delle prestazioni hanno come ambito tre livelli diversi: Servizio, endpoint e operazione.  
  
 Per recuperare il nome di un'istanza di contatore delle prestazioni è possibile usare WMI. Ad esempio,  
  
- Il nome dell'istanza del contatore del servizio può essere ottenuto tramite la proprietà "CounterInstanceName" dell'istanza del [servizio](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) WMI.  
  
- Il nome dell'istanza del contatore dell'endpoint può essere ottenuto tramite la proprietà "CounterInstanceName" dell'istanza di [endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) WMI.  
  
- Il nome dell'istanza del contatore delle operazioni può essere ottenuto tramite il metodo "GetOperationCounterInstanceName" dell'istanza dell' [endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) WMI.  
  
 Per ulteriori informazioni su WMI, vedere [utilizzo di Strumentazione gestione Windows per la diagnostica](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
### <a name="service-performance-counters"></a>Contatori delle prestazioni a livello di servizio  
 I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio. Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor. Le istanze vengono denominate usando il modello seguente:  
  
`ServiceName@ServiceBaseAddress`
  
 Un contatore nell'ambito di un servizio viene aggregato dal contatore in una raccolta di endpoint.  
  
 I contatori delle prestazioni per la creazione dell'istanza di servizio vengono incrementati alla creazione di un nuovo contesto InstanceContext. Si noti che un nuovo contesto InstanceContext viene creato anche quando si riceve un messaggio di non attivazione (con un servizio esistente) o quando vi è una connessione a un'istanza da una determinata sessione, si termina la sessione e ci si riconnette da un'altra sessione.  
  
### <a name="endpoint-performance-counters"></a>Contatori delle prestazioni a livello di endpoint  
 I contatori delle prestazioni a livello di endpoint consentono di analizzare i dati che riflettono la modalità di accettazione dei messaggi da parte di un endpoint. Sono reperibili nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` in caso di visualizzazione con Performance Monitor. Le istanze vengono denominate usando il modello seguente:  
  
`(ServiceName).(ContractName)@(endpoint listener address)`
  
 I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.  
  
 Un contatore nell'ambito di un endpoint viene aggregato dai contatori in una raccolta di operazioni.  
  
> [!NOTE]
> Se due endpoint hanno nomi e indirizzi di contratto identici, vengono mappati alla stessa istanza di contatore.  
  
### <a name="operation-performance-counters"></a>Contatori delle prestazioni a livello di operazione  
 I contatori delle prestazioni a livello di operazione sono reperibili nell'oggetto prestazione `ServiceModelOperation 4.0.0.0` in caso di visualizzazione con Performance Monitor. Ogni operazione ha un'istanza singola. Ovvero, se un determinato contratto ha 10 operazioni, ad esso sono associate 10 istanze di contatore per l'operazione. Le istanze di oggetti vengono denominate usando il modello seguente:  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 Questo contatore consente di misurare come viene usata la chiamata e le prestazioni dell'operazione.  
  
 Quando i contatori sono visibili su più ambiti, i dati raccolti da un ambito di livello superiore vengono aggregati ai dati relativi ad ambiti di livello inferiore. Ad esempio, il contatore `Calls` in un endpoint rappresenta la somma di tutte le chiamate a operazioni all'interno dell'endpoint; mentre il contatore `Calls` in un servizio rappresenta la somma di tutte le chiamate a tutti gli endpoint all'interno del servizio.  
  
> [!NOTE]
> Se in un contratto sono presenti nomi di operazione duplicati, per entrambe le operazioni è possibile ottenere soltanto le istanze di un solo contatore.  
  
## <a name="programming-the-wcf-performance-counters"></a>Programmazione dei contatori delle prestazioni di WCF  
 Diversi file vengono installati nella cartella di installazione dell'SDK, in modo che sia possibile accedere ai contatori delle prestazioni WCF a livello di codice. Di seguito è riportato l'elenco di questi file.  
  
- _ServiceModelEndpointPerfCounters.vrg  
  
- _ServiceModelOperationPerfCounters.vrg  
  
- _ServiceModelServicePerfCounters.vrg  
  
- _SMSvcHostPerfCounters.vrg  
  
- _TransactionBridgePerfCounters.vrg  
  
 Per ulteriori informazioni sull'accesso ai contatori a livello di codice, vedere l' [architettura di programmazione dei contatori delle prestazioni](https://go.microsoft.com/fwlink/?LinkId=95179).  
  
## <a name="see-also"></a>Vedere anche

- [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
