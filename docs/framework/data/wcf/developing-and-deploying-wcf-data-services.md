---
title: Sviluppo e distribuzione di WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: cf1782eaf54701f0cf93576325b3d46e8bc4d3f1
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261511"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Sviluppare e distribuire servizi dati WCF

In questo argomento fornisce informazioni sullo sviluppo e distribuzione di WCF Data Services. Per informazioni di base su WCF Data Services, vedere [Guida introduttiva](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) e [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Lo sviluppo di WCF Data Services

Quando si utilizza WCF Data Services per creare un servizio dati che supporta il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], è necessario eseguire le seguenti attività di base durante lo sviluppo:

1.  **Definizione del modello di dati**

     WCF Data Services supporta un'ampia gamma di provider del servizio dati che consentono di definire un modello di dati basato sui dati da un'ampia gamma di origini dati, dai database relazionali ai tipi di dati con associazione tardiva. Per altre informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

2.  **Creazione del servizio dati**

     La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

3.  **Configurazione del servizio dati**

     Per impostazione predefinita, WCF Data Services disabilita l'accesso alle risorse esposte da un contenitore di entità. Il <xref:System.Data.Services.DataServiceConfiguration> interfaccia consente di configurare l'accesso alle risorse e operazioni del servizio, specificare la versione supportata di OData e per definire altri comportamenti a livello di servizio, ad esempio il numero massimo di entità che possono essere restituiti o comportamenti di invio in batch in un feed di risposta singola. Per altre informazioni, vedere [configurazione del servizio dati](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

Questo argomento illustra principalmente lo sviluppo e distribuzione dei servizi dati tramite Visual Studio. Per informazioni sulla flessibilità offerta da WCF Data Services per esporre i dati come feed OData, vedere [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Scegliere un Server Web di sviluppo

Quando si sviluppa un servizio dati WCF come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione o [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sito Web usando Visual Studio 2015, è possibile scegliere di server Web su cui eseguire il servizio dati durante lo sviluppo. Il server Web seguenti integrano con Visual Studio per renderne più semplice testare ed eseguire il debug dei servizi dati sul computer locale.

1.  **Server IIS locale**

     Quando si crea un servizio dati che è un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o un sito Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] eseguito su Internet Information Services (IIS), si consiglia di sviluppare e testare il servizio dati tramite IIS sul computer locale. L'esecuzione del servizio dati su IIS facilita l'esecuzione della traccia delle richieste HTTP durante l'esecuzione il debug. Consente inoltre di determinare in anticipo i diritti necessari richiesti da IIS per accedere a file, database e altre risorse richieste dal servizio dati. Per eseguire il servizio dati in IIS, è necessario assicurarsi che IIS sia Windows Communication Foundation (WCF) vengono installati e configurati correttamente e concedere l'accesso agli account IIS nel file system e del database. Per altre informazioni, vedere [Procedura: sviluppare un servizio WCF in esecuzione in IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > È necessario eseguire Visual Studio con diritti di amministratore per abilitare l'ambiente di sviluppo configurare il server IIS locale.

2.  **Server di sviluppo di Visual Studio**

     Visual Studio include un server Web incorporato, Visual Studio Development Server, ovvero il server Web predefinito per [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetti. Questo server Web è progettato per eseguire progetti [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sul computer locale durante lo sviluppo. Il [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) viene illustrato come creare un servizio dati che viene eseguito in Visual Studio Development Server.

     È necessario tenere presente le seguenti limitazioni quando si usa Visual Studio Development Server per sviluppare il servizio dati:

    -   L'accesso al server può essere eseguito solo sul computer locale.

    -   Il server è in ascolto su `localhost` e su una porta specifica, non sulla porta 80 che è la porta predefinita per i messaggi HTTP. Per altre informazioni, vedere [Server Web in Visual Studio per progetti Web ASP.NET](https://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328).

    -   Il server esegue il servizio dati nel contesto dell'account utente corrente. Ad esempio, se si esegue come utente a livello di amministratore, un servizio dati eseguito in Visual Studio Development Server avrà privilegi di amministratore. È possibile che il servizio dati quindi sia in grado di accedere alle risorse che non ha diritto ad accedere se viene distribuito in un server IIS.

    -   Il server non include le funzionalità aggiuntive di IIS, ad esempio l'autenticazione.

    -   Questo server non è possibile gestire i flussi HTTP chunked, che vengono inviati per impostazione predefinita dal client di WCF Data Services quando si accede a dati binari di grandi dimensioni dal servizio dati. Per altre informazioni, vedere [Provider di flusso](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).

    -   Questo server ha problemi con il periodo di elaborazione (`.`) carattere in un URL, anche se questo carattere è supportato da WCF Data Services nei valori chiave.

    > [!TIP]
    > Anche se è possibile usare Visual Studio Development Server per testare i servizi dati durante lo sviluppo, è necessario testare nuovamente dopo la distribuzione in un server Web che esegue IIS.

3.  **Ambiente di sviluppo Microsoft Azure**

     Windows Azure Tools per Visual Studio include un set integrato di strumenti per lo sviluppo di servizi di Azure in Visual Studio. Con questi strumenti, è possibile sviluppare un servizio dati che può essere distribuito a Microsoft Azure ed è possibile testare il servizio dati sul computer locale prima della distribuzione. Usare questi strumenti quando si usa Visual Studio per sviluppare un servizio dati che viene eseguito su piattaforma Windows Azure. È possibile scaricare gli strumenti di Azure per Visual Studio dal [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Per altre informazioni sullo sviluppo di un servizio dati che viene eseguito in Windows Azure, vedere il post [distribuzione di un OData Service in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="development-tips"></a>Suggerimenti per lo sviluppo

Quando si sviluppa un servizio dati è opportuno considerare quanto segue:

-   Determinare i requisiti di sicurezza del servizio dati, se si pianifica di autenticare gli utenti o di limitare l'accesso a utenti specifici. Per altre informazioni, vedere [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

-   Un programma di ispezione HTTP può essere molto utile quando si esegue il debug di un servizio dati in quanto permette di controllare il contenuto dei messaggi di risposta e richiesta. Qualsiasi analizzatore di pacchetti di rete in grado di visualizzare pacchetti non elaborati può essere usato per controllare le richieste HTTP e le risposte del servizio dati.

-   Quando si esegue debug di un servizio dati, si potrebbe desiderare di ottenere altre informazioni su un errore dal servizio dati anziché durante l'operazione normale. È possibile ottenere altre informazioni sull'errore dal servizio dati impostando la proprietà <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> in <xref:System.Data.Services.DataServiceConfiguration> su `true` e impostando la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> dell'attributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> nella classe del servizio dati su `true`. Per altre informazioni, vedere il post [debug di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=201868). È anche possibile abilitare la traccia in WCF per visualizzare le eccezioni generate nel livello di messaggistica HTTP. Per altre informazioni, vedere [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).

-   Un servizio dati viene generalmente sviluppato come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto di applicazione, ma è anche possibile creare il servizio dati come un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto sito Web in Visual Studio. Per informazioni sulle differenze tra i due tipi di progetti, vedere [NIB: progetti di applicazioni Web e progetti di siti Web in Visual Studio](https://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5).

-   Quando si crea un servizio dati tramite il **Aggiungi nuovo elemento** finestra di dialogo in Visual Studio, il servizio dati è ospitato da [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in IIS. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e IIS costituiscono l'host predefinito di un servizio dati, tuttavia sono supportate altre opzioni host. Per altre informazioni, vedere [che ospita il servizio dati](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Distribuire servizi dati WCF

WCF Data Services fornisce flessibilità di scelta per il processo che ospita il servizio dati. È possibile usare Visual Studio per distribuire un servizio dati per le piattaforme seguenti:

-   **Server Web ospitato in IIS**

     Quando un servizio dati viene sviluppato come un progetto [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , può essere distribuito a un server Web IIS tramite i processi di distribuzione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] standard.  Visual Studio offre le seguenti tecnologie di distribuzione per [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], a seconda del tipo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] progetto che ospita il servizio dati che si desidera distribuire.

    -   **Tecnologie di distribuzione per applicazioni Web ASP.NET**

        -   [Pacchetto di distribuzione Web](https://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)

        -   [Pubblicazione con un clic](https://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)

    -   **Tecnologie di distribuzione per siti Web ASP.NET**

        -   [Strumento Copia sito Web](https://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)

        -   [Strumento Pubblica sito Web](https://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)

        -   [XCopy](https://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)

     Per altre informazioni sulle opzioni di distribuzione per un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione, vedere [Cenni preliminari sulla distribuzione Web per Visual Studio e ASP.NET](https://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).

    > [!TIP]
    > Prima di tentare di distribuire il servizio dati a IIS, verificare che sia stata testata la distribuzione a un server Web che esegue IIS. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).

-   **Windows Azure**

     È possibile distribuire un servizio dati in Azure usando Windows Azure Tools per Visual Studio. È possibile scaricare gli strumenti di Azure per Visual Studio dal [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848). Per altre informazioni su come distribuire un servizio dati in Windows Azure, vedere il post [distribuzione di un OData Service in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=201847).

### <a name="deployment-considerations"></a>Considerazioni sulla distribuzione

Quando si distribuisce un servizio dati è opportuno considerare quanto segue:

-   Quando si distribuisce un servizio dati che usa il provider [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] per accedere a un database SQL Server, è possibile che si debbano propagare anche strutture di dati, dati o entrambi gli elementi con la distribuzione del servizio dati. Visual Studio possa creare automaticamente script (file con estensione SQL) per eseguire questa operazione nel database di destinazione e questi script possono essere inclusi nel pacchetto di distribuzione Web di un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dell'applicazione. Per altre informazioni, vedere [procedura: distribuire un Database con un progetto di applicazione Web](https://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Per un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] sito Web, è possibile farlo usando il **Database Publishing Wizard** in Visual Studio. Per altre informazioni, vedere [distribuzione di un Database tramite Database Publishing Wizard](https://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).

-   Poiché WCF Data Services include un'implementazione WCF di base, è possibile usare Windows Server AppFabric per monitorare un servizio dati distribuito a IIS che esegue Windows Server. Per altre informazioni sull'uso di Windows Server AppFabric per monitorare un servizio dati, vedere il post [traccia di WCF Data Services con Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=202005).

## <a name="see-also"></a>Vedere anche

- [Hosting del servizio dati](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
- [Protezione di WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
