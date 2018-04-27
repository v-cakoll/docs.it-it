---
title: Sviluppo e distribuzione di WCF Data Services
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fbfd28931f484c5b643dad278b358e7ac2a2945
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="developing-and-deploying-wcf-data-services"></a>Sviluppo e distribuzione di WCF Data Services
In questo argomento vengono fornite informazioni sullo sviluppo e sulla distribuzione di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Per informazioni di base su [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], vedere [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) e [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).  
  
## <a name="developing-wcf-data-services"></a>Sviluppo di WCF Data Services  
 Quando si usa [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per creare un servizio dati che supporta [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], è necessario effettuare le seguenti attività di base durante lo sviluppo:  
  
1.  **Definizione del modello di dati**  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta diversi provider di servizi dati che consentono di definire un modello di dati basato su dati di varie origini, dai database relazionali ai tipi di dati ad associazione tardiva. Per ulteriori informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
2.  **Creazione del servizio dati**  
  
     La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Configurazione del servizio dati**  
  
     Per impostazione predefinita, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] disabilita l'accesso alle risorse esposte da un contenitore di entità. L'interfaccia <xref:System.Data.Services.DataServiceConfiguration> consente di configurare l'accesso a risorse e operazioni del servizio, di specificare la versione supportata di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]e di definire altri comportamenti a livello di server, ad esempio i comportamenti di invio in batch o il numero massimo di entità che è possibile restituire in un unico feed di risposta. Per ulteriori informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 In questo argomento si analizza principalmente lo sviluppo e distribuzione dei servizi dati tramite Visual Studio. Per informazioni sulla flessibilità offerta da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] per esporre i dati come feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
### <a name="choosing-a-development-web-server"></a>Scelta di un server Web di sviluppo  
 Quando si sviluppa un servizio dati WCF come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sito Web usando Visual Studio, è possibile scegliere di server Web su cui eseguire il servizio dati durante lo sviluppo. Il server Web seguenti si integrano con Visual Studio per semplificare la di test e debug dei servizi dati sul computer locale.  
  
