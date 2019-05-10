---
title: Amministrazione e diagnostica
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
ms.openlocfilehash: 5df95c6b5f91cd4f36bd03c1bd291f7a44025ee9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64600079"
---
# <a name="administration-and-diagnostics"></a>Amministrazione e diagnostica
Windows Communication Foundation (WCF) offre un'ampia gamma di funzionalità che consentono di monitorare le varie fasi del ciclo di vita di un'applicazione. È ad esempio possibile utilizzare la configurazione per impostare servizi e client in fase di distribuzione. WCF include un vasto set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione. WCF espone inoltre dati di ispezione di un servizio in fase di esecuzione tramite un provider di Strumentazione gestione Windows (WMI) di WCF. In caso di errore dell'applicazione o di comportamento non corretto, è possibile utilizzare il Registro eventi per controllare se si è verificato qualcosa di grave. È inoltre possibile utilizzare la registrazione messaggi e le tracce per controllare gli eventi end-to-end in corso nell'applicazione. Queste funzionalità aiutano gli sviluppatori e professionisti IT a risolvere i problemi di un'applicazione WCF quando non funzioni correttamente.  
  
> [!NOTE]
>  Se si ricevono errori senza informazioni dettagliate specifiche, è necessario abilitare la `includeExceptionDetailInFaults` attributo del [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) elemento di configurazione. Ciò indica a WCF di inviare i dettagli dell'eccezione ai client, che consente di rilevare molti problemi comuni senza richiedere diagnosi più avanzate. Per altre informazioni, vedere [Sending and Receiving Faults](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Funzionalità di diagnostica fornite da WCF  
 WCF fornisce le funzionalità di diagnostica seguenti:  
  
- Le tracce end-to-end forniscono dati di strumentazione per risolvere i problemi di un'applicazione senza utilizzare un debugger. WCF genera tracce per le attività cardine di processo, nonché i messaggi di errore. Tale processo può comprendere l'apertura di una channel factory o l'invio e ricezione di messaggi tramite un host del servizio. È possibile attivare la traccia per monitorare lo stato di avanzamento di un'applicazione in esecuzione. Per altre informazioni, vedere la [traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md) argomento. Per comprendere il modo in cui è possibile utilizzare traccia per il debug dell'applicazione, vedere la [tramite la traccia per risolvere i problemi dell'applicazione](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) argomento.  
  
- La registrazione dei messaggi consente di vedere il loro aspetto prima e dopo la trasmissione. Per altre informazioni, vedere la [registrazione messaggi](../../../../docs/framework/wcf/diagnostics/message-logging.md) argomento.  
  
- La traccia eventi scrive gli eventi nel Registro eventi per qualsiasi problema importante. È quindi possibile utilizzare il Visualizzatore eventi per esaminare eventuali anomalie. Per altre informazioni, vedere la [registrazione eventi](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) argomento.  
  
- I contatori delle prestazioni esposti tramite Performance Monitor consentono di monitorare lo stato d'integrità dell'applicazione e del sistema. Per altre informazioni, vedere la [contatori delle prestazioni](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) argomento.  
  
- Lo spazio dei nomi <xref:System.ServiceModel.Configuration> consente di caricare file di configurazione e configurare un endpoint del servizio o client. È possibile utilizzare il modello a oggetti per inserire in uno script le modifiche a numerose applicazioni quando è necessario distribuire gli aggiornamenti a più computer. In alternativa, è possibile usare la [dello strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per modificare le impostazioni di configurazione tramite una procedura guidata GUI. Per altre informazioni, vedere la [configurazione dell'applicazione](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) argomento.  
  
- Con WMI è possibile scoprire quali servizi sono in attesa in un computer e le associazioni utilizzate. Per altre informazioni, vedere la [uso di Strumentazione gestione Windows per la diagnostica](../../../../docs/framework/wcf/diagnostics/wmi/index.md) argomento.  
  
 WCF fornisce inoltre numerosi strumenti dell'interfaccia utente e della riga di comando che rendono più semplice per poter creare, distribuire e gestire le applicazioni WCF. Per altre informazioni, vedere [strumenti di Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Ad esempio, è possibile usare la [dello strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare le impostazioni di configurazione di WCF tramite una procedura guidata, anziché modificare direttamente il codice XML. È anche possibile usare la [strumento Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare, raggruppare e filtrare i messaggi di traccia in modo da poter diagnosticare, riparare e verificare i problemi dei servizi WCF.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dell'applicazione](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
- [Distribuzione di servizi](../../../../docs/framework/wcf/diagnostics/deploying-services.md)
- [Riferimenti per le eccezioni](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)
- [Registrazione eventi](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [Registrazione messaggi](../../../../docs/framework/wcf/diagnostics/message-logging.md)
- [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
- [Strumento di registrazione ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)
- [Traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Uso di Strumentazione gestione Windows per la diagnostica](../../../../docs/framework/wcf/diagnostics/wmi/index.md)
- [Contatori delle prestazioni](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
- [Strumenti Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
