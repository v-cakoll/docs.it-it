---
title: Applicazioni monolitiche containerizing
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Applicazioni monolitiche containerizing
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 11e2c24403b9b61584e424696c844e00e5d34b03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="containerizing-monolithic-applications"></a>Applicazioni monolitiche containerizing

Si potrebbe voler creare applicazione web distribuito monolithically singolo o un servizio e distribuirlo come un contenitore. L'applicazione potrebbe non essere internamente monolitico, ma strutturato da diverse librerie, componenti o livelli anche (livello di applicazione, il livello di dominio, il livello di accesso ai dati e così via). Esternamente, tuttavia, è un singolo contenitore, un singolo processo, una singola applicazione web o un singolo servizio.

Per gestire questo modello, si distribuisce un singolo contenitore per rappresentare l'applicazione. Per applicare la scalabilità verticale, è sufficiente aggiungere più copie con un bilanciamento del carico in primo piano. La semplicità proviene da un'unica distribuzione in un singolo contenitore o di una macchina virtuale di gestione.

![](./media/image1.png)

**Figura 4-1**. Esempio dell'architettura di un'applicazione monolitica nei contenitori

È possibile includere più componenti, librerie o livelli interni in ogni contenitore, come illustrato nella figura 4-1. Tuttavia, questo modello monolitico potrebbe essere in conflitto con il principio di contenitore "un contenitore consente di eseguire un'operazione e non un processo", ma potrebbe essere adatta per alcuni casi.

Lo svantaggio di questo approccio diventa evidente se si estende l'applicazione, che li richiede di scala. Se è possibile ridimensionare l'intera applicazione, non è effettivamente un problema. Tuttavia, nella maggior parte dei casi, solo alcune parti dell'applicazione sono i punti di riduzione che richiedono scalabilità, mentre gli altri componenti sono utilizzate minore.

Ad esempio, in un'applicazione di e-commerce tipico, è probabilmente necessario ridimensionare il sottosistema di informazioni di prodotto, poiché molti clienti più sfogliare i prodotti di acquistare le licenze. Numero di clienti Usa carrello di utilizzare la pipeline di pagamento. I clienti meno aggiungono commenti o visualizzarne la cronologia di acquisto. E potrebbe essere un numero limitato di dipendenti, che devono gestire il contenuto e le campagne di marketing. Se si modifica la scala progettazione monolitica, tutto il codice per le diverse attività viene distribuito più volte e scala in stesso grado.

Esistono diversi modi per scalare un'applicazione, la duplicazione orizzontale diverse aree di dati dell'applicazione e partizionamento concetti simili di business o di divisione. Tuttavia, oltre il problema di scalabilità di tutti i componenti, le modifiche apportate a un singolo componente richiedono completa la riesecuzione del test dell'intera applicazione e una ridistribuzione completa di tutte le istanze.

Tuttavia, l'approccio monolitico è comune, in quanto lo sviluppo dell'applicazione è più semplice per gli approcci di microservizi inizialmente. Di conseguenza, molte organizzazioni sviluppano utilizzando questo approccio architetturale. Sebbene in alcune organizzazioni hanno buone risultati insufficienti, altri raggiunge i limiti. Molte organizzazioni progettavano le applicazioni utilizzando questo modello perché gli strumenti e l'infrastruttura rendeva troppo difficile per compilare un servizio architetture orientate ai (servizi SOA), anni e non visualizzano la necessità, fino a quando l'applicazione aumento delle dimensioni.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dello stesso host e dispone di un rapporto accettabile di efficienza di utilizzo di risorse, come illustrato nella figura 4-2.

![](./media/image2.png)

**Figura 4-2**. Approccio monolitico: Host che esegue più applicazioni, ciascuna applicazione in esecuzione come un contenitore

Applicazioni monolitiche in Microsoft Azure possono essere distribuite utilizzando macchine virtuali dedicate per ogni istanza. Inoltre, l'uso [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile ridimensionare le macchine virtuali. [Servizio App di Azure](https://azure.microsoft.com/services/app-service/) può anche eseguire applicazioni monolitiche e scalare facilmente istanze senza che sia necessario gestire le macchine virtuali. A partire da 2016, servizi di App di Azure può eseguito singole istanze di contenitori di Docker, nonché semplificando la distribuzione.

