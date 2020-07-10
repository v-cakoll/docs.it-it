---
title: Introduzione ad Azure e .NET
description: Nozioni di base su Azure e .NET.
ms.date: 06/20/2020
ms.openlocfilehash: c64de800f47035b22cc62b6d08cb7b71246984a7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174322"
---
# <a name="introduction-to-azure-and-net"></a>Introduzione ad Azure e .NET

Questo documento fornisce una panoramica dei concetti chiave e dei servizi che gli sviluppatori .NET devono conoscere per iniziare a sviluppare app usando i servizi di Azure.

## <a name="key-concepts"></a>Concetti chiave

**Account Azure**: l'account Azure rappresenta le credenziali usate per accedere ai servizi di Azure, ad esempio il [portale di Azure](https://portal.azure.com) o [Cloud Shell](https://shell.azure.com). Se non si ha un account Azure, è possibile [crearne uno gratuitamente](https://azure.microsoft.com/free/dotnet/).

**Sottoscrizione di Azure**: una sottoscrizione è il piano di fatturazione nel quale vengono create le risorse di Azure. Le sottoscrizioni possono essere individuali o aziendali, gestite dall'azienda. L'account Azure può essere associato a più sottoscrizioni. In questo caso è necessario accertarsi di aver selezionato la sottoscrizione corretta quando si creano le risorse. Per altre informazioni, vedere [Informazioni sugli account, sulle sottoscrizioni e sulla fatturazione](/azure/guides/developer/azure-developer-guide#understanding-accounts-subscriptions-and-billing).

> [!TIP]
> Se è disponibile una sottoscrizione di Visual Studio, [è possibile attivare crediti Azure mensili](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/).

**Gruppo di risorse**: i gruppi di risorse rappresentano un modo per organizzare le risorse di Azure in gruppi per la gestione. Le risorse create in Azure verranno archiviate in un gruppo di risorse, operazione simile al salvataggio di un file in una cartella nel computer.

**Hosting**: per l'esecuzione in Azure, il codice deve essere ospitato in un servizio che supporti l'esecuzione di codice fornito dall'utente.

**Servizi gestiti**: Azure fornisce alcuni servizi in cui si forniscono dati o informazioni ad Azure e l'implementazione di Azure esegue l'azione appropriata. Un esempio è Archiviazione BLOB di Azure, in cui si forniscono file e Azure gestisce la lettura, la scrittura e la persistenza.

**Azure SDK per .NET**: a volte definito librerie di **Azure per .NET**, questo si riferisce collettivamente ai [pacchetti NuGet](https://www.nuget.org/profiles/azure-sdk) installati nel progetto che forniscono diverse interazioni e funzionalità con i servizi di Azure. Questi pacchetti includono anche le librerie di gestione usate per il provisioning e l'amministrazione delle risorse.

## <a name="choosing-a-hosting-option"></a>Scelta di un'opzione di hosting

L'hosting in Azure può essere suddiviso in tre categorie.

* **Infrastruttura distribuita come servizio (IaaS)**: con la tecnologia IaaS, si effettua il provisioning delle macchine virtuali necessarie insieme ai componenti di rete e di archiviazione associati. Successivamente si distribuiscono il software e le applicazioni desiderate nelle macchine virtuali. Questo modello è il più simile a un ambiente locale tradizionale, con la differenza che l'infrastruttura viene gestita da Microsoft. È comunque possibile gestire le singole macchine virtuali, compresi il sistema operativo, il software personalizzato e gli aggiornamenti della sicurezza.

* **Piattaforma distribuita come servizio (PaaS)**: il modello di piattaforma distribuita come servizio offre un ambiente di hosting gestito in cui è possibile distribuire l'applicazione senza dover gestire le macchine virtuali o le risorse di rete. Ad esempio, anziché creare singole macchine virtuali, si specifica un numero di istanze e il servizio eseguirà il provisioning, la configurazione e la gestione delle risorse necessarie. Servizio app di Azure è un esempio di servizio PaaS.
  
* **Funzioni distribuite come servizio (FaaS)**: comunemente noto come "elaborazione serverless", il modello FaaS si spinge ancora oltre rispetto al modello PaaS nell'astrarre gli aspetti che riguardano l'ambiente di hosting. Invece di creare istanze di calcolo e quindi distribuire il codice alle istanze, è sufficiente distribuire il codice e il servizio lo eseguirà automaticamente. Non è necessario amministrare le risorse di calcolo. La piattaforma ridimensiona agevolmente il codice a qualsiasi livello necessario per gestire il traffico e l'utente paga solo quando il codice è in esecuzione. Funzioni di Azure è un servizio FaaS.

In generale, più l'applicazione predilige i modelli FaaS e PaaS, maggiori sono i benefici dall'esecuzione nel cloud. Di seguito è riportato un riepilogo di tre opzioni di hosting comuni in Azure e quando sceglierle.

* [Servizio app di Azure](/azure/app-service/app-service-value-prop-what-is): se si intende ospitare un'applicazione o un servizio Web, prendere prima in considerazione il servizio app. Per un'introduzione al servizio app e alle app ASP.NET, WCF e ASP.NET Core, vedere [Creare un'app Web ASP.NET Core in Azure](/azure/app-service/app-service-web-get-started-dotnet).

* [Funzioni di Azure](/azure/azure-functions/functions-overview): Funzioni di Azure è ideale per i flussi di lavoro guidati dagli eventi. Esempi includono la risposta ai webhook, l'elaborazione degli elementi in code o archivi BLOB e i timer. Per un'introduzione a Funzioni di Azure, vedere [Creare la prima funzione con Visual Studio](/azure/azure-functions/functions-create-your-first-function-visual-studio).

* [Macchine virtuali di Azure](/azure/virtual-machines/): se il servizio app se non soddisfa le proprie esigenze di hosting di un'applicazione esistente a causa di dipendenze specifiche, le macchine virtuali rappresentano il punto di partenza più semplice. Per un'introduzione alle macchine virtuali, ad ASP.NET o WCF, vedere [Deploy an ASP.NET app to an Azure virtual machine](https://tutorials.visualstudio.com/aspnet-vm/intro) (Distribuire un'app ASP.NET in una macchina virtuale di Azure).

> [!TIP]
> Per altre informazioni sulla scelta di un servizio, vedere scelta di un [servizio di calcolo di Azure per l'applicazione](/azure/architecture/guide/technology-choices/compute-decision-tree).

## <a name="choose-a-data-storage-service"></a>Scegliere un servizio di archiviazione dati

Azure offre diversi servizi per l'archiviazione dei dati in funzione delle proprie esigenze. I servizi dati più comuni per gli sviluppatori .NET sono:

* [Database SQL di Azure](/azure/sql-database/): se si intende eseguire la migrazione di un'applicazione che usa già SQL Server nel cloud, il database SQL di Azure è il punto di partenza naturale. Per un'introduzione, vedere [Esercitazione: Creare un'app ASP.NET in Azure con un database SQL](/azure/app-service/app-service-web-tutorial-dotnet-sqldatabase).

* [Azure Cosmos DB](/azure/cosmos-db/): Azure Cosmos DB è un moderno database progettato per il cloud. Quando si crea una nuova applicazione che non ha ancora una specifica dipendenza dal database, è consigliabile prendere in considerazione Azure Cosmos DB. Azure Cosmos DB è un'ottima scelta per le nuove applicazioni Web, per dispositivi mobili, di gioco e IoT in cui scalabilità automatica, prestazioni prevedibili, tempi di risposta rapidi e la possibilità di eseguire query su dati privi di schema sono fattori importanti. Per un'introduzione, vedere [Guida introduttiva: Creare un'app Web .NET con Azure Cosmos DB usando l'API SQL e il portale di Azure](/azure/cosmos-db/create-sql-api-dotnet).

* [Archiviazione BLOB di Azure](/azure/storage/): Archiviazione BLOB di Azure è ottimizzato per l'archiviazione e il recupero di oggetti binari di grandi dimensioni, ad esempio immagini, file e flussi. Gli archivi di oggetti consentono di gestire quantità estremamente elevate di dati non strutturati. Per un'introduzione, vedere [Guida introduttiva: Usare .NET per creare un BLOB nell'archiviazione di oggetti](/azure/storage/blobs/storage-quickstart-blobs-dotnet).

> [!TIP]
> Per altre informazioni, vedere [Scegliere l'archivio dati corretto](/azure/architecture/guide/technology-choices/data-store-overview).

## <a name="connect-to-azure-services"></a>Connettersi ai servizi di Azure

Se si usa Visual Studio, è possibile aggiungere ai progetti il supporto per determinati servizi di Azure. La finestra di dialogo **Servizi connessi** in Visual Studio consente di aggiungere facilmente ai progetti il codice di connessione, le impostazioni di configurazione e tutti i riferimenti necessari. Alcuni servizi di Azure usati comunemente sono supportati per impostazione predefinita, ad esempio [Archiviazione](/azure/vs-azure-tools-connected-services-storage), l'autenticazione di [Azure Active Directory](/azure/active-directory/develop/vs-active-directory-add-connected-service), [Azure Key Vault](/azure/key-vault/vs-key-vault-add-connected-service) e [Servizi cognitivi](/azure/cognitive-services/) come [Visione artificiale](/azure/cognitive-services/computer-vision/vs-computer-vision-connected-service). Altri servizi, tra cui servizi di terze parti, sono disponibili come estensioni in [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?term=connected%20service&target=VS&category=Tools&vsVersion=&subCategory=All&sortBy=Relevance).

## <a name="using-the-azure-sdk-for-net"></a>Uso di Azure SDK per .NET

Se si usa Azure SDK per .NET per accedere o gestire le risorse di Azure, tenere presente quanto segue:

* **Autenticazione**: molte librerie nell'SDK usano un'infrastruttura di autenticazione comune, mentre alcune librerie usano meccanismi di autenticazione specifici per il servizio che stanno consumando. Per altre informazioni, vedere [autenticazione con Azure SDK per .NET](authentication.md).
* **Registrazione**: se supportata, le librerie client includono la possibilità di registrare le operazioni della libreria client. Per altre informazioni, vedere [registrazione con Azure SDK per .NET](logging.md).
* **API REST**: Azure SDK per .NET è un'astrazione basata sull' [API REST di Azure](/rest/api/azure/). Se lo si desidera, l'API REST di Azure può essere usata invece di o insieme a Azure SDK per .NET.

## <a name="diagnosing-problems-in-the-cloud"></a>Diagnosi dei problemi nel cloud
Dopo aver distribuito l'applicazione in Azure, potrebbero verificarsi casi in cui l'applicazione funziona nell'ambiente di sviluppo, ma non in Azure. Di seguito sono indicati due buoni punti di partenza per la diagnosi dei problemi:

* **Debug remoto da Visual Studio**: la maggior parte dei servizi di calcolo di Azure, inclusi quelli trattati in questo documento, supporta il debug remoto con Visual Studio e l'acquisizione di log. Per esplorare le funzionalità di Visual Studio con l'applicazione, aprire la finestra dello strumento Cloud Explorer digitando 'Cloud Explorer' nella barra degli strumenti di avvio veloce di Visual Studio (nell'angolo in alto a destra), quindi individuare l'applicazione nella struttura ad albero. Per informazioni dettagliate, vedere [Risoluzione dei problemi di un'app Web nel servizio app di Azure tramite Visual Studio](/azure/app-service/web-sites-dotnet-troubleshoot-visual-studio#remotedebug).

* **Application Insights**: [Application Insights](/azure/application-insights/) è una soluzione completa di monitoraggio delle prestazioni applicative (Application Performance Monitoring, APM) che acquisisce automaticamente i dati diagnostici, di telemetria e delle prestazioni dalle applicazioni. Per un'introduzione alla raccolta di dati di diagnostica per l'app, vedere [Iniziare a monitorare l'applicazione Web ASP.NET](/azure/application-insights/quick-monitor-portal).

## <a name="next-steps"></a>Passaggi successivi

* [Distribuire la prima app Web ASP.NET Core in Azure](/azure/app-service/app-service-web-get-started-dotnet)
* [Informazioni sull'autenticazione in Azure SDK per .NET](authentication.md)
* [Diagnosticare gli errori nelle app cloud](https://devblogs.microsoft.com/aspnet/diagnosing-errors-on-your-cloud-apps/)
* Scaricare l'e-book gratuito [Guida introduttiva ad Azure per sviluppatori .NET](https://www.microsoft.com/net/download/thank-you/azure-quick-start-ebook)