1.  **Server IIS locale**  
  
     Quando si crea un servizio dati che è un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o un sito Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] eseguito su Internet Information Services (IIS), si consiglia di sviluppare e testare il servizio dati tramite IIS sul computer locale. L'esecuzione del servizio dati su IIS facilita l'esecuzione della traccia delle richieste HTTP durante l'esecuzione il debug. Consente inoltre di determinare in anticipo i diritti necessari richiesti da IIS per accedere a file, database e altre risorse richieste dal servizio dati. Per eseguire il servizio dati su IIS, è necessario assicurarsi che IIS e [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] siano installati e configurati correttamente e che l'accesso sia stato concesso agli account IIS nel file system e nei database. Per altre informazioni, vedere [Procedura: sviluppare un servizio WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
    > [!NOTE]
    >  È necessario eseguire Visual Studio con diritti di amministratore per abilitare l'ambiente di sviluppo alla configurazione del server IIS locale.  
  
2.  **Server di sviluppo di Visual Studio**  
  
     Visual Studio include un server Web incorporato, Visual Studio Development Server, ovvero il server Web predefinito per [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetti. Questo server Web è progettato per eseguire progetti [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sul computer locale durante lo sviluppo. Il [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) viene illustrato come creare un servizio dati che viene eseguito in Visual Studio Development Server.  
  
     È necessario tenere presente le seguenti limitazioni quando si utilizza Visual Studio Development Server per sviluppare il servizio dati:  
  
    -   L'accesso al server può essere eseguito solo sul computer locale.  
  
    -   Il server è in ascolto su `localhost` e su una porta specifica, non sulla porta 80 che è la porta predefinita per i messaggi HTTP. Per altre informazioni, vedere [Server Web in Visual Studio per progetti Web ASP.NET](http://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
    -   Il server esegue il servizio dati nel contesto dell'account utente corrente. Ad esempio, se si esegue come utente a livello di amministratore, un servizio dati eseguito in Visual Studio Development Server avrà i privilegi di amministratore a livello. È possibile che il servizio dati quindi sia in grado di accedere alle risorse che non ha diritto ad accedere se viene distribuito in un server IIS.  
  
    -   Il server non include le funzionalità aggiuntive di IIS, ad esempio l'autenticazione.  
  
    -   Il server non può gestire i flussi HTTP Chunked che vengono inviati per impostazione predefinita dal client [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] quando si esegue l'accesso a dati binari di grandi dimensioni dal servizio dati. Per ulteriori informazioni, vedere [Provider di flusso](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
    -   In questo server l'elaborazione del carattere punto (`.`) negli URL risulta problematica anche se il punto è supportato da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] nei valori delle chiavi.  
  
    > [!TIP]
    >  Anche se è possibile usare Visual Studio Development Server per testare i servizi dati durante lo sviluppo, è necessario verificarne nuovamente dopo la distribuzione a un server Web che esegue IIS.  
  
3.  **Ambiente di sviluppo Microsoft Azure**  
  
     Strumenti di Windows Azure per Visual Studio include un set integrato di strumenti per lo sviluppo di servizi di Microsoft Azure in Visual Studio. Con questi strumenti, è possibile sviluppare un servizio dati che può essere distribuito a Microsoft Azure ed è possibile testare il servizio dati sul computer locale prima della distribuzione. Utilizzare questi strumenti quando si utilizza Visual Studio per sviluppare un servizio dati che viene eseguita nella piattaforma Windows Azure. È possibile scaricare gli strumenti di Azure per Visual Studio il [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] llo sviluppo di un servizio dati in esecuzione in Microsoft Azure, vedere il post sulla [distribuzione di un servizio OData in Microsoft Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="development-tips"></a>Suggerimenti per lo sviluppo  
 Quando si sviluppa un servizio dati è opportuno considerare quanto segue:  
  
-   Determinare i requisiti di sicurezza del servizio dati, se si pianifica di autenticare gli utenti o di limitare l'accesso a utenti specifici. Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
-   Un programma di ispezione HTTP può essere molto utile quando si esegue il debug di un servizio dati in quanto permette di controllare il contenuto dei messaggi di risposta e richiesta. Qualsiasi analizzatore di pacchetti di rete in grado di visualizzare pacchetti non elaborati può essere usato per controllare le richieste HTTP e le risposte del servizio dati.  
  
-   Quando si esegue debug di un servizio dati, si potrebbe desiderare di ottenere altre informazioni su un errore dal servizio dati anziché durante l'operazione normale. È possibile ottenere altre informazioni sull'errore dal servizio dati impostando la proprietà <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> in <xref:System.Data.Services.DataServiceConfiguration> su `true` e impostando la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> dell'attributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> nella classe del servizio dati su `true`. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] il post sul [debug di WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=201868). È possibile abilitare la traccia anche in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per visualizzare le eccezioni generate nel livello di messaggistica HTTP. Per altre informazioni, vedere [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Un servizio dati viene generalmente sviluppato come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto di applicazione, ma è possibile anche creare servizio dati come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto sito Web in Visual Studio. Per informazioni sulle differenze tra i due tipi di progetti, vedere [NIB: progetti di applicazione Web e progetti di sito Web in Visual Studio](http://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5).  
  
-   Quando si crea un servizio dati tramite il **Aggiungi nuovo elemento** finestra di dialogo in Visual Studio, il servizio dati è ospitato da [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in IIS. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e IIS costituiscono l'host predefinito di un servizio dati, tuttavia sono supportate altre opzioni host. Per ulteriori informazioni, vedere [ospita il servizio dati](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).  
  
## <a name="deploying-wcf-data-services"></a>Distribuzione di WCF Data Services  
 WCF Data Services fornisce flessibilità di scelta per il processo che ospita il servizio dati. È possibile utilizzare Visual Studio per distribuire un servizio dati alle piattaforme seguenti:  
  
-   **Server Web ospitato in IIS**  
  
     Quando un servizio dati viene sviluppato come un progetto [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , può essere distribuito a un server Web IIS tramite i processi di distribuzione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] standard.  Visual Studio fornisce le tecnologie di distribuzione seguenti per [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], a seconda del tipo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetti che ospita il servizio dati che si sta distribuendo.  
  
    -   **Tecnologie di distribuzione per applicazioni Web ASP.NET**  
  
        -   [Pacchetto di distribuzione Web](http://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [Pubblicazione con un clic](http://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **Tecnologie di distribuzione per siti Web ASP.NET**  
  
        -   [Strumento Copia sito Web](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [Strumento Pubblica sito Web](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] opzioni di distribuzione per un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione, vedere [Panoramica della distribuzione Web per Visual Studio e ASP.NET](http://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).  
  
    > [!TIP]
    >  Prima di tentare di distribuire il servizio dati a IIS, verificare che sia stata testata la distribuzione a un server Web che esegue IIS. Per altre informazioni, vedere [Procedura: sviluppare un servizio WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
-   **Windows Azure**  
  
     È possibile distribuire un servizio dati in Windows Azure utilizzando gli strumenti di Azure per Visual Studio. È possibile scaricare gli strumenti di Azure per Visual Studio il [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848). [!INCLUDE[crabout](../../../../includes/crabout-md.md)] lla distribuzione di un servizio dati in Microsoft Azure, vedere il post sulla [distribuzione di un servizio OData in Microsoft Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="deployment-considerations"></a>Considerazioni sulla distribuzione  
 Quando si distribuisce un servizio dati è opportuno considerare quanto segue:  
  
-   Quando si distribuisce un servizio dati che usa il provider [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] per accedere a un database SQL Server, è possibile che si debbano propagare anche strutture di dati, dati o entrambi gli elementi con la distribuzione del servizio dati. Visual Studio possa creare automaticamente script (file con estensione SQL) per eseguire questa operazione nel database di destinazione e tali script possono essere inclusi nel pacchetto di distribuzione Web di un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione. Per ulteriori informazioni, vedere [NIB: procedura: distribuire un Database con un progetto di applicazione Web](http://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Per un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sito Web, è possibile farlo utilizzando il **Database Publishing Wizard** in Visual Studio. Per altre informazioni, vedere [distribuzione di un Database tramite Database Publishing Wizard](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).  
  
-   Poiché [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include un'implementazione di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di base, è possibile usare Windows Server AppFabric per il monitoraggio di un servizio dati distribuito a IIS che è in esecuzione su Windows Server. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] ll'uso di Windows Server AppFabric per monitorare un servizio dati, vedere il post sul [monitoraggio di WCF Data Services con Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=202005).  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting del servizio dati](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [Protezione di WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
