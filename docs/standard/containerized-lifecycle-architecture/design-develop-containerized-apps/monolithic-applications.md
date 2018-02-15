---
title: Applicazioni monolitiche
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 95561aaa8ffccb8eae3fe276192c6648c0819685
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="monolithic-applications"></a>Applicazioni monolitiche

In questo scenario, la compilazione di un'applicazione web unico e monolitico o un servizio e distribuirlo come un contenitore. All'interno dell'applicazione, la struttura potrebbe non essere monolitica; è possibile costituiscono diverse librerie, componenti o livelli anche (livello di applicazione, il livello di dominio, il livello di accesso ai dati e così via). Esternamente, si tratta di un singolo contenitore, ad esempio un singolo processo, una singola applicazione web o un servizio singolo.

Per gestire questo modello, si distribuisce un singolo contenitore per rappresentare l'applicazione. La scalabilità sufficiente aggiungere alcune altre copie con un bilanciamento del carico in primo piano. La semplicità proviene da un'unica distribuzione in un singolo contenitore o di una macchina virtuale (VM) di gestione.

In seguito l'entità che consente di eseguire un'operazione solo un contenitore e opera in un unico processo, il modello monolitico è in conflitto. È possibile includere più componenti/librerie o interni livelli all'interno di ogni contenitore, come illustrato nella figura 4-1.

![](./media/image1.png)

Figura 4-1: esempio di architettura dell'applicazione monolitico

Lo svantaggio di questo approccio viene fornito se o quando si espande l'applicazione, che li richiede di scala. Se l'intera applicazione ridimensionata, non è effettivamente un problema. Tuttavia, nella maggior parte dei casi, alcune parti dell'applicazione sono i punti di riduzione che richiedono scalabilità, mentre altri componenti sono utilizzati meno.

Utilizzando l'esempio tipico di e-commerce, è probabile che sia necessario è ridimensionare il componente di informazioni di prodotto. Molti clienti più sfogliare i prodotti di acquistare le licenze. Numero di clienti Usa carrello di utilizzare la pipeline di pagamento. I clienti meno aggiungono commenti o visualizzarne la cronologia di acquisto. E probabilmente necessario solo un numero limitato di dipendenti, in un'area singola, che devono gestire il contenuto e le campagne di marketing. Per la progettazione monolitica la scala, tutto il codice viene distribuito più volte.

Oltre alla "scalabilità-tutti gli elementi" problema, le modifiche a un singolo componente richiedono completa la riesecuzione del test dell'intera applicazione, nonché una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni sono lo sviluppo con questo metodo dell'architettura. Molti usufruisci buono sufficiente risultati, mentre altri limiti di verifica. Molti progettati le applicazioni in questo modello perché gli strumenti e l'infrastruttura sono troppo difficili da creare architetture SOA e non visualizzano la necessità, fino a quando l'app aumento delle dimensioni.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dello stesso host e dispone di un rapporto accettabile di efficienza sull'utilizzo delle risorse, come illustrato nella figura 4-2.

![](./media/image2.png)

Figura 4-2: un host che esegue più applicazioni/contenitori

