---
title: Processo di sviluppo per Azure
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Processo di sviluppo per Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 21826e2c90d234d873cc06bfae3bd22ce89a62d2
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="development-process-for-azure"></a>Processo di sviluppo per Azure

> _"Con il cloud, agli utenti e aziende di piccole dimensioni può blocca le dita e impostare immediatamente i servizi di livello aziendale."_  
> _-Roy Stephan_

 ## <a name="vision"></a>Visione

> *Sviluppare applicazioni ASP .NET Core ben progettate il modo in cui che si desidera, tramite Visual Studio o dotnet CLI e codice di Visual Studio o l'editor preferito.*

## <a name="development-environment-for-aspnet-core-apps"></a>Ambiente di sviluppo per applicazioni ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Gli strumenti di sviluppo scelte: IDE o editor

Se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha la copertura durante lo sviluppo di applicazioni ASP.NET Core.

**Visual Studio 2017.** Se si utilizza *Visual Studio 2017* la compilazione di ASP.NET Core applicazioni purché disponga di *lo sviluppo multipiattaforma con .NET Core* installato carico di lavoro. Nella figura 10-1 viene illustrato il carico di lavoro richiesto nella finestra di dialogo di installazione di Visual Studio 2017.

![](./media/image10-1.png)

**Nella figura 10-1.** Installazione del carico di lavoro di .NET Core in Visual Studio 2017.

