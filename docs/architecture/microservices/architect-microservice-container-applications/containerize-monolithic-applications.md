---
title: Inserimento di applicazioni monolitiche nei contenitori
description: L'inserimento di applicazioni monolitiche nei contenitori, anche se non consente di usufruire di tutti i vantaggi dell'architettura dei microservizi, offre fin dall'inizio vantaggi notevoli per la distribuzione.
ms.date: 01/30/2020
ms.openlocfilehash: 0e6f7504a91d2b1a89193471746168fc34f50956
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503276"
---
# <a name="containerizing-monolithic-applications"></a>Inserimento di applicazioni monolitiche nei contenitori

Può essere utile creare una singola applicazione o un singolo servizio Web con distribuzione monolitica e distribuirli come contenitore. L'applicazione stessa potrebbe non essere internamente monolitica, ma strutturata come diverse librerie, componenti o persino livelli (livello dell'applicazione, livello di accesso ai dati, ecc.). Esternamente, però, si tratta di un singolo contenitore, cioè di un singolo processo, di una singola applicazione Web o di un singolo servizio.

Per gestire questo modello, distribuire un singolo contenitore per rappresentare l'applicazione. Per aumentare la capacità, è possibile aumentare il numero di istanze, in altre parole, è sufficiente aggiungere altre copie con un servizio di bilanciamento del carico al di sopra di queste. La semplicità deriva dalla gestione di un'unica distribuzione in un singolo contenitore o una singola macchina virtuale.

