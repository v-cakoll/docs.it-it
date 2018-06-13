---
title: Contatori delle prestazioni di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: 1d9e6b83a78967193c4cb0343f6c77560354a837
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805168"
---
# <a name="wcf-performance-counters"></a>Contatori delle prestazioni di WCF
Windows Communication Foundation (WCF) include un vasto set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione.  
  
## <a name="enabling-performance-counters"></a>Attivazione dei contatori delle prestazioni  
 È possibile abilitare i contatori delle prestazioni per un servizio WCF tramite il file di configurazione App. config del servizio WCF come indicato di seguito:  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 L'attributo `performanceCounters` può essere impostato per attivare un tipo specifico di contatori delle prestazioni. I valori validi sono:  
  
-   All: vengono attivati tutti i contatori della categoria (ServiceModelService, ServiceModelEndpoint e ServiceModelOperation).  
  
-   ServiceOnly: vengono attivati soltanto i contatori della categoria ServiceModelService. Rappresenta il valore predefinito.  
  
-   Off: vengono disattivati i contatori delle prestazioni della categoria ServiceModel*.  
  
 Se si desidera abilitare contatori delle prestazioni per tutte le applicazioni WCF, è possibile inserire le impostazioni di configurazione nel file Machine. config.  Vedere il **l'aumento delle dimensioni della memoria per i contatori delle prestazioni** sezione riportata di seguito per ulteriori informazioni sulla configurazione di memoria sufficiente per i contatori delle prestazioni nel computer.  
  
 Se si usano punti di estendibilità WCF, ad esempio invoker di operazioni personalizzati, è necessario creare anche i contatori delle prestazioni. Infatti, se si implementa un punto di estensibilità, WCF non è più possibile creare i dati del contatore delle prestazioni standard nel percorso predefinito. Se non si implementa il supporto manuale dei contatori delle prestazioni, è possibile che i dati previsti di questi ultimi non vengano visualizzati.  
  
 È inoltre possibile abilitare contatori delle prestazioni nel codice nel modo seguente:  
  
```  
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
 Per visualizzare i dati acquisiti dai contatori delle prestazioni è possibile usare lo strumento Performance Monitor (Perfmon.exe) di Windows. È possibile avviare questo strumento, passare a **avviare**, fare clic su **eseguire** e tipo `perfmon.exe` nella finestra di dialogo.  
  
> [!NOTE]
>  Le istanze del contatore delle prestazioni possono essere rilasciate prima che gli ultimi messaggi siano stati elaborati dal Dispatcher dell'endpoint. In questo caso è possibile che i dati relativi alle prestazioni non vengano acquisiti per alcuni messaggi.  
  
## <a name="increasing-memory-size-for-performance-counters"></a>Aumento della dimensione della memoria per i contatori delle prestazioni  
 WCF utilizza memoria condivisa separata per le categorie di contatori delle prestazioni.  
  
 Per impostazione predefinita, la memoria condivisa separata è impostata su un quarto della dimensione della memoria globale dei contatori delle prestazioni. La dimensione della memoria globale predefinita dei contatori delle prestazioni è di 524.288 byte. Pertanto, le tre categorie di contatori delle prestazioni WCF hanno una dimensione predefinita di circa 128KB ognuna. A seconda delle caratteristiche di runtime delle applicazioni WCF in un computer, potrebbe essere esaurita memoria dei contatori delle prestazioni. In questo caso, WCF scrive un errore nel registro eventi dell'applicazione. Il contenuto dell'errore indica che un contatore delle prestazioni non è stato caricato e la voce contiene l'eccezione "System.InvalidOperationException: Memoria insufficiente per la visualizzazione del file dei contatori personalizzati". Se è attivata l'analisi al livello dell'errore, l'errore viene anche analizzato. Se la memoria dei contatori delle prestazioni è esaurita, continuando a eseguire le applicazioni WCF con i contatori delle prestazioni abilitati può comportare un calo delle prestazioni. In questo caso l'amministratore del computer dovrà configurare il computer per l'allocazione di memoria sufficiente a supportare il numero massimo di contatori delle prestazioni che possono essere presenti in qualsiasi momento.  
  
 È possibile modificare la quantità di memoria dei contatori delle prestazioni per le categorie WCF nel Registro di sistema. A tale scopo, è necessario aggiungere un nuovo valore DWORD denominato `FileMappingSize` ai tre percorsi specificati di seguito e impostarlo sul valore desiderato espresso in byte. Riavviare il computer per rendere effettive le modifiche.  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance  
  
 Quando numerosi oggetti (ad esempio, ServiceHost) vengono eliminati ma rimangono in attesa di essere sottoposti all'operazione di Garbage Collection, il contatore delle prestazioni `PrivateBytes` registra un valore insolitamente elevato. Per risolvere questo problema è possibile aggiungere contatori specifici dell'applicazione o usare l'attributo `performanceCounters` per attivare soltanto i contatori a livello di servizio.  
  
## <a name="types-of-performance-counters"></a>Tipi di contatori delle prestazioni  
 I contatori delle prestazioni vengono applicati a tre livelli differenti: servizio, endpoint e operazione.  
  
 Per recuperare il nome di un'istanza di contatore delle prestazioni è possibile usare WMI. Ad esempio,  
  
-   Nome dell'istanza del contatore servizio può essere ottenuto tramite WMI [servizio](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) proprietà "CounterInstanceName" dell'istanza.  
  
-   Nome dell'istanza del contatore endpoint può essere ottenuto tramite WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) proprietà "CounterInstanceName" dell'istanza.  
  
-   Nome dell'istanza del contatore operazione può essere ottenuto tramite WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) metodo "GetOperationCounterInstanceName" dell'istanza.  
  
 Per ulteriori informazioni su WMI, vedere [tramite Strumentazione gestione Windows per la diagnostica](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
### <a name="service-performance-counters"></a>Contatori delle prestazioni a livello di servizio  
 I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio. Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor. Le istanze vengono denominate usando il modello seguente:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 Un contatore nell'ambito di un servizio viene aggregato dal contatore in una raccolta di endpoint.  
  
 I contatori delle prestazioni per la creazione dell'istanza di servizio vengono incrementati alla creazione di un nuovo contesto InstanceContext. Si noti che un nuovo contesto InstanceContext viene creato anche quando si riceve un messaggio di non attivazione (con un servizio esistente) o quando vi è una connessione a un'istanza da una determinata sessione, si termina la sessione e ci si riconnette da un'altra sessione.  
  
### <a name="endpoint-performance-counters"></a>Contatori delle prestazioni a livello di endpoint  
 I contatori delle prestazioni a livello di endpoint consentono di analizzare i dati che riflettono la modalità di accettazione dei messaggi da parte di un endpoint. Sono reperibili nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` in caso di visualizzazione con Performance Monitor. Le istanze vengono denominate usando il modello seguente:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.  
  
 Un contatore nell'ambito di un endpoint viene aggregato dai contatori in una raccolta di operazioni.  
  