[Scarica Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code e dotnet CLI** (strumenti multipiattaforma per Windows, Mac e Linux). Se si preferisce un editor leggero e multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare Microsoft Visual Studio Code e dotnet CLI. Questi prodotti forniscono un'esperienza semplice ed efficace che consente di ottimizzare il flusso di lavoro di sviluppo. Inoltre, supporta le estensioni di Visual Studio Code per C\# e lo sviluppo web, fornire intellisense e attività di collegamento all'interno dell'editor.

[Scaricare il SDK .NET di base](https://www.microsoft.com/net/download/core)

[Scaricare il codice di Visual Studio](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Flusso di lavoro di sviluppo per applicazioni ASP.NET Core ospitato di Azure

Il ciclo di vita di sviluppo di applicazioni viene avviato dal computer di ogni sviluppatore, la generazione di codice l'app utilizzando la lingua desiderata e il relativo test in locale. Gli sviluppatori possono scegliere il controllo del codice sorgente preferito e possono configurare l'integrazione continua (CI) e/o recapito/distribuzione continua (CD) utilizzando un server di compilazione o in base alle funzionalità incorporate di Azure.

Per iniziare con lo sviluppo di un'applicazione ASP.NET di base utilizzando l'elemento di configurazione/CD, è possibile utilizzare Visual Studio Team Services o l'organizzazione proprietari di Team Foundation Server (TFS).

### <a name="initial-setup"></a>Configurazione iniziale

Per creare una pipeline di rilascio per l'app, è necessario avere il codice dell'applicazione nel controllo del codice sorgente. Configurare un repository locale e connetterlo a un archivio remoto in un progetto team. Seguire queste istruzioni:

-   [Condividere il codice con Git e di Visual Studio](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs) o

-   [Condividere il codice con TFVC e Visual Studio](https://docs.microsoft.com/vsts/tfvc/share-your-code-in-tfvc-vs)

Creare un servizio App di Azure in cui verrà distribuita l'applicazione. Creare un'App Web, passare al pannello delle servizi App nel portale di Azure. Fare clic su + Aggiungi, selezionare il modello di applicazione Web, fare clic su Crea e specificare un nome e altri dettagli. L'app web sarà accessibile da {name}. azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Figura 10-2.** Creazione di una nuova App Web di Azure App Service nel portale di Azure.

Il processo di compilazione CI eseguirà una compilazione automatica ogni volta che viene eseguito il commit al repository di controllo codice sorgente del progetto nuovo codice. Ciò consente di verificare immediatamente che il codice verrà compilato (e, idealmente, supera i test automatizzati) e potenzialmente possono essere distribuiti. Questa compilazione CI produrrà un web distribuire l'elemento di pacchetto e pubblicarlo per l'utilizzo dal processo di CD-ROM.

[Definire il processo di compilazione CI](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#ci)

Assicurarsi di abilitare l'integrazione continua in modo il sistema verrà accodare una compilazione ogni volta che un utente membro del team esegue il commit di nuovo codice. La compilazione di test e verificare che produce un web distribuire un pacchetto come uno dei relativi elementi.

Quando una compilazione ha esito positivo, il processo CD distribuirà i risultati della compilazione CI all'App web di Azure. A questo scopo, creare e configurare un *versione*, che verrà distribuito del servizio App di Azure.

[Definire il processo di rilascio del CD](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#cd)

Una volta configurata la pipeline CI/CD, è possibile effettuare aggiornamenti per l'app web e ne esegue il commit in modo che vengano distribuiti nel controllo del codice sorgente.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Flusso di lavoro per lo sviluppo di applicazioni ASP.NET Core ospitato di Azure

Dopo aver configurato l'account di Azure e il processo di CI/CD, lo sviluppo di applicazioni ASP.NET Core ospitato di Azure è semplice. Di seguito sono indicati i passaggi di base che accettano in genere quando si compila un'applicazione ASP.NET di base, ospitata in Azure App Service come un'App Web, come illustrato nella figura 10-3.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Nella figura 10-3.** Flusso di lavoro dettagliato per la creazione di applicazioni ASP.NET Core e all'hosting in Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Passaggio 1. Ciclo interno ambiente di sviluppo locale

Sviluppo dell'applicazione ASP.NET di base per la distribuzione in Azure non è diverso dallo sviluppo dell'applicazione in caso contrario. Utilizzare l'ambiente di sviluppo locale acquisita familiarità con, se Visual Studio 2017 o dotnet CLI e codice di Visual Studio o l'editor preferito. È possibile scrivere codice, eseguire e debug le modifiche, eseguire test automatizzati e apportare commit locale al controllo del codice sorgente fino a quando non si è pronti per il push delle modifiche nel repository di controllo del codice sorgente condiviso.

#### <a name="step-2-application-code-repository"></a>Passaggio 2. Repository di codice dell'applicazione

Ogni volta che si è pronti per condividere il codice con il team, è necessario il push delle modifiche dal repository del codice sorgente locale al repository di origine condivisa del team. Se si è collaborato in un ramo personalizzato, questo passaggio prevede in genere l'unione di codice in un branch condiviso (ad esempio per mezzo di un [richiesta pull](https://docs.microsoft.com/vsts/git/pull-requests)).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Passaggio 3. Server di compilazione: Integrazione continua. Pacchetto di compilazione, Test,

Ogni volta che viene eseguito il commit di una nuova nel repository di codice di applicazione condivisa, nel server di compilazione viene attivata una nuova compilazione. Come parte del processo di integrazione continua, la compilazione deve compilare l'applicazione completamente ed eseguire test automatizzati per verificare che funzionino come previsto. Il risultato finale del processo di CI deve essere una versione nel pacchetto dell'app web, pronto per la distribuzione.

#### <a name="step-4-build-server-continuous-delivery"></a>Passaggio 4. Server di compilazione: Il recapito continuo

Una volta una compilazione come ha avuto esito positivo, il processo di CD selezionerà i prodotto degli artefatti di compilazione. Ciò comprende una web distribuire il pacchetto. Il server di compilazione verrà distribuito il pacchetto di servizio App di Azure, sostituendo qualsiasi servizio esistente con quella appena creata. In genere questo passaggio è destinato a un ambiente di gestione temporanea, ma alcune applicazioni distribuire direttamente nell'ambiente di produzione tramite un processo del CD.

#### <a name="step-5-azure-app-service-web-app"></a>Passaggio 5. Servizio App di Azure. App Web.

Una volta distribuito, l'applicazione ASP.NET Core viene eseguita all'interno del contesto di un'App Web di Azure App Service. L'App Web può essere monitorata e ulteriormente configurate tramite il portale di Azure.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Passaggio 6. Monitoraggio di produzione e di diagnostica

Mentre l'App Web è in esecuzione, è possibile monitorare l'integrità dell'applicazione e raccogliere dati sul comportamento di utente e di diagnostica. Application Insights è incluso in Visual Studio e offre strumentazione automatica per le applicazioni ASP.NET. Può fornire informazioni sull'utilizzo, eccezioni, le richieste, prestazioni e log.

## <a name="references"></a>Riferimenti

**Compilare e distribuire l'applicazione ASP.NET di base in Azure**  
<https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core>


>[!div class="step-by-step"]
[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)