![Diagramma che mostra i componenti di un'applicazione containerizzata monolitica.](./media/containerize-monolithic-applications/monolithic-containerized-application.png)

**Figura 4-1**. Esempio dell'architettura di un'applicazione monolitica inclusa in contenitori

È possibile includere più componenti, librerie o livelli interni in ogni contenitore, come illustrato nella figura 4-1. Un'applicazione containerizzata monolitica ha la maggior parte delle sue funzionalità all'interno di un singolo contenitore, con livelli o librerie interne, e scala orizzontalmente clonando il contenitore in più server/VM. Questo schema monolitico è in conflitto con il principio secondo il quale un contenitore esegue una sola operazione in un unico processo, ma in alcuni casi può comunque essere adatto.

Lo svantaggio di questo approccio diventa evidente con l'eventuale crescita dell'applicazione, che ne richiede la scalabilità. Se è possibile ridimensionare l'intera applicazione, questo non rappresenta un problema. Tuttavia, nella maggior parte dei casi, solo alcune parti dell'applicazione rappresentano colli di bottiglia che richiedono il ridimensionamento, mentre altri componenti vengono usati di meno.

Ad esempio, in una tipica applicazione di e-commerce, potrebbe essere necessario ridimensionare il sottosistema delle informazioni sul prodotto, perché molti più clienti danno un'occhiata ai prodotti prima di acquistarli. Molti più clienti usano il carrello per poi usare la pipeline di pagamento, meno clienti aggiungono commenti o visualizzano la cronologia degli acquisti. E potresti avere solo una manciata di dipendenti che hanno bisogno di gestire i contenuti e le campagne di marketing. Se si modifica la scala della progettazione monolitica, tutto il codice per le diverse attività viene distribuito più volte e scalato allo stesso grado.

Esistono diversi modi per ridimensionare un'applicazione: duplicazione orizzontale, suddivisione di aree diverse dell'applicazione e partizionamento di concetti o dati aziendali simili. Tuttavia, oltre al problema di ridimensionamento di tutti i componenti, le modifiche apportate a un singolo componente richiedono la completa riesecuzione del test dell'intera applicazione e una ridistribuzione completa di tutte le istanze.

Tuttavia, l'approccio monolitico è comune, perché lo sviluppo dell'applicazione è inizialmente più semplice rispetto agli approcci ai microservizi. Di conseguenza, molte organizzazioni sviluppano applicazioni usando questo approccio architetturale. Nonostante alcune organizzazioni abbiano ottenuto risultati sufficienti, altre raggiungeranno ben presto i limiti prefissati. Anni fa, molte organizzazioni progettavano le proprie applicazioni usando questo modello, perché con gli strumenti e l'infrastruttura a loro disposizione era troppo difficile creare architetture orientate ai servizi, e quindi non ne vedevano la necessità fino a quando le dimensioni dell'applicazione non aumentavano.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dello stesso host e mostrare un rapporto accettabile di efficienza nell'utilizzo di risorse, come illustrato nella figura 4-2.

![Diagramma che mostra un host che esegue molte app nei contenitori.](./media/containerize-monolithic-applications/host-multiple-apps-containers.png)

**Figura 4-2**. Approccio monolitico: Host che esegue più applicazioni, ciascuna delle quali in esecuzione come contenitore

Le applicazioni monolitiche in Microsoft Azure possono essere distribuite usando macchine virtuali dedicate per ogni istanza. Con i [set di scalabilità di macchine virtuali di Microsoft Azure](https://azure.microsoft.com/documentation/services/virtual-machine-scale-sets/) è anche possibile ridimensionare facilmente le macchine virtuali. Anche il [Servizio app di Azure](https://azure.microsoft.com/services/app-service/) può eseguire applicazioni monolitiche e scalare facilmente le istanze senza la necessità di gestire le macchine virtuali. Dal 2016, i Servizi app di Azure possono eseguire anche singole istanze di contenitori Docker, semplificando la distribuzione.

In un ambiente di controllo di qualità o ambiente di produzione limitato, è possibile distribuire più macchine virtuali host Docker e bilanciarle usando il bilanciamento del carico di Azure, come illustrato in figura 4-3. Ciò consente di gestire il ridimensionamento con un approccio con granularità grossolana, perché l'intera applicazione risiede all'interno di un singolo contenitore.

![Diagramma che mostra diversi host che eseguono i contenitori di app monolitici.](./media/containerize-monolithic-applications/docker-infrastructure-monolithic-application.png)

**Figura 4-3**. Esempio di più host che scalano verticalmente una singola applicazione contenitore

La distribuzione ai vari host può essere gestita con le tecniche di distribuzione tradizionali. Gli host Docker possono essere gestiti con comandi come `docker run` o `docker-compose` eseguiti manualmente o con l'automazione, ad esempio le pipeline di recapito continuo (CD).

## <a name="deploying-a-monolithic-application-as-a-container"></a>Distribuzione di un'applicazione monolitica come contenitore

Esistono vantaggi derivanti dall'uso di contenitori per gestire le distribuzioni di applicazioni monolitiche. Il ridimensionamento di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche se si usano set di scalabilità di macchine virtuali, l'avvio delle macchine virtuali richiede tempo. Quando l'applicazione viene distribuita sotto forma di istanze tradizionali anziché in contenitori, la sua configurazione viene gestita come parte della configurazione della macchina virtuale, il che non rappresenta una condizione ideale.

La distribuzione degli aggiornamenti come immagini Docker è molto più veloce ed efficiente per la rete. Le immagini Docker si avviano in genere in pochi secondi, velocizzando le implementazioni. Per chiudere un'istanza di un'immagine Docker è sufficiente emettere un comando `docker stop`, che in l'operazione viene completata in meno di un secondo.

Dal momento che, in base alle caratteristiche progettuali, i contenitori non sono modificabili, non è mai necessario preoccuparsi delle macchine virtuali danneggiate. Al contrario, gli script di aggiornamento per una macchina virtuale potrebbero dimenticare di tenere conto di alcune configurazioni specifiche o alcuni file disponibili su disco.

Le applicazioni monolitiche possano trarre vantaggio da Docker, ma in questo articolo i vantaggi vengono trattati solo in modo rapido. Altri vantaggi della gestione dei contenitori derivano dalla distribuzione con agenti di orchestrazione del contenitore, che gestiscono le varie istanze e il ciclo di vita di ciascuna istanza di contenitore. La suddivisione dell'applicazione monolitica in sottosistemi scalabili, sviluppabili e distribuibili a livello individuale è il punto di ingresso al campo dei microservizi.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Pubblicazione di un'applicazione basata su un singolo contenitore nel Servizio App di Azure

Se si vuole ottenere la convalida di un contenitore distribuito in Azure o quando un'applicazione è semplicemente un'applicazione a un solo contenitore, il Servizio app di Azure offre un ottimo modo per fornire servizi scalabili basati su un singolo contenitore. L'uso del Servizio app di Azure è semplice e offre un'ottima integrazione con Git per semplificare la creazione del codice in Visual Studio e la sua distribuzione diretta in Azure.

![Screenshot della finestra di dialogo Crea servizio app che mostra un Registro di sistema del contenitore.](./media/containerize-monolithic-applications/publish-azure-app-service-container.png)

**Figura 4-4**. Pubblicazione di un'applicazione a contenitore singolo nel servizio app di Azure da Visual Studio 2019Publishing a single-container application to Azure App Service from Visual Studio 2019

Senza Docker, se erano necessari altri framework, funzionalità o dipendenze non supportati nel Servizio app di Azure, bisognava attendere che il team di Azure aggiornasse tali dipendenze nel Servizio app. In alternativa, si doveva passare ad altri servizi come Servizi cloud di Azure o macchine virtuali, in cui si otteneva un ulteriore controllo ed era possibile installare un componente o un framework richiesto per l'applicazione.

Il supporto dei contenitori in Visual Studio 2017 e versioni successive offre la possibilità di includere ciò che si vuole nell'ambiente dell'applicazione, come illustrato in figura 4-4. Dal momento che l'esecuzione avviene in un contenitore, se si aggiunge una dipendenza all'applicazione, è possibile includere tale dipendenza nel Dockerfile o nell'immagine Docker.

Come illustrato anche nella figura 4-4, il flusso di pubblicazione esegue il push di un'immagine con un registro contenitori. Può trattarsi del Registro Azure Container (un registro vicino alle distribuzioni in Azure e protetto dai gruppi e dagli account di Azure Active Directory) oppure di qualsiasi altro registro di Docker, come l'hub Docker o un registro locale.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](docker-application-state-data.md)
