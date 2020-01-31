---
title: Analisi circolare
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 0b1d62177828b52b21a3e43cc083f79c27878804
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741971"
---
# <a name="circular-tracing"></a>Analisi circolare

Questo esempio illustra l'implementazione di un listener traccia circolare del buffer. Un scenario comune per i servizi in un ambiente di produzione è avere servizi disponibili per lunghi periodi e avere la registrazione analisi attivata a un livello basso. Questi servizi utilizzano molto spazio su disco. Durante la risoluzione dei problemi di un servizio, i dati più recenti del registro di traccia sono attinenti alla risoluzione di un problema. Questo esempio illustra l'implementazione di un listener di traccia circolare del buffer in cui solo tracce più recenti vengono tenute su disco fino al raggiungimento di una quantità configurabile di dati. Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e include un listener di traccia personalizzato.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

Questo esempio presuppone che si abbia familiarità con l'esempio di [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) e che sia stata letta la documentazione fornita per l'esempio di [traccia e registrazione dei messaggi](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) .

## <a name="circular-buffer-trace-listener"></a>Listener di traccia circolare del buffer

Il concetto alla base dell'implementazione del Listener di traccia circolare del buffer è avere due file in grado di contenere, singolarmente, la metà dei dati totali che si desidera inserire nel registro di traccia. Il listener crea un file e scrive in quel file fino al raggiungimento della metà dei dati totali, a quel punto passa a scrivere sul secondo file. Quando il listener raggiunge il limite per il secondo file - sovrascrive il primo file con le nuove tracce.

Questo listener deriva dalla `XmlWriteTraceListener` e consente la visualizzazione dei log con lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Quando si desidera visualizzare il log, i due file possono essere facilmente ricombinati aprendoli contemporaneamente nello strumento Service Trace Viewer. Lo strumento Service Trace Viewer si occupa automaticamente di ordinare le tracce, che verranno visualizzate nell'ordine corretto.

## <a name="configuration"></a>Configurazione di

Un servizio può essere configurato per utilizzare il Listener di traccia circolare del buffer aggiungendo il codice seguente per un listener e gli elementi di origine. La dimensione massima del file viene specificata impostando l'attributo `maxFileSizeKB` durante la configurazione listener di traccia circolare, come illustrato nell'esempio di codice riportato di seguito.

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">
      <listeners>
        <add name="CircularTraceListener" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />
  </sharedListeners>
  <trace autoflush="true" />
</system.diagnostics>
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`

## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
