---
title: Sviluppo e distribuzione di WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 7519dce8ed17bc623173f30222296ffaa42b4341
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416067"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Sviluppare e distribuire WCF Data Services

In questo articolo vengono fornite informazioni sullo sviluppo e la distribuzione di WCF Data Services. Per informazioni di base su WCF Data Services, vedere [Introduzione](getting-started-with-wcf-data-services.md) e [Panoramica](wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Sviluppare WCF Data Services

Quando si utilizza WCF Data Services per creare un servizio dati che supporta il Open Data Protocol (OData), è necessario eseguire le seguenti attività di base durante lo sviluppo:

1. **Definizione del modello di dati**

     WCF Data Services supporta un'ampia gamma di provider di servizi dati che consentono di definire un modello di dati basato su dati di un'ampia gamma di origini dati, dai database relazionali ai tipi di dati ad associazione tardiva. Per ulteriori informazioni, vedere [provider di servizi dati](data-services-providers-wcf-data-services.md).

2. **Creazione del servizio dati**

     La maggior parte dei servizi di base espone una classe che eredita dalla classe <xref:System.Data.Services.DataService%601> , con un tipo `T` che corrisponde al nome completo dello spazio dei nomi del contenitore di entità. Per altre informazioni, vedere [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Configurazione del servizio dati**

     Per impostazione predefinita, WCF Data Services Disabilita l'accesso alle risorse esposte da un contenitore di entità. L' <xref:System.Data.Services.DataServiceConfiguration> interfaccia consente di configurare l'accesso a risorse e operazioni del servizio, di specificare la versione supportata di OData e di definire altri comportamenti a livello di servizio, ad esempio i comportamenti di invio in batch o il numero massimo di entità che possono essere restituite in un singolo feed di risposta. Per ulteriori informazioni, vedere [configurazione del servizio dati](configuring-the-data-service-wcf-data-services.md).

Questo articolo illustra principalmente lo sviluppo e la distribuzione dei servizi dati tramite Visual Studio. Per informazioni sulla flessibilità fornita da WCF Data Services per esporre i dati come feed OData, vedere Definizione di [WCF Data Services](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Scegliere un server Web di sviluppo

Quando si sviluppa un servizio dati WCF come applicazione ASP.NET o sito Web ASP.NET utilizzando Visual Studio 2015, è possibile scegliere tra i server Web su cui eseguire il servizio dati durante lo sviluppo. I server Web seguenti si integrano con Visual Studio per semplificare il test e il debug dei servizi dati nel computer locale.

1. **Server IIS locale**

     Quando si crea un servizio dati che è un'applicazione ASP.NET o un sito Web ASP.NET eseguito in Internet Information Services (IIS), si consiglia di sviluppare e testare il servizio dati utilizzando IIS nel computer locale. L'esecuzione del servizio dati su IIS facilita l'esecuzione della traccia delle richieste HTTP durante l'esecuzione il debug. Consente inoltre di predeterminare i diritti necessari richiesti da IIS per accedere a file, database e altre risorse richieste dal servizio dati. Per eseguire il servizio dati su IIS, assicurarsi che IIS e Windows Communication Foundation (WCF) siano installati e configurati correttamente e concedere l'accesso agli account IIS nel file system e nei database. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > È necessario eseguire Visual Studio con diritti di amministratore per abilitare l'ambiente di sviluppo per la configurazione del server IIS locale.

2. **Server di sviluppo di Visual Studio**

     Visual Studio include un server Web incorporato, il Server di sviluppo Visual Studio, che è il server Web predefinito per i progetti ASP.NET. Questo server Web è progettato per eseguire progetti ASP.NET nel computer locale durante lo sviluppo. Nella [Guida introduttiva WCF Data Services](quickstart-wcf-data-services.md) viene illustrato come creare un servizio dati in esecuzione nel server di sviluppo Visual Studio.

     Quando si usa il Server di sviluppo Visual Studio per sviluppare il servizio dati, tenere presenti le limitazioni seguenti:

    - L'accesso al server può essere eseguito solo sul computer locale.

    - Il server è in ascolto su `localhost` e su una porta specifica, non sulla porta 80 che è la porta predefinita per i messaggi HTTP. Per altre informazioni, vedere [Server Web in Visual Studio per progetti Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Il server esegue il servizio dati nel contesto dell'account utente corrente. Se, ad esempio, si esegue come utente a livello di amministratore, un servizio dati in esecuzione nel Server di sviluppo Visual Studio avrà privilegi a livello di amministratore. È possibile che il servizio dati quindi sia in grado di accedere alle risorse che non ha diritto ad accedere se viene distribuito in un server IIS.

    - Il server non include le funzionalità aggiuntive di IIS, ad esempio l'autenticazione.

    - Questo server non è in grado di gestire i flussi HTTP in blocchi, che vengono inviati per impostazione predefinita dal client WCF Data Services quando si accede a dati binari di grandi dimensioni dal servizio dati. Per ulteriori informazioni, vedere [provider di flussi](streaming-provider-wcf-data-services.md).

    - Questo server presenta problemi di elaborazione del carattere punto ( `.` ) in un URL, anche se questo carattere è supportato da WCF Data Services nei valori chiave.

    > [!TIP]
    > Anche se è possibile utilizzare il Server di sviluppo Visual Studio per testare i servizi dati durante lo sviluppo, è necessario testarli nuovamente dopo la distribuzione in un server Web che esegue IIS.

3. **Ambiente di sviluppo di Azure**

     Gli strumenti di Azure per Visual Studio includono un set integrato di strumenti per lo sviluppo di servizi di Azure in Visual Studio. Con questi strumenti è possibile sviluppare un servizio dati che può essere distribuito in Azure ed è possibile testare il servizio dati sul computer locale prima della distribuzione. Usare questi strumenti quando si usa Visual Studio per sviluppare un servizio dati in esecuzione nella piattaforma Azure. Per informazioni sull'installazione degli strumenti, vedere [strumenti di Azure per Visual Studio 2015](../../../azure/vs2015-install.md). Per ulteriori informazioni sullo sviluppo di un servizio dati in esecuzione in Azure, vedere il post sulla [distribuzione di un servizio OData in Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="development-tips"></a>Suggerimenti per lo sviluppo

Quando si sviluppa un servizio dati, tenere presente quanto segue:

- Se si prevede di autenticare gli utenti o di limitare l'accesso per utenti specifici, determinare i requisiti di sicurezza del servizio dati. Per altre informazioni, vedere [Securing WCF Data Services](securing-wcf-data-services.md).

- Un programma di ispezione HTTP può essere utile quando si esegue il debug di un servizio dati consentendo di esaminare il contenuto dei messaggi di richiesta e risposta. Qualsiasi analizzatore di pacchetti di rete in grado di visualizzare pacchetti non elaborati può essere usato per controllare le richieste HTTP e le risposte del servizio dati.

- Quando si esegue il debug di un servizio dati, potrebbe essere necessario ottenere ulteriori informazioni su un errore dal servizio dati anziché durante il normale funzionamento. È possibile ottenere altre informazioni sull'errore dal servizio dati impostando la proprietà <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> in <xref:System.Data.Services.DataServiceConfiguration> su `true` e impostando la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> dell'attributo <xref:System.ServiceModel.Description.ServiceDebugBehavior> nella classe del servizio dati su `true`. Per ulteriori informazioni, vedere il post [debug WCF Data Services](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services). È anche possibile abilitare la traccia in WCF per visualizzare le eccezioni generate nel livello di messaggistica HTTP. Per altre informazioni, vedere [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Un servizio dati viene in genere sviluppato come progetto di applicazione ASP.NET, ma è anche possibile creare il servizio dati come progetto di sito Web ASP.NET in Visual Studio. Per informazioni sulle differenze tra i due tipi di progetti, vedere [progetti di applicazioni Web rispetto ai progetti di siti Web in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Quando si crea un servizio dati tramite la finestra di dialogo **Aggiungi nuovo elemento** in Visual Studio, il servizio dati è ospitato da ASP.NET in IIS. Mentre ASP.NET e IIS sono l'host predefinito per un servizio dati, sono supportate altre opzioni di hosting. Per ulteriori informazioni, vedere [hosting del servizio dati](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Distribuisci WCF Data Services

WCF Data Services fornisce flessibilità di scelta per il processo che ospita il servizio dati. È possibile usare Visual Studio per distribuire un servizio dati nelle piattaforme seguenti:

- **Server Web ospitato in IIS**

    Quando un servizio dati viene sviluppato come progetto ASP.NET, può essere distribuito a un server Web IIS tramite i processi di distribuzione standard di ASP.NET. Visual Studio fornisce le tecnologie di distribuzione seguenti per ASP.NET, a seconda del tipo di progetto ASP.NET che ospita il servizio dati che si sta distribuendo.

  - **Tecnologie di distribuzione per applicazioni Web ASP.NET**

    - [Procedura: Creare un pacchetto di distribuzione Web in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Procedura: distribuire un progetto Web tramite la pubblicazione con un clic in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Tecnologie di distribuzione per siti Web ASP.NET**

    - [Procedura: copiare i file di un sito Web con lo strumento Copia sito Web](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Procedura: pubblicare siti Web](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Procedura dettagliata: distribuzione di un'applicazione Web ASP.NET con XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Per ulteriori informazioni sulle opzioni di distribuzione per un'applicazione ASP.NET, vedere [Cenni preliminari sulla distribuzione Web per Visual Studio e ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Prima di tentare di distribuire il servizio dati a IIS, verificare che sia stata testata la distribuzione a un server Web che esegue IIS. Per altre informazioni, vedere [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Azure**

     È possibile distribuire un servizio dati in Azure usando [gli strumenti di Azure per Visual Studio](../../../azure/vs2015-install.md). Per ulteriori informazioni sulla distribuzione di un servizio dati in Azure, vedere [distribuzione di un servizio OData in Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="deployment-considerations"></a>Considerazioni sulla distribuzione

Quando si distribuisce un servizio dati, tenere presente quanto segue:

- Quando si distribuisce un servizio dati che utilizza il provider di Entity Framework per accedere a un database SQL Server, potrebbe essere necessario propagare anche strutture di dati, dati o entrambi con la distribuzione del servizio dati. Visual Studio è in grado di creare automaticamente script (file con estensione SQL) per eseguire questa operazione nel database di destinazione e tali script possono essere inclusi nel pacchetto di distribuzione Web di un'applicazione ASP.NET. Per altre informazioni, vedere [procedura: distribuire un database con un progetto di applicazione Web](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)). Per un sito Web ASP.NET, è possibile eseguire questa operazione utilizzando la **pubblicazione guidata database** in Visual Studio. Per ulteriori informazioni, vedere [pubblicazione di un database SQL](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

- Poiché WCF Data Services include un'implementazione WCF di base, è possibile usare Windows Server AppFabric per monitorare un servizio dati distribuito in IIS in esecuzione in Windows Server. Per ulteriori informazioni sull'utilizzo di Windows Server AppFabric per il monitoraggio di un servizio dati, vedere il post di [WCF Data Services Tracking con Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Vedere anche

- [Hosting del servizio dati](hosting-the-data-service-wcf-data-services.md)
- [Protezione di WCF Data Services](securing-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)