> [!NOTE]
>  Se due endpoint hanno nomi e indirizzi di contratto identici, vengono mappati alla stessa istanza di contatore.  
  
### <a name="operation-performance-counters"></a>Contatori delle prestazioni a livello di operazione  
 I contatori delle prestazioni a livello di operazione sono reperibili nell'oggetto prestazione `ServiceModelOperation 4.0.0.0` in caso di visualizzazione con Performance Monitor. Ogni operazione ha un'istanza singola. Ovvero, se un determinato contratto ha 10 operazioni, ad esso sono associate 10 istanze di contatore per l'operazione. Le istanze di oggetti vengono denominate usando il modello seguente:  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 Questo contatore consente di misurare come viene usata la chiamata e le prestazioni dell'operazione.  
  
 Quando i contatori sono visibili su più ambiti, i dati raccolti da un ambito di livello superiore vengono aggregati ai dati relativi ad ambiti di livello inferiore. Ad esempio, il contatore `Calls` in un endpoint rappresenta la somma di tutte le chiamate a operazioni all'interno dell'endpoint; mentre il contatore `Calls` in un servizio rappresenta la somma di tutte le chiamate a tutti gli endpoint all'interno del servizio.  
  
> [!NOTE]
>  Se in un contratto sono presenti nomi di operazione duplicati, per entrambe le operazioni è possibile ottenere soltanto le istanze di un solo contatore.  
  
## <a name="programming-the-wcf-performance-counters"></a>Programmazione dei contatori delle prestazioni di WCF  
 Diversi file vengono installati nella cartella di installazione del SDK in modo da poter accedere a livello di programmazione i contatori delle prestazioni di WCF. Di seguito è riportato l'elenco di questi file.  
  
-   _ServiceModelEndpointPerfCounters.vrg  
  
-   _ServiceModelOperationPerfCounters.vrg  
  
-   _ServiceModelServicePerfCounters.vrg  
  
-   _SMSvcHostPerfCounters.vrg  
  
-   _TransactionBridgePerfCounters.vrg  
  
 Per ulteriori informazioni sull'accesso ai contatori a livello di codice, vedere [architettura di programmazione del contatore delle prestazioni](http://go.microsoft.com/fwlink/?LinkId=95179).  
  
## <a name="see-also"></a>Vedere anche  
 [Amministrazione e diagnostica](../../../../../docs/framework/wcf/diagnostics/index.md)
