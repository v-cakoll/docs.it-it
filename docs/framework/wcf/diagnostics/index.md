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
ms.openlocfilehash: dfe169cd6c8d9a643e90e98fc9f22bf116d4335f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795983"
---
# <a name="administration-and-diagnostics"></a>Amministrazione e diagnostica
Windows Communication Foundation (WCF) fornisce un set completo di funzionalità che consentono di monitorare le diverse fasi della vita di un'applicazione. È ad esempio possibile utilizzare la configurazione per impostare servizi e client in fase di distribuzione. WCF include un ampio set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione. WCF espone inoltre i dati di ispezione di un servizio in fase di esecuzione tramite un provider WCF Strumentazione gestione Windows (WMI). In caso di errore dell'applicazione o di comportamento non corretto, è possibile utilizzare il Registro eventi per controllare se si è verificato qualcosa di grave. È inoltre possibile utilizzare la registrazione messaggi e le tracce per controllare gli eventi end-to-end in corso nell'applicazione. Queste funzionalità consentono agli sviluppatori e ai professionisti IT di risolvere i problemi relativi a un'applicazione WCF in caso di mancata correttezza.  
  
> [!NOTE]
> Se si ricevono errori senza informazioni dettagliate specifiche, è necessario abilitare l' `includeExceptionDetailInFaults` attributo [ \<](../../configure-apps/file-schema/wcf/servicedebug.md) dell'elemento di configurazione serviceDebug >. In questo modo si indica a WCF di inviare dettagli sulle eccezioni ai client, consentendo di rilevare molti problemi comuni senza richiedere una diagnosi più avanzata. Per ulteriori informazioni, vedere [invio e ricezione di errori](../sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Funzionalità di diagnostica fornite da WCF  
 WCF fornisce le funzionalità di diagnostica seguenti:  
  
- Le tracce end-to-end forniscono dati di strumentazione per risolvere i problemi di un'applicazione senza utilizzare un debugger. WCF restituisce le tracce per le attività cardine del processo, nonché i messaggi di errore. Tale processo può comprendere l'apertura di una channel factory o l'invio e ricezione di messaggi tramite un host del servizio. È possibile attivare la traccia per monitorare lo stato di avanzamento di un'applicazione in esecuzione. Per ulteriori informazioni, vedere l'argomento relativo alla [traccia](./tracing/index.md) . Per comprendere come è possibile usare la traccia per eseguire il debug dell'applicazione, vedere l'argomento [uso della traccia per risolvere i problemi dell'applicazione](./tracing/using-tracing-to-troubleshoot-your-application.md) .  
  
- La registrazione dei messaggi consente di vedere il loro aspetto prima e dopo la trasmissione. Per ulteriori informazioni, vedere l'argomento relativo alla [registrazione dei messaggi](message-logging.md) .  
  
- La traccia eventi scrive gli eventi nel Registro eventi per qualsiasi problema importante. È quindi possibile utilizzare il Visualizzatore eventi per esaminare eventuali anomalie. Per ulteriori informazioni, vedere l'argomento [registrazione degli eventi](./event-logging/index.md) .  
  
- I contatori delle prestazioni esposti tramite Performance Monitor consentono di monitorare lo stato d'integrità dell'applicazione e del sistema. Per ulteriori informazioni, vedere l'argomento [contatori delle prestazioni](./performance-counters/index.md) .  
  
- Lo spazio dei nomi <xref:System.ServiceModel.Configuration> consente di caricare file di configurazione e configurare un endpoint del servizio o client. È possibile utilizzare il modello a oggetti per inserire in uno script le modifiche a numerose applicazioni quando è necessario distribuire gli aggiornamenti a più computer. In alternativa, è possibile utilizzare lo [strumento Editor di configurazione (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) per modificare le impostazioni di configurazione utilizzando una procedura guidata GUI. Per ulteriori informazioni, vedere l'argomento relativo alla [configurazione dell'applicazione](configuring-your-application.md) .  
  
- Con WMI è possibile scoprire quali servizi sono in attesa in un computer e le associazioni utilizzate. Per ulteriori informazioni, vedere l'argomento [Using Strumentazione gestione Windows for Diagnostics](./wmi/index.md) .  
  
 In WCF sono inoltre disponibili diversi strumenti dell'interfaccia utente grafica e della riga di comando per semplificare la creazione, la distribuzione e la gestione di applicazioni WCF. Per ulteriori informazioni, vedere [Windows Communication Foundation Tools](../tools.md). Ad esempio, è possibile usare lo [strumento Editor di configurazione (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare le impostazioni di configurazione di WCF tramite una procedura guidata, anziché modificare direttamente il codice XML. È inoltre possibile utilizzare lo [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare, raggruppare e filtrare i messaggi di traccia in modo da poter diagnosticare, ripristinare e verificare i problemi relativi ai servizi WCF.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dell'applicazione](configuring-your-application.md)
- [Distribuzione di servizi](deploying-services.md)
- [Riferimenti per le eccezioni](./exceptions-reference/index.md)
- [Registrazione eventi](./event-logging/index.md)
- [Registrazione messaggi](message-logging.md)
- [Strumento Editor di configurazione (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)
- [Strumento di registrazione ServiceModel](servicemodel-registration-tool.md)
- [Traccia](./tracing/index.md)
- [Uso di Strumentazione gestione Windows per la diagnostica](./wmi/index.md)
- [Contatori delle prestazioni](./performance-counters/index.md)
- [Strumenti Windows Communication Foundation](../tools.md)
