---
title: Sviluppo e distribuzione di WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 4591175da5078a194bfe69884701e5432a0c38a3
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389738"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Sviluppare e distribuire WCF Data ServicesDevelop and Deploy WCF Data Services

In questo articolo vengono fornite informazioni sullo sviluppo e la distribuzione di WCF Data ServicesWCF Data Services.This article provides information about developing and deploying WCF Data Services. Per altre informazioni di base su WCF Data ServicesWCF Data Services, vedere [Introduzione](getting-started-with-wcf-data-services.md) e [panoramica.](wcf-data-services-overview.md)

## <a name="develop-wcf-data-services"></a>Sviluppare WCF Data ServicesDevelop WCF Data Services

Quando si usa WCF Data ServicesWCF Data Services per creare un servizio dati che supporta il protocollo OData (Open Data Protocol), è necessario eseguire le attività di base seguenti durante lo sviluppo:When you use WCF Data ServicesWCF Data Services to create a data service that supports the Open Data Protocol (OData), you must perform the following basic tasks during development:

1. **Definizione del modello di dati**

     WCF Data ServicesWCF Data Services supporta un'ampia gamma di provider di servizi dati che consentono di definire un modello di dati basato su dati provenienti da un'ampia gamma di origini dati, dai database relazionali ai tipi di dati ad associazione tardiva. Per ulteriori informazioni, vedere [Provider di servizi dati](data-services-providers-wcf-data-services.md).

2. **Creazione del servizio dati**

     La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configurazione del servizio dati**

     Per impostazione predefinita, WCF Data ServicesWCF Data Services disabilita l'accesso alle risorse esposte da un contenitore di entità. L'interfaccia <xref:System.Data.Services.DataServiceConfiguration> consente di configurare l'accesso alle risorse e alle operazioni del servizio, specificare la versione supportata di OData e di definire altri comportamenti a livello di servizio, ad esempio comportamenti di invio in batch o il numero massimo di entità che possono essere restituite in un singolo feed di risposta. Per ulteriori informazioni, vedere [Configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

In questo articolo viene illustrato principalmente lo sviluppo e la distribuzione di servizi dati tramite Visual Studio.This article covers primarily the development and deployment of data services by using Visual Studio. Per informazioni sulla flessibilità fornita da WCF Data ServicesWCF Data Services per l'esposizione dei dati come feed OData, vedere [Definizione di WCF Data ServicesWCF Data Services](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Scelta di un server Web di sviluppo

Quando si sviluppa un servizio dati WCF come ASP.NET applicazione o ASP.NET sito Web utilizzando Visual Studio 2015, è possibile scegliere tra i server Web in cui eseguire il servizio dati durante lo sviluppo. I server Web seguenti si integrano con Visual Studio per semplificare il test e il debug dei servizi dati nel computer locale.

1. **Server IIS locale**

     Quando si crea un servizio dati che è un'applicazione ASP.NET o un sito Web ASP.NET in esecuzione su Internet Information Services (IIS), è consigliabile sviluppare e testare il servizio dati utilizzando IIS nel computer locale. L'esecuzione del servizio dati su IIS facilita l'esecuzione della traccia delle richieste HTTP durante l'esecuzione il debug. Consente inoltre di determinare in anticipo i diritti necessari richiesti da IIS per accedere a file, database e altre risorse richieste dal servizio dati. Per eseguire il servizio dati in IIS, assicurarsi che IIS e Windows Communication Foundation (WCF) siano installati e configurati correttamente e concedere l'accesso agli account IIS nel file system e nei database. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > È necessario eseguire Visual Studio con diritti di amministratore per consentire all'ambiente di sviluppo di configurare il server IIS locale.

