---
title: Applicazioni monolitiche
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: a2fe2c325377ec49f89199ad2e36c950ebab6a24
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374703"
---
# <a name="monolithic-applications"></a>Applicazioni monolitiche

In questo scenario, la compilazione di un servizio o applicazione web monolitica e singolo e distribuirla come contenitore. All'interno dell'applicazione, la struttura potrebbe non essere monolitica; può comprendere diverse librerie, componenti o persino livelli (livello dell'applicazione, livello di dominio, il livello di accesso ai dati e così via). Esternamente, è un singolo contenitore, come un singolo processo, singola applicazione web o servizio singolo.

Per gestire questo modello, distribuire un singolo contenitore per rappresentare l'applicazione. Per la scalabilità, è sufficiente aggiungere alcune altre copie con un bilanciamento del carico in primo piano. La semplicità deriva dalla gestione di un'unica distribuzione in un singolo contenitore o una macchina virtuale (VM).

In seguito l'entità che esegue un'operazione solo un contenitore e lo fa in un unico processo, lo schema monolitico è in conflitto. È possibile includere più componenti/librerie o livelli interni in ogni contenitore, come illustrato nella figura 4-1.

![](./media/image1.png)

Figura 4-1: un esempio di architettura dell'applicazione monolitica

Lo svantaggio di questo approccio viene fornito se o quando si espande l'applicazione, che richiedono scalabilità. Se l'intera applicazione è stata ridimensionata, non ci sono problemi. Tuttavia, nella maggior parte dei casi, alcune parti dell'applicazione sono colli di bottiglia che richiedono il ridimensionamento, mentre altri componenti vengono utilizzate meno.

Usando l'esempio tipico di e-commerce, ciò che è probabilmente necessario è scalare il componente di informazioni di prodotto. Il numero di clienti che visualizzano i prodotti è molto superiore al numero di quelli che li acquistano. Molti più clienti usano il carrello per poi usare la pipeline di pagamento, meno clienti aggiungono commenti o visualizzano la cronologia degli acquisti. E sono inclusi probabilmente solo pochi dipendenti, in una singola area, che devono gestire il contenuto e le campagne di marketing. Con il ridimensionamento della progettazione monolitica, tutto il codice viene distribuito più volte.

Oltre alla "scalabilità-tutto" problema, le modifiche apportate a un singolo componente richiedono la completa riesecuzione di test dell'intera applicazione, nonché una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni sviluppano con questo metodo dell'architettura. Molti usufruire buoni risultati, mentre altri utenti verificano i limiti. Molti progettavano le proprie applicazioni in questo modello perché gli strumenti e infrastruttura erano troppo difficili per creare SOA e non ne vedevano la necessità, fino a quando non sono aumentate l'app.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dell'host stesso e mostrare un rapporto accettabile di efficienza nell'utilizzo delle risorse, come illustrato nella figura 4-2.

![](./media/image2.png)

Figura 4-2: un host che esegue più App/contenitori

È possibile distribuire le applicazioni monolitiche in Azure usando macchine virtuali dedicate per ogni istanza. Usando [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile ridimensionare facilmente le macchine virtuali. I [Servizi app di Azure](https://azure.microsoft.com/services/app-service/) sono in grado di eseguire le applicazioni monolitiche e di ridimensionare facilmente le istanze senza la necessità di gestire le macchine virtuali. Dal 2016, servizi App di Azure può eseguire anche singole istanze di contenitori di Docker, semplificando la distribuzione. E, usando Docker, è possibile distribuire una singola macchina virtuale come host Docker ed eseguire più istanze. Usa il servizio di bilanciamento Azure, come illustrato nella figura 4-3, è possibile gestire la scalabilità.

![](./media/image3.png)

Figura 4-3: più host la scalabilità orizzontale una singola applicazione App/contenitori Docker

È possibile gestire la distribuzione ai vari host tramite le tecniche di distribuzione tradizionali. È possibile gestire gli host Docker, utilizzando comandi quali `docker run` manualmente, tramite l'automazione, ad esempio le pipeline di recapito continuo (CD), che viene illustrato più avanti in questo e-book.

## <a name="monolithic-application-deployed-as-a-container"></a>Applicazione monolitica distribuita come contenitore

Esistono vantaggi derivanti dall'uso di contenitori per gestire le distribuzioni monolitiche. Il ridimensionamento di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche se il set di scalabilità di macchine Virtuali sono un'ottima funzionalità di scalabilità di macchine virtuali, sono necessari per ospitare i contenitori Docker, occorre tempo per configurare. Quando viene distribuita come istanza dell'app, la configurazione dell'app viene gestita nell'ambito della macchina virtuale.

La distribuzione degli aggiornamenti come immagini Docker è molto più veloce ed efficiente per la rete. Le istanze Vn da impostare negli host stesso come le istanze di Vn-1, eliminando i costi aggiuntivi dovuti a macchine virtuali aggiuntive. Le immagini docker iniziano in genere espresso in secondi, consentendo implementazioni più veloci. Per chiudere un'istanza di Docker è sufficiente richiamare il `docker stop` comando, viene normalmente completato in meno di un secondo.

Poiché i contenitori sono implicitamente non modificabili, per impostazione predefinita, non si devono mai preoccuparsi delle macchine virtuali danneggiate in quanto non è stato uno script di aggiornamento per conto di alcune configurazioni specifiche o i file disponibili su disco.

Anche se le app monolitiche possono trarre vantaggio da Docker, abbiamo stiamo toccare su solo le punte dei vantaggi. I maggiori vantaggi di gestione dei contenitori proviene dalla distribuzione con agenti di orchestrazione del contenitore che gestiscono le varie istanze e ciclo di vita di ogni istanza di contenitore. La suddivisione dell'applicazione monolitica in sottosistemi scalabili, sviluppabili e distribuibili a livello individuale è il punto di ingresso al campo dei microservizi.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>Pubblicazione di una singola app contenitore Docker in Azure App Service

Sia perché si vuole ottenere una convalida rapida di un contenitore distribuito in Azure o l'app è semplicemente un'app singolo contenitore, servizi App di Azure fornisce un ottimo modo per fornire servizi scalabili singolo contenitore.

Tramite il servizio App di Azure è intuitivo e avrai e in esecuzione rapidamente perché offre eccezionali Git dell'integrazione del codice, compilare la soluzione in Microsoft Visual Studio e distribuirlo direttamente in Azure. Ma, tradizionalmente (con nessun Docker), se sono necessarie altre funzionalità, Framework o dipendenze che non sono supportate in servizi App, è necessario attendere fino a quando il team di Azure aggiorna tali dipendenze nel servizio App o passa ad altri servizi, ad esempio Service Fabric, servizi Cloud o persino il normale macchine virtuali, per cui si dispone di un'ulteriore controllo e può installare un componente richiesto o un framework per l'applicazione.

A questo punto, tuttavia, (annunciato in occasione di Microsoft Connect 2016 a novembre 2016) e come illustrato nella figura 4‑4, quando si usa Visual Studio 2017, supporto per i contenitori nel servizio App di Azure ti offre la possibilità di includere ciò che vuole app nell'ambiente in uso. Se una dipendenza è stato aggiunto alla tua app, perché in esecuzione in un contenitore, si ottiene la funzionalità di inclusione di tali dipendenze nell'immagine del Dockerfile o Docker.

![](./media/image4.png)

Figura 4-4: pubblicazione di un contenitore in servizio App di Azure da Visual Studio. app/contenitori

Figura 4-4 mostra anche che il flusso di pubblicazione effettua il push di un'immagine tramite un registro contenitori, che può essere il registro contenitori di Azure (un registro vicino alle distribuzioni in Azure e protetto dall'account e gruppi di Azure Active Directory) o qualsiasi altro registro Docker ad esempio i registri di Docker Hub o in locale.


>[!div class="step-by-step"]
[Precedente](common-container-design-principles.md)
[Successivo](state-and-data-in-docker-applications.md)
