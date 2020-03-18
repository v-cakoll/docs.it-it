---
title: Processo di sviluppo per Azure
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Processo di sviluppo per Azure
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 7a641c1b6665af6e9e78ef182174b360041d74aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77450043"
---
# <a name="development-process-for-azure"></a>Processo di sviluppo per Azure

> _"Con il cloud, privati e piccole aziende possono configurare rapidamente servizi di livello professionale"._  
> _- Roy Stephan_

## <a name="vision"></a>Visione

> *Sviluppare applicazioni ASP .NET Core ben progettate nel modo desiderato usando Visual Studio o l'interfaccia della riga di comando per .NET e Visual Studio Code o l'editor preferito.*

## <a name="development-environment-for-aspnet-core-apps"></a>Ambiente di sviluppo per app ASP.NET Core

### <a name="development-tools-choices-ide-or-editor"></a>Opzioni degli strumenti di sviluppo: IDE o editor

Durante lo sviluppo di applicazioni ASP.NET Core Microsoft offre gli strumenti necessari sia che si scelga un IDE potente e completo sia che si preferisca un editor semplice e agile.

**Visual Studio 2019.** Visual Studio 2019 è l'IDE migliore per lo sviluppo di applicazioni per ASP.NET Core. Offre una serie di funzionalità che aumentano la produttività degli sviluppatori. È possibile utilizzarlo per sviluppare l'applicazione, quindi analizzarne le prestazioni e altre caratteristiche. Il debugger integrato consente di sospendere l'esecuzione del codice e di passare avanti e indietro nel codice in tempo reale durante l'esecuzione. Il test runner integrato ti consente di organizzare i test e i relativi risultati e può anche eseguire unit test dal vivo durante la codifica. Utilizzando Live Share, è possibile collaborare in tempo reale con altri sviluppatori, condividendo la sessione di codice senza problemi in rete. E quando si è pronti, Visual Studio include tutto il necessario per pubblicare l'applicazione in Azure o ovunque si potrebbe ospitarlo.

