---
title: Applicazioni monolitiche
description: Comprendere i concetti di base per l'inserimento di applicazioni monolitiche nei contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: e577f9a8d9ce4f9d2c8180318b1df181db730e2f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641308"
---
# <a name="monolithic-applications"></a>Applicazioni monolitiche

In questo scenario, si sta compila un'applicazione web monolitica e singolo o un servizio e distribuirlo come un contenitore. All'interno dell'applicazione, la struttura potrebbe non essere monolitica; può comprendere diverse librerie, componenti o persino livelli (livello dell'applicazione, livello di dominio, il livello di accesso ai dati e così via). Esternamente, è un singolo contenitore, come un singolo processo, singola applicazione web o servizio singolo.

Per gestire questo modello, distribuire un singolo contenitore per rappresentare l'applicazione. Per la scalabilità, è sufficiente aggiungere alcune altre copie con un bilanciamento del carico in primo piano. La semplicità deriva dalla gestione di un'unica distribuzione in un singolo contenitore o una macchina virtuale (VM).

In seguito l'entità che esegue un'operazione solo un contenitore e lo fa in un unico processo, lo schema monolitico è in conflitto. È possibile includere più componenti/librerie o livelli interni in ogni contenitore, come illustrato nella figura 4-1.

![Dispone di un'app monolitica tutti o la maggior parte delle proprie funzionalità all'interno di un singolo processo o contenitore e suddivisa in componenti in librerie o livelli interni.](./media/image1.png)

**Figura 4-1.** Un esempio di architettura dell'applicazione monolitica

Lo svantaggio di questo approccio viene fornito se o quando si espande l'applicazione, che richiedono scalabilità. Se l'intera applicazione è stata ridimensionata, non ci sono problemi. Tuttavia, nella maggior parte dei casi, alcune parti dell'applicazione sono colli di bottiglia che richiedono il ridimensionamento, mentre altri componenti vengono utilizzate meno.

Usando l'esempio tipico di e-commerce, ciò che è probabilmente necessario è scalare il componente di informazioni di prodotto. Il numero di clienti che visualizzano i prodotti è molto superiore al numero di quelli che li acquistano. Molti più clienti usano il carrello per poi usare la pipeline di pagamento, meno clienti aggiungono commenti o visualizzano la cronologia degli acquisti. E sono inclusi probabilmente solo pochi dipendenti, in una singola area, che devono gestire il contenuto e le campagne di marketing. Con il ridimensionamento della progettazione monolitica, tutto il codice viene distribuito più volte.

Oltre alla "scalabilità-tutto" problema, le modifiche apportate a un singolo componente richiedono la completa riesecuzione di test dell'intera applicazione, nonché una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni sviluppano con questo metodo dell'architettura. Molti usufruire buoni risultati, mentre altri utenti verificano i limiti. Molti progettavano le proprie applicazioni in questo modello perché gli strumenti e infrastruttura erano troppo difficili per creare SOA e non ne vedevano la necessità, fino a quando non sono aumentate l'app.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dell'host stesso e mostrare un rapporto accettabile di efficienza nell'utilizzo delle risorse, come illustrato nella figura 4-2.

![Un singolo host è possibile eseguire più App in contenitori separati.](./media/image2.png)

**Figura 4-2**. Un host che esegue più App/contenitori

Infine, dal punto di vista della disponibilità, le applicazioni monolitiche devono essere distribuite come un unico elemento. Questo significa che, nel caso in cui è necessario *arrestare e avviare*, tutte le funzionalità e tutti gli utenti interessati durante la finestra di distribuzione. In determinate situazioni, l'uso di Azure e contenitori può ridurre al minimo queste situazioni e ridurre la probabilità che il tempo di inattività dell'applicazione, come illustrato in figura 4-3.