2. **Server di sviluppo di Visual Studio**

     Visual Studio include un server Web incorporato, il server di sviluppo di Visual Studio, che è il server Web predefinito per i progetti ASP.NET. Questo server Web è progettato per eseguire ASP.NET progetti nel computer locale durante lo sviluppo. Guida introduttiva di [WCF Data ServicesWCF Data Services](quickstart-wcf-data-services.md) viene illustrato come creare un servizio dati che viene eseguito nel server di sviluppo di Visual Studio.The WCF Data Services quickstart shows how to create a data service that runs in the Visual Studio Development Server.

     Quando si utilizza Visual Studio Development Server, è necessario tenere presenti le limitazioni seguenti:

    - L'accesso al server può essere eseguito solo sul computer locale.

    - Il server è in ascolto su `localhost` e su una porta specifica, non sulla porta 80 che è la porta predefinita per i messaggi HTTP. Per altre informazioni, vedere [Server Web in Visual Studio per progetti Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Il server esegue il servizio dati nel contesto dell'account utente corrente. Ad esempio, se si esegue come utente a livello di amministratore, un servizio dati in esecuzione nel server di sviluppo di Visual Studio dirà privilegi a livello di amministratore. È possibile che il servizio dati quindi sia in grado di accedere alle risorse che non ha diritto ad accedere se viene distribuito in un server IIS.

    - Il server non include le funzionalità aggiuntive di IIS, ad esempio l'autenticazione.

    - Questo server non è in grado di gestire flussi HTTP in blocchi, che vengono inviati per impostazione predefinita dal client WCF Data ServicesWCF Data Services quando si accede a dati binari di grandi dimensioni dal servizio dati. Per ulteriori informazioni, vedere [Provider di flusso](streaming-provider-wcf-data-services.md).

    - Questo server presenta problemi con`.`l'elaborazione del carattere punto ( ) in un URL, anche se questo carattere è supportato da WCF Data ServicesWCF Data Services nei valori di chiave.

    > [!TIP]
    > Anche se è possibile utilizzare Visual Studio Development Server per testare i servizi dati durante lo sviluppo, è consigliabile testarli nuovamente dopo la distribuzione in un server Web che esegue IIS.

3. **Ambiente di sviluppo Microsoft Azure**

     Windows Azure Tools for Visual Studio includes an integrated set of tools for developing Windows Azure services in Visual Studio. Con questi strumenti, è possibile sviluppare un servizio dati che può essere distribuito a Microsoft Azure ed è possibile testare il servizio dati sul computer locale prima della distribuzione. Usare questi strumenti quando si usa Visual Studio per sviluppare un servizio dati che viene eseguito sulla piattaforma Windows Azure.Use these tools when using Visual Studio to develop a data service that runs on the Windows Azure platform. Per informazioni sull'installazione degli strumenti, vedere Strumenti di Azure per Visual Studio 2015.For information about installing the tools, see [Azure tools for Visual Studio 2015](../../../azure/sdk/vs2015-install.md). Per altre informazioni sullo sviluppo di un servizio dati in esecuzione in Windows Azure, vedere post Distribuzione di un servizio OData in Windows Azure.For more information about developing a data service that runs on Windows Azure, see the post [Deploying an OData Service in Windows Azure.](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)

### <a name="development-tips"></a>Suggerimenti per lo sviluppo

Quando si sviluppa un servizio dati, tenere presente quanto segue:Consider the following when you develop a data service:

- Se si prevede di autenticare gli utenti o limitare l'accesso per utenti specifici, determinare i requisiti di sicurezza del servizio dati. Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md).

- Un programma di ispezione HTTP può essere utile quando si esegue il debug di un servizio dati consentendo di esaminare il contenuto dei messaggi di richiesta e risposta. Qualsiasi analizzatore di pacchetti di rete in grado di visualizzare pacchetti non elaborati può essere usato per controllare le richieste HTTP e le risposte del servizio dati.

- Quando si esegue il debug di un servizio dati, è possibile ottenere ulteriori informazioni su un errore dal servizio dati che durante il normale funzionamento. È possibile ottenere altre informazioni sull'errore dal servizio dati impostando la proprietà <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> in <xref:System.Data.Services.DataServiceConfiguration> su `true` e impostando la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> dell'attributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> nella classe del servizio dati su `true`. Per altre informazioni, vedere il post [Debug di WCF Data ServicesWCF Data Services](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services). È inoltre possibile abilitare la traccia in WCF per visualizzare le eccezioni generate nel livello di messaggistica HTTP. Per altre informazioni, vedere [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Un servizio dati viene in genere sviluppato come progetto di applicazione ASP.NET, ma è anche possibile creare il servizio dati come ASP.NET progetto di sito Web in Visual Studio. Per informazioni sulle differenze tra i due tipi di progetti, vedere [Progetti di applicazione Web e progetti di sito Web in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Quando si crea un servizio dati utilizzando la finestra di dialogo **Aggiungi nuovo elemento** in Visual Studio, il servizio dati è ospitato da ASP.NET in IIS. Mentre ASP.NET e IIS è l'host predefinito per un servizio dati, sono supportate altre opzioni di hosting. Per ulteriori informazioni, vedere [Hosting del servizio dati](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Distribuire WCF Data ServicesDeploy WCF Data Services

WCF Data Services fornisce flessibilità di scelta per il processo che ospita il servizio dati. È possibile usare Visual Studio per distribuire un servizio dati nelle piattaforme seguenti:You can use Visual Studio to deploy a data service to the following platforms:

- **Server Web ospitato in IIS**

    Quando un servizio dati viene sviluppato come progetto ASP.NET, può essere distribuito in un server Web IIS utilizzando i processi di distribuzione ASP.NET standard.  Visual Studio fornisce le tecnologie di distribuzione seguenti per ASP.NET, a seconda del tipo di progetto di ASP.NET che ospita il servizio dati che si sta distribuendo.

  - **Tecnologie di distribuzione per applicazioni Web ASP.NET**

    - [Procedura: Creare un pacchetto di distribuzione Web in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Procedura: distribuire un progetto Web tramite la pubblicazione con un clic in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Tecnologie di distribuzione per siti Web ASP.NET**

    - [Procedura: copiare i file del sito Web con lo strumento Copia sito Web](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Procedura: pubblicare siti Web](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Procedura dettagliata: distribuzione di un'applicazione Web ASP.NET tramite XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Per ulteriori informazioni sulle opzioni di distribuzione per un'applicazione ASP.NET, vedere [Cenni](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110))preliminari sulla distribuzione Web per Visual Studio e ASP.NET .

    > [!TIP]
    > Prima di tentare di distribuire il servizio dati a IIS, verificare che sia stata testata la distribuzione a un server Web che esegue IIS. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Microsoft Azure**

     È possibile distribuire un servizio dati in Windows Azure usando Strumenti di Windows Azure per Visual Studio.You can deploy a data service to Windows Azure by using Windows Azure Tools for Visual Studio. È possibile scaricare Windows Azure Tools for Visual Studio [dall'Area download Microsoft](https://go.microsoft.com/fwlink/?LinkID=201848). Per altre informazioni sulla distribuzione di un servizio dati in Windows Azure, vedere il post Distribuzione di un servizio OData in Windows Azure.For more information about deploying a data service to Windows Azure, see the post [Deploying an OData Service in Windows Azure.](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure)

### <a name="deployment-considerations"></a>Considerazioni sulla distribuzione

Quando si distribuisce un servizio dati, tenere presente quanto segue:Consider the following when deploying a data service:

- Quando si distribuisce un servizio dati che utilizza il provider Entity Framework per accedere a un database di SQL Server, potrebbe anche essere necessario propagare strutture di dati, dati o entrambi con la distribuzione del servizio dati. Visual Studio può creare automaticamente script (file con estensione sql) per eseguire questa operazione nel database di destinazione e questi script possono essere inclusi nel pacchetto di distribuzione Web di un'applicazione ASP.NET. Per ulteriori informazioni, vedere [Procedura: distribuire un database con un progetto](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100))di applicazione Web . Per un sito Web ASP.NET, è possibile eseguire questa operazione utilizzando la **Pubblicazione guidata database** in Visual Studio. Per ulteriori informazioni, vedere [Pubblicazione di un database SQL](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

- Poiché WCF Data ServicesWCF Data Services include un'implementazione WCF di base, è possibile usare Windows Server AppFabric per monitorare un servizio dati distribuito in IIS in esecuzione in Windows Server.Because WCF Data Services includes a basic WCF implementation, you can use Windows Server AppFabric to monitor a data service deployed to IIS running on Windows Server. Per altre informazioni sull'uso di Windows Server AppFabric per monitorare un servizio dati, vedere il post [Rilevamento di WCF Data Services con Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Vedere anche

- [Hosting del servizio dati](hosting-the-data-service-wcf-data-services.md)
- [Protezione di WCF Data Services](securing-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)
