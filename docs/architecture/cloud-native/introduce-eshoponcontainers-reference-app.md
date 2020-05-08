---
title: Introduzione all'app di riferimento per eShopOnContainers
description: Introduzione all'app di riferimento per i microservizi nativi del cloud eShopOnContainers per ASP.NET Core e Azure.
ms.date: 06/30/2019
ms.openlocfilehash: 8d4ad982716a07613ebbef6668afab69d5a8b4f6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895533"
---
# <a name="introducing-eshoponcontainers-reference-app"></a>Introduzione all'app di riferimento per eShopOnContainers

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Microsoft, in collaborazione con gli esperti della community leader, ha prodotto un'applicazione di riferimento per microservizi nativa del cloud completa, eShopOnContainers. Questa applicazione è stata creata per presentare l'uso di .NET Core e Docker e, facoltativamente, di Azure, Kubernetes e Visual Studio, per creare una vetrina online.

![Schermata dell'app di esempio eShopOnContainers.](./media/eshoponcontainers-sample-app-screenshot.png)

**Figura 2-1**. Schermata dell'app di esempio eShopOnContainers.

Prima di iniziare questo capitolo, è consigliabile scaricare l' [applicazione di riferimento eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers). In tal caso, dovrebbe essere più semplice proseguire con le informazioni presentate.

## <a name="features-and-requirements"></a>Funzionalità e requisiti

Iniziamo con una verifica delle funzionalità e dei requisiti dell'applicazione. L'applicazione eShopOnContainers rappresenta uno Store online che vende vari prodotti fisici, ad esempio magliette e tazze da caffè. Se in precedenza è stato acquistato qualcosa online, l'esperienza di utilizzo dello Store dovrebbe essere relativamente familiare. Di seguito sono riportate alcune delle funzionalità di base implementate dallo Store:

- Elencare gli elementi del catalogo
- Filtra elementi per tipo
- Filtra elementi per marchio
- Aggiungere elementi al carrello acquisti
- Modificare o rimuovere elementi dal Cestino
- Checkout
- Registrare un account
- Accesso
- Disconnessione
- Verifica ordini

L'applicazione presenta anche i requisiti non funzionali seguenti:

- Deve essere a disponibilità elevata e deve essere ridimensionato automaticamente per soddisfare un aumento del traffico (e la riduzione delle prestazioni di una volta al traffico).
- Deve fornire un monitoraggio facile da usare dei log di diagnostica e di integrità per facilitare la risoluzione di eventuali problemi riscontrati.
- Deve supportare un processo di sviluppo agile, incluso il supporto per l'integrazione e la distribuzione continue (CI/CD).
- Oltre ai due front-end Web (applicazione tradizionale e a pagina singola), l'applicazione deve supportare anche le app client per dispositivi mobili che eseguono diversi tipi di sistemi operativi.
- Deve supportare l'hosting multipiattaforma e lo sviluppo multipiattaforma.

![architettura di sviluppo dell'applicazione di riferimento eShopOnContainers.](./media/eshoponcontainers-development-architecture.png)

**Figura 2-2**. architettura di sviluppo dell'applicazione di riferimento eShopOnContainers.

L'applicazione eShopOnContainers è accessibile da client Web o per dispositivi mobili che accedono all'applicazione tramite HTTPS destinata all'applicazione server MVC ASP.NET Core o a un gateway API appropriato. I gateway API offrono diversi vantaggi, ad esempio la separazione dei servizi back-end dai singoli client front-end e la migliore sicurezza. L'applicazione usa anche un modello correlato noto come backend per i front-end (BFF), che consiglia di creare gateway API distinti per ogni client front-end. L'architettura di riferimento Mostra come suddividere i gateway API a seconda che la richiesta provenga da un client Web o per dispositivi mobili.

La funzionalità dell'applicazione è suddivisa in diversi microservizi distinti. Sono disponibili servizi responsabili dell'autenticazione e dell'identità, che elencano gli articoli del catalogo dei prodotti, gestiscono gli acquisti degli utenti e impostano ordini. Ognuno di questi servizi distinti dispone di un proprio archivio permanente. Si noti che non esiste un singolo archivio dati master con cui tutti i servizi interagiscono. Al contrario, il coordinamento e la comunicazione tra i servizi vengono eseguiti in base alle esigenze e tramite l'uso di un bus di messaggi.

Ognuno dei diversi microservizi è progettato in modo diverso in base ai singoli requisiti. Questo significa che lo stack di tecnologie potrebbe variare, anche se tutti sono compilati con .NET Core e progettati per il cloud. I servizi più semplici forniscono l'accesso CRUD (create-Read-Update-Delete) di base agli archivi dati sottostanti, mentre i servizi più avanzati usano approcci e modelli di progettazione basati su dominio per gestire la complessità aziendale.

![Tipi diversi di microservizi](./media/different-kinds-of-microservices.png)

**Figura 2-3**. Tipi diversi di microservizi.

## <a name="overview-of-the-code"></a>Panoramica del codice

Poiché sfrutta i microservizi, l'app eShopOnContainers include alcuni progetti e soluzioni distinti nel repository GitHub. Oltre a separare le soluzioni e i file eseguibili, i vari servizi sono progettati per l'esecuzione all'interno dei propri contenitori, sia durante lo sviluppo locale che in fase di esecuzione nell'ambiente di produzione. Nella figura 2-4 è illustrata la soluzione completa di Visual Studio, in cui sono organizzati i diversi progetti.

![Progetti nella soluzione Visual Studio.](./media/projects-in-visual-studio-solution.png)

**Figura 2-4**. Progetti nella soluzione Visual Studio.

Il codice è organizzato per supportare i diversi microservizi e, all'interno di ogni microservizio, il codice viene suddiviso in logica di dominio, problemi di infrastruttura e interfaccia utente o endpoint di servizio. In molti casi, le dipendenze di ogni servizio possono essere soddisfatte dai servizi di Azure nell'ambiente di produzione, nonché da opzioni alternative per lo sviluppo locale. Esaminiamo il modo in cui i requisiti dell'applicazione vengono mappati ai servizi di Azure.

## <a name="understanding-microservices"></a>Informazioni sui microservizi

Questo libro è incentrato sulle applicazioni native del cloud create con la tecnologia Azure. Per altre informazioni sulle procedure consigliate per i microservizi e su come progettare applicazioni basate su microservizi, vedere il libro complementare, [microservizi .NET: architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

>[!div class="step-by-step"]
>[Precedente](candidate-apps.md)
>[successivo](map-eshoponcontainers-azure-services.md)