Come un ambiente QA o un ambiente di produzione limitato, è possibile distribuire un host Docker più macchine virtuali e bilanciare mediante il servizio di bilanciamento Azure, come illustrato nella figura 4-3. Ciò consente di gestire la scalabilità con un approccio con granularità grossolana, poiché l'intera applicazione risiede all'interno di un singolo contenitore.

![](./media/image3.png)

**Figura 4-3**. Esempio di più host, la scalabilità dell'applicazione di un singolo contenitore

Distribuzione di host diversi può essere gestita con le tecniche tradizionali di distribuzione. Host docker possono essere gestiti con comandi come `docker run` o `docker-compose` eseguiti manualmente o tramite l'automazione, ad esempio le pipeline di recapito continuo (CD).

## <a name="deploying-a-monolithic-application-as-a-container"></a>Distribuzione di un'applicazione monolitica come un contenitore

Esistono vantaggi derivanti dall'utilizzo di contenitori per gestire le distribuzioni applicazione monolitico. La scalabilità di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche se si utilizza il set di scalabilità di macchine Virtuali, le macchine virtuali richiedere ora di inizio. Quando viene distribuita come le istanze dell'applicazione tradizionale anziché contenitori, la configurazione dell'applicazione viene gestita come parte della macchina virtuale, che non è ideale.

Distribuzione degli aggiornamenti, come immagini Docker è molto più veloce e rete efficiente. Le immagini docker iniziano in genere espresso in secondi, velocizzando le implementazioni. Chiudere un'istanza di immagine di Docker è facile come emittente un `docker stop` comandi e in genere viene completato in meno di un secondo.

Poiché i contenitori sono modificabili in base alla progettazione, è non necessario mai preoccuparsi di macchine virtuali danneggiate. Al contrario, gli script di aggiornamento per una macchina virtuale abbia dimenticato di account per alcuni specifici file di configurazione o su disco.

Mentre monolitiche applicazioni possono trarre vantaggio da Docker, ci stiamo tocca solo sui vantaggi. Vantaggi aggiuntivi di gestione dei contenitori provengono dalla distribuzione con orchestrators contenitore, gestire le varie istanze e ciclo di vita di ogni istanza del contenitore. L'interruzione dell'applicazione monolitica in sottosistemi che possono essere ridimensionate, sviluppato e distribuito singolarmente è il punto di ingresso nell'area di autenticazione di microservizi.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Pubblicazione di un'applicazione basato su singolo contenitore al servizio App di Azure

Se si desidera ottenere la convalida di un contenitore distribuito in Azure o quando un'applicazione è semplicemente un'applicazione contenitore di singolo servizio App di Azure fornisce un ottimo modo per fornire servizi scalabili basato su singolo contenitore. Utilizzo del servizio App di Azure è semplice. Fornisce integrazione ottima con Git per renderlo più facile eseguire il codice, compilazione in Visual Studio e distribuirlo direttamente in Azure.

![](./media/image4.png)

**Figura 4-4**. Pubblicazione di un'applicazione single-container al servizio App di Azure da Visual Studio

Senza Docker, se sono necessarie altre funzionalità, Framework o le dipendenze che non sono supportate in Azure App Service, era necessario attendere che il team di Azure aggiornate di tali dipendenze nel servizio App. O era necessario passare ad altri servizi come Azure Service Fabric, servizi Cloud di Azure o anche le macchine virtuali, in cui è stato ulteriormente controllo ed è possibile installare un componente richiesto o un framework per l'applicazione.

Supporto contenitore in Visual Studio 2017 offre la possibilità di includere desiderato nell'ambiente dell'applicazione, come illustrato nella figura 4-4. Poiché si sta eseguendo in un contenitore, se si aggiunge una dipendenza all'applicazione, è possibile includere la dipendenza nell'immagine del Dockerfile o Docker.

Come anche illustrata nella figura 4-4, il flusso di pubblicazione inserisce un'immagine tramite un registro di sistema del contenitore. Può trattarsi di qualsiasi altro Docker Registro di sistema come Hub Docker oppure un registro di sistema locale o del contenitore Azure (un registro di sistema su Chiudi per le distribuzioni in Azure e protetto dall'account e gruppi di Azure Active Directory).


>[!div class="step-by-step"]
[Precedente] [Avanti] (docker applicazione-stato data.md) (index.md)