È possibile distribuire applicazioni monolitiche in Azure utilizzando macchine virtuali dedicate per ogni istanza. Utilizzando [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile scalare facilmente le macchine virtuali. [Servizi App Azure](https://azure.microsoft.com/en-us/services/app-service/) possono eseguire applicazioni monolitiche e scalare facilmente istanze senza la necessità di gestire le macchine virtuali. A partire da 2016, servizi di App di Azure può eseguito singole istanze di contenitori di Docker, nonché semplificando la distribuzione. E, usando Docker, è possibile distribuire una singola macchina virtuale come host Docker ed eseguire più istanze. Tramite il bilanciamento di Azure, come illustrato nella figura 4-3, è possibile gestire la scalabilità.

![](./media/image3.png)

Figura 4-3: più host scalabilità una singola applicazione App/contenitori di Docker

È possibile gestire la distribuzione di vari host tramite le tecniche tradizionali di distribuzione. È possibile gestire gli host Docker, utilizzando comandi quali `docker run` manualmente, tramite l'automazione, ad esempio le pipeline di recapito continuo (CD), cui viene descritto più avanti in questo e-book.

## <a name="monolithic-application-deployed-as-a-container"></a>Qualsiasi applicazione distribuita come contenitore

Esistono vantaggi derivanti dall'utilizzo di contenitori per gestire le distribuzioni monolitiche. Le istanze di contenitori di ridimensionamento è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche se il set di scalabilità di macchine Virtuali sono un'ottima funzionalità di scalabilità di macchine virtuali, che sono necessari per ospitare i contenitori di Docker, hanno durata per la configurazione. Quando viene distribuita come istanze dell'applicazione, la configurazione dell'app viene gestita come parte della macchina virtuale.

Distribuzione degli aggiornamenti, come immagini Docker è molto più veloce e rete efficiente. Le istanze Vn da impostare per gli host stesso come le istanze di Vn-1, eliminando i costi e risultanti da altre macchine virtuali. Le immagini docker iniziano in genere espresso in secondi, velocizzando l'implementazione. Chiudere un'istanza di Docker è facile come richiamare il `docker stop` comando, in genere completato in meno di un secondo.

Poiché i contenitori sono intrinsecamente non modificabili, in base alla progettazione, è non necessario mai preoccuparsi di macchine virtuali danneggiate perché non è stato uno script di aggiornamento tenere conto per alcuni specifici file di configurazione o su disco.

Anche se le app monolitiche possono trarre vantaggio da Docker, ci stiamo tocca su solo i suggerimenti dei vantaggi. I maggiori vantaggi della gestione di contenitori proviene dalla distribuzione con orchestrators contenitore che gestiscono le varie istanze e ciclo di vita di ogni istanza del contenitore. L'interruzione dell'applicazione monolitica in sottosistemi che possono essere ridimensionate, sviluppato e distribuito singolarmente è il punto di ingresso nell'area di autenticazione di microservizi.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>La pubblicazione di una singola app contenitore Docker in Azure App Service

Sia perché si desidera ottenere una rapida convalida di un contenitore distribuito in Azure o l'app è semplicemente un'app singolo contenitore, servizi di App di Azure fornisce un ottimo modo per fornire servizi singolo contenitore scalabili.

L'utilizzo di servizio App di Azure è intuitiva e la possibilità di rendere in esecuzione e rapidamente perché offre grande Git integration per rendere il codice, compilarlo in Microsoft Visual Studio, distribuirlo direttamente in Azure. Ma, in genere (con nessun Docker), se sono necessarie altre funzionalità, un framework o le dipendenze che non sono supportate in servizi di App, è necessario attendere fino a quando il team di Azure aggiorna tali dipendenze nel servizio App o passato ad altri servizi come Service Fabric, servizi Cloud o macchine virtuali anche normale, per cui si dispone di ulteriore controllo e può installare un componente obbligatorio o un framework per l'applicazione.

A questo punto, tuttavia, (annunciati in Microsoft Connect 2016 nel novembre 2016) e come illustrato nella figura 4‑4, quando si utilizza Visual Studio 2017, supporto contenitore nel servizio App di Azure offre la possibilità di includere desiderato nell'ambiente di app. Se una dipendenza è stato aggiunto all'app, perché sono in esecuzione in un contenitore, si ottiene la funzionalità di tali dipendenze incluse nell'immagine del Dockerfile o Docker.

![](./media/image4.png)

Figura 4-4: pubblicare un contenitore di servizio App di Azure da Visual Studio. app/contenitori

Figura 4-4 mostra anche che il flusso di pubblicazione inserisce un'immagine tramite un contenitore del Registro di sistema, che può essere il Registro di sistema contenitore di Azure (un registro di sistema vicino alle distribuzioni in Azure e protetto dall'account e gruppi di Azure Active Directory) o qualsiasi altro Docker del Registro di sistema ad esempio i registri di Hub Docker oppure in locale.


>[!div class="step-by-step"]
[Previous] (common-container-design-principles.md) [Next] (state-and-data-in-docker-applications.md)