[Scarica Visual Studio 2019](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code e l'interfaccia della riga di comando per .NET** (strumenti multipiattaforma per Mac, Linux e Windows). Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Microsoft Visual Studio Code e l'interfaccia della riga di comando per .NET. Questi prodotti offrono un'esperienza semplice ed efficace che consente di ottimizzare il flusso di lavoro di sviluppo. Inoltre, Visual Studio Code supporta le estensioni per C\# e lo sviluppo Web offrendo IntelliSense e attività di collegamento all'interno dell'editor.

[Scaricare .NET Core SDK](https://dotnet.microsoft.com/download)

[Download di Visual Studio Code](https://code.visualstudio.com/download)

## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Flusso di lavoro di sviluppo per le app ASP.NET Core ospitate in Azure

Il ciclo di vita dello sviluppo applicativo inizia dal computer di ogni sviluppatore quando l'applicazione viene scritta usando il linguaggio preferito e viene testata in locale. Gli sviluppatori possono scegliere il sistema di controllo del codice sorgente preferito e possono configurare l'integrazione continua (CI) e/o il recapito/distribuzione continua (CD) usando un server di compilazione o in base alle funzionalità di Azure predefinite.

Per iniziare a sviluppare un'applicazione ASP.NET Core mediante CI/CD, è possibile usare Azure DevOps Services o Team Foundation Server (TFS) dell'organizzazione.

### <a name="initial-setup"></a>Configurazione iniziale

Per creare una pipeline di versione per l'app, è necessario avere il codice dell'applicazione nel controllo del codice sorgente. Configurare un repository locale e connetterlo a un repository remoto in un progetto team. Seguire queste istruzioni:

- [Condividere il codice con Git e Visual Studio](https://docs.microsoft.com/azure/devops/git/share-your-code-in-git-vs) oppure

- [Condividere il codice con il controllo della versione di Team Foundation e Visual Studio](https://docs.microsoft.com/azure/devops/tfvc/share-your-code-in-tfvc-vs)

Creare un servizio app di Azure in cui verrà distribuita l'applicazione. Creare un'app Web passando al pannello Servizi app nel portale di Azure. Fare clic su +Aggiungi, selezionare il modello di app Web, fare clic su Crea e specificare un nome e altri dettagli. L'app Web sarà accessibile da {name}.azurewebsites.net.

![AzureWebApp](./media/image10-2.png)

**Figure 10-1.** Creazione di una nuova app Web del servizio app di Azure nel portale di Azure.

Il processo di compilazione CI eseguirà una compilazione automatica ogni volta che viene eseguito il commit di nuovo codice nel repository di controllo del codice sorgente del progetto. Ciò consente di verificare immediatamente che il codice venga compilato (e passi i test automatizzati) e possa essere potenzialmente distribuito. Questa compilazione CI produrrà un artefatto del pacchetto di distribuzione Web e lo pubblicherà per l'utilizzo da parte del processo CD.

[Definire il processo di compilazione CI](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#ci)

Assicurarsi di abilitare l'integrazione continua in modo che il sistema accodi una compilazione ogni volta che un utente del team esegue il commit di nuovo codice. Testare la compilazione e verificare che produca un pacchetto di distribuzione Web come uno dei relativi artefatti.

Dopo aver eseguito la compilazione, il processo CD distribuirà i risultati della compilazione CI nell'app Web di Azure. Per procedere alla configurazione, creare e configurare una *Versione* che verrà distribuita nel servizio app di Azure.

[Definire il processo della versione CD](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core#cd)

Dopo aver configurato la pipeline CI/CD, è possibile effettuare aggiornamenti nell'app Web ed eseguirne il commit nel controllo del codice sorgente per distribuirli.

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>Flusso di lavoro per lo sviluppo di applicazioni ASP.NET Core ospitate in Azure

Dopo aver configurato l'account di Azure e il processo CI/CD, lo sviluppo di applicazioni ASP.NET Core ospitate in Azure è semplice. Di seguito sono riportati i passaggi di base da eseguire in genere quando si compila un'app ASP.NET Core, ospitata nel servizio app di Azure come app Web, come illustrato nella Figura 10-2.

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**Figura 10-2.** Flusso di lavoro dettagliato per la compilazione di app ASP.NET Core e l'hosting in Azure

#### <a name="step-1-local-dev-environment-inner-loop"></a>Passaggio 1. Ciclo interno dell'ambiente di sviluppo locale

Lo sviluppo di un'applicazione ASP.NET Core per la distribuzione in Azure non differisce dalla normale procedura di sviluppo dell'applicazione. Usare l'ambiente di sviluppo locale desiderato, ovvero Visual Studio 2017 o l'interfaccia della riga di comando per .NET e Visual Studio Code o l'editor preferito. È possibile scrivere codice, eseguire ed eseguire il debug delle modifiche, eseguire test automatizzati e commit locali nel controllo del codice sorgente fino a quando non si è pronti per il push delle modifiche nel repository del controllo del codice sorgente condiviso.

#### <a name="step-2-application-code-repository"></a>Passaggio 2. Repository del codice dell'applicazione

Quando si è pronti per condividere il codice con il proprio team, eseguire il push delle modifiche dal repository del codice sorgente locale al repository del codice sorgente condiviso del team. Se è stato usato un ramo personalizzato, questo passaggio prevede in genere l'unione del codice in un ramo condiviso, ad esempio per mezzo di una [richiesta pull](https://docs.microsoft.com/azure/devops/git/pull-requests).

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>Passaggio 3. Server di compilazione: integrazione continua. compilazione, test, pacchetto

Per ogni nuovo commit eseguito nel repository di codice dell'applicazione condiviso, nel server di compilazione viene attivata una nuova compilazione. Come parte del processo di integrazione continua (CI), la compilazione deve compilare l'applicazione ed eseguire test automatizzati per verificare che tutto funzioni come previsto. Il risultato finale del processo di integrazione continua deve essere una versione pacchetto dell'app Web pronta per la distribuzione.

#### <a name="step-4-build-server-continuous-delivery"></a>Passaggio 4. Server di compilazione: recapito continuo

Dopo la compilazione, il processo di recapito continuo acquisirà gli artefatti di compilazione generati. Gli artefatti includeranno un pacchetto di distribuzione Web. Il server di compilazione distribuirà il pacchetto nel servizio app di Azure, sostituendo eventuali servizi esistenti con il servizio appena creato. Sebbene questo passaggio sia in genere destinato a un ambiente di gestione temporanea, alcune applicazioni eseguono la distribuzione direttamente nell'ambiente di produzione tramite un processo CD.

#### <a name="step-5-azure-app-service-web-app"></a>Passaggio 5. App Web del servizio app di Azure

Dopo la distribuzione, l'applicazione ASP.NET Core viene eseguita all'interno del contesto di un'app Web del servizio app di Azure. L'app Web può essere monitorata e configurata tramite il portale di Azure.

#### <a name="step-6-production-monitoring-and-diagnostics"></a>Passaggio 6. Monitoraggio e diagnostica della produzione

Mentre l'app Web è in esecuzione, è possibile monitorare l'integrità dell'applicazione e raccogliere dati di diagnostica e sul comportamento degli utenti. Application Insights è incluso in Visual Studio e offre strumentazione automatica per le app ASP.NET. Application Insights può offrire informazioni sull'utilizzo, le eccezioni, le richieste, le prestazioni e i log.

## <a name="references"></a>Riferimenti

**Compilare e distribuire l'app ASP.NET Core in Azure**  
<https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core>

>[!div class="step-by-step"]
>[Successivo](test-asp-net-core-mvc-apps.md)
>[precedente](azure-hosting-recommendations-for-asp-net-web-apps.md)
