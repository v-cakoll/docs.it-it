---
title: Estensione della funzionalità di traccia
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c56f886857e8d391a243e3af4a13353f14116247
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329713"
---
# <a name="extending-tracing"></a>Estensione della funzionalità di traccia
In questo esempio viene illustrato come estendere la funzionalità di traccia di Windows Communication Foundation (WCF) scrivendo le tracce di attività definite dall'utente nel codice client e del servizio. In questo modo l'utente può creare attività di traccia e raggruppare le tracce in unità logiche di lavoro. È anche possibile correlare le attività tramite trasferimenti (all'interno dello stesso endpoint) e propagazione (attraverso diversi endpoint). In questo esempio la traccia è abilitata sia per il client che per il servizio. Per altre informazioni su come abilitare la traccia nel file di configurazione client e servizio, vedere [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
 In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a>Traccia e propagazione delle attività  
 Traccia di attività definite dall'utente consente all'utente di creare le proprie attività di traccia per raggruppare le tracce in unità logiche di lavoro, correlare le attività tramite trasferimenti e propagazione e ridurre i costi della traccia di WCF (ad esempio, lo spazio su disco dei costi di un file di log).  
  
### <a name="adding-custom-sources"></a>Aggiunta di origini personalizzate  
 Le tracce definite dall'utente possono essere aggiunte sia al codice del client che al codice del servizio. Aggiunta di origini di traccia ai file di configurazione client o del servizio consentono queste tracce personalizzate essere registrati e visualizzati nei [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Nell'esempio di codice seguente viene illustrato come aggiungere un'origine di traccia definita dall'utente denominata `ServerCalculatorTraceSource` al file di configurazione.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a>Correlazione di attività  
 Per correlare direttamente le attività attraverso gli endpoint, l'attributo `propagateActivity` deve essere impostato su `true` nell'origine di traccia `System.ServiceModel`. Inoltre, per propagare le tracce senza passare attraverso le attività WCF, traccia attività ServiceModel deve essere spenta. Tutto ciò è illustrato nell'esempio di codice seguente.  
  
> [!NOTE]
>  La disattivazione dell'attività di traccia ServiceModel non equivale a disattivare il livello di traccia, indicato dalla proprietà `switchValue`.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a>Riduzione del costo in termini di prestazioni  
 La disattivazione di `ActivityTracing` nell'origine di traccia `System.ServiceModel` genera un file di traccia che contiene solo le tracce di attività definite dall'utente, senza includere le tracce di attività ServiceModel. Di conseguenza, le dimensioni del file di log risulteranno molto più piccole. Tuttavia, la possibilità per correlare le tracce di elaborazione WCF viene persa.  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio](https://go.microsoft.com/fwlink/?LinkId=193959)
