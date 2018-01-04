---
title: Amministrazione e diagnostica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, diagnostics
- Windows Communication Foundation, administration
- diagnostics [WCF]
- WCF, diagnostics
- administration [WCF]
- WCF, administration
ms.assetid: 34c81c08-0e0f-4fbc-9ae8-91948640ee43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d26386a0669c92b1b21559474c8f5f61862e6de7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="administration-and-diagnostics"></a>Amministrazione e diagnostica
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] fornisce numerose funzionalità che possono aiutare a monitorare le varie fasi della vita di un'applicazione. È ad esempio possibile utilizzare la configurazione per impostare servizi e client in fase di distribuzione. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] include un vasto set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espone inoltre dati di ispezione di un servizio in fase di esecuzione tramite un provider WMI di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. In caso di errore dell'applicazione o di comportamento non corretto, è possibile utilizzare il Registro eventi per controllare se si è verificato qualcosa di grave. È inoltre possibile utilizzare la registrazione messaggi e le tracce per controllare gli eventi end-to-end in corso nell'applicazione. Queste funzionalità aiutano sia gli sviluppatori che i professionisti IT a identificare e risolvere i problemi di un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] quando non si comporta correttamente.  
  
> [!NOTE]
>  Se si ricevono errori senza informazioni di dettaglio specifico, è necessario abilitare il `includeExceptionDetailInFaults` attributo del [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) elemento di configurazione. In tal modo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invia i dettagli relativi alle eccezioni ai client e consente di individuare i problemi più comuni senza dover eseguire diagnosi più avanzate. Per ulteriori informazioni, vedere [invio e ricezione di errori](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="diagnostics-features-provided-by-wcf"></a>Funzionalità di diagnostica fornite da WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce le funzionalità di diagnostica seguenti:  
  
-   Le tracce end-to-end forniscono dati di strumentazione per risolvere i problemi di un'applicazione senza utilizzare un debugger. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] restituisce in output le tracce sia per le attività cardine del processo sia per i messaggi di errore. Tale processo può comprendere l'apertura di una channel factory o l'invio e ricezione di messaggi tramite un host del servizio. È possibile attivare la traccia per monitorare lo stato di avanzamento di un'applicazione in esecuzione. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md) argomento. Per comprendere come è possibile utilizzare la traccia per il debug dell'applicazione, vedere il [utilizzando opzioni di traccia per risolvere i problemi dell'applicazione](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md) argomento.  
  
-   La registrazione dei messaggi consente di vedere il loro aspetto prima e dopo la trasmissione. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [registrazione messaggi](../../../../docs/framework/wcf/diagnostics/message-logging.md) argomento.  
  
-   La traccia eventi scrive gli eventi nel Registro eventi per qualsiasi problema importante. È quindi possibile utilizzare il Visualizzatore eventi per esaminare eventuali anomalie. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [registrazione degli eventi](../../../../docs/framework/wcf/diagnostics/event-logging/index.md) argomento.  
  
-   I contatori delle prestazioni esposti tramite Performance Monitor consentono di monitorare lo stato d'integrità dell'applicazione e del sistema. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [i contatori delle prestazioni](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md) argomento.  
  
-   Lo spazio dei nomi <xref:System.ServiceModel.Configuration> consente di caricare file di configurazione e configurare un endpoint del servizio o client. È possibile utilizzare il modello a oggetti per inserire in uno script le modifiche a numerose applicazioni quando è necessario distribuire gli aggiornamenti a più computer. In alternativa, è possibile utilizzare il [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per modificare le impostazioni di configurazione tramite una procedura guidata grafica. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [la configurazione dell'applicazione](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md) argomento.  
  
-   Con WMI è possibile scoprire quali servizi sono in attesa in un computer e le associazioni utilizzate. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]il [tramite Strumentazione gestione Windows per la diagnostica](../../../../docs/framework/wcf/diagnostics/wmi/index.md) argomento.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fornisce inoltre numerosi strumenti della riga di comando e GUI per semplificare la creazione, distribuzione e gestione di applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Strumenti di Windows Communication Foundation](../../../../docs/framework/wcf/tools.md). Ad esempio, è possibile utilizzare il [strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le impostazioni di configurazione tramite una procedura guidata, anziché modificare direttamente il codice XML. È inoltre possibile utilizzare il [strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) per visualizzare, raggruppare e filtrare i messaggi di traccia in modo che è possibile diagnosticare, riparare e verificare i problemi con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizi.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione dell'applicazione](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)  
 [Distribuzione di servizi](../../../../docs/framework/wcf/diagnostics/deploying-services.md)  
 [Riferimenti per le eccezioni](../../../../docs/framework/wcf/diagnostics/exceptions-reference/index.md)  
 [Registrazione eventi](../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [Registrazione messaggi](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [Strumento di registrazione ServiceModel](../../../../docs/framework/wcf/diagnostics/servicemodel-registration-tool.md)  
 [Traccia](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Uso di Strumentazione gestione Windows per la diagnostica](../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
 [Contatori delle prestazioni](../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)  
 [Strumenti Windows Communication Foundation](../../../../docs/framework/wcf/tools.md)