È possibile distribuire le applicazioni monolitiche in Azure usando macchine virtuali dedicate per ogni istanza. Usando [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile ridimensionare facilmente le macchine virtuali.

È anche possibile usare [servizi App di Azure](https://azure.microsoft.com/services/app-service/) per eseguire applicazioni monolitiche e scalare facilmente le istanze senza la necessità di gestire le macchine virtuali. Servizi App di Azure può eseguire anche singole istanze di contenitori di Docker, semplificando la distribuzione.

È possibile distribuire più macchine virtuali come host Docker ed eseguire un numero qualsiasi di contenitori per ogni macchina virtuale. Quindi, usando un Azure Load Balancer, come illustrato nella figura 4-3, è possibile gestire la scalabilità.

![Un'app monolitica può essere scalabilità orizzontale in diversi host in cui ognuno di essi è in esecuzione l'app in contenitori.](./media/image3.png)

**Figura 4-3**. Più host, la scalabilità orizzontale una singola applicazione App/contenitori Docker

È possibile gestire la distribuzione degli stessi host tramite le tecniche di distribuzione tradizionali.

È possibile gestire i contenitori Docker dalla riga di comando, utilizzando comandi quali `docker run` e `docker-compose up`, ed è anche possibile automatizzarlo nelle pipeline di recapito continuo (CD) e distribuire gli host Docker da servizi di Azure DevOps, ad esempio.

## <a name="monolithic-application-deployed-as-a-container"></a>Applicazione monolitica distribuita come contenitore

Esistono vantaggi derivanti dall'uso di contenitori per gestire le distribuzioni monolitiche. Il ridimensionamento di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive.

La distribuzione degli aggiornamenti come immagini Docker è molto più veloce ed efficiente per la rete. I contenitori docker iniziano in genere espresso in secondi, consentendo implementazioni più veloci. Per chiudere un contenitore Docker è sufficiente richiamare il `docker stop` comando, viene normalmente completato in meno di un secondo.

Poiché i contenitori sono implicitamente non modificabili, per impostazione predefinita, non si devono mai preoccuparsi delle macchine virtuali danneggiate in quanto non è stato uno script di aggiornamento per conto di alcune configurazioni specifiche o i file disponibili su disco.

Anche se le app monolitiche possono trarre vantaggio da Docker, abbiamo stiamo toccare su solo le punte dei vantaggi. I maggiori vantaggi di gestione dei contenitori derivano dalla distribuzione con agenti di orchestrazione del contenitore che gestiscono le varie istanze e ciclo di vita di ogni istanza di contenitore. La suddivisione dell'applicazione monolitica in sottosistemi scalabili, sviluppabili e distribuibili a livello individuale è il punto di ingresso al campo dei microservizi.

Per altre informazioni su come "lift- and -shift le applicazioni monolitiche nei contenitori e come è possibile modernizzare le applicazioni, è possibile leggere questa Guida di Microsoft aggiuntiva, [modernizzare le applicazioni .NET esistenti con cloud di Azure e i contenitori Windows ](../../modernize-with-azure-and-containers/index.md), che è anche possibile scaricare in formato PDF da <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Pubblicare una singola app contenitore Docker nel servizio App di Azure

Sia perché si vuole ottenere una convalida rapida di un contenitore distribuito in Azure o l'app è semplicemente un'app singolo contenitore, servizi App di Azure fornisce un ottimo modo per fornire servizi scalabili singolo contenitore.

Tramite il servizio App di Azure è intuitivo e avrai e in esecuzione rapidamente perché offre eccezionali Git dell'integrazione del codice, compilare la soluzione in Microsoft Visual Studio e distribuirlo direttamente in Azure. Ma, tradizionalmente (con nessun Docker), se sono necessarie altre funzionalità, Framework o dipendenze che non sono supportate in servizi App, è necessario attendere fino a quando il team di Azure aggiorna tali dipendenze nel servizio App o passa ad altri servizi, ad esempio Service Fabric, servizi Cloud o persino il normale macchine virtuali, per cui si dispone di un'ulteriore controllo e può installare un componente richiesto o un framework per l'applicazione.

A questo punto, come illustrato nella figura 4-4, quando si usa Visual Studio 2017, supporto per i contenitori nel servizio App di Azure offre la possibilità di includere ciò che vuole app nell'ambiente in uso. Se una dipendenza è stato aggiunto alla tua app, perché viene eseguito in un contenitore, si ottiene la funzionalità di inclusione di tali dipendenze nell'immagine del Dockerfile o Docker.

![Visualizzazione della procedura guidata di Visual Studio per la pubblicazione in un servizio app di Azure, evidenziando i selettori per il registro contenitori.](./media/image4.png)

**Figura 4-4**. Pubblicazione di un contenitore in servizio App di Azure da Visual Studio. app/contenitori

Figura 4-4 mostra anche che il flusso di pubblicazione effettua il push di un'immagine tramite un registro contenitori, che può essere il registro contenitori di Azure (un registro vicino alle distribuzioni in Azure e protetto dall'account e gruppi di Azure Active Directory) o qualsiasi altro registro Docker ad esempio i registri di Docker Hub o in locale.

>[!div class="step-by-step"]
>[Precedente](common-container-design-principles.md)
>[Successivo](state-and-data-in-docker-applications.md)
