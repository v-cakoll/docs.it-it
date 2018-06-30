---
title: Applicazioni monolitiche
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 4d25ef131cf149eb869fa2acd40eddff5ee0b55d
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106619"
---
# <a name="monolithic-applications"></a>Applicazioni monolitiche

In questo scenario, la compilazione di un singolo e monolitico applicazione o servizio web e distribuirla come contenitore. All'interno dell'applicazione, la struttura potrebbe non essere monolitica; potrebbe comprendono diverse librerie, componenti o livelli anche (livello dell'applicazione, il livello di dominio, il livello di accesso ai dati e così via). Esternamente, è un singolo contenitore, come un unico processo, singola applicazione web o singolo servizio.

Per gestire questo modello, distribuire un singolo contenitore per rappresentare l'applicazione. La scalabilità sufficiente aggiungere alcune altre copie con un bilanciamento del carico in primo piano. La semplicità proviene da un'unica distribuzione in un singolo contenitore o una macchina virtuale (VM) di gestione.

In seguito l'entità che consente di eseguire un'operazione solo un contenitore e opera in un unico processo, il modello monolitico è in conflitto. È possibile includere più componenti/librerie o interni livelli all'interno di ogni contenitore, come illustrato nella figura 4-1.

![](./media/image1.png)

Figura 4-1: esempio di architettura dell'applicazione monolitico

Lo svantaggio di questo approccio proviene se o quando si estende l'applicazione, che richiedono scalabilità. Se l'intera applicazione è stata ridimensionata, non ci sono problemi. Tuttavia, nella maggior parte dei casi, alcune parti dell'applicazione sono i punti di riduzione che richiedono scalabilità, mentre gli altri componenti sono utilizzati meno.

Utilizzando l'esempio tipico di e-commerce, è probabilmente necessario è scalare il componente di informazioni di prodotto. Il numero di clienti che visualizzano i prodotti è molto superiore al numero di quelli che li acquistano. Molti più clienti usano il carrello per poi usare la pipeline di pagamento, meno clienti aggiungono commenti o visualizzano la cronologia degli acquisti. E probabilmente necessario solo un numero limitato di dipendenti, in una singola area, che devono gestire il contenuto e le campagne di marketing. Per la progettazione monolitica la scala, tutto il codice viene distribuito più volte.

Oltre alla "scalabilità-tutti gli elementi" problema, le modifiche apportate a un singolo componente richiedono una nuova esecuzione completa l'intera applicazione, nonché una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni sviluppa con questo metodo dell'architettura. Molti dispongono buono sufficiente risultati, mentre altri utenti verificano limiti. Molti progettati proprie applicazioni in questo modello perché gli strumenti e l'infrastruttura erano troppo difficile da compilare SOA e non visualizzano la necessità, fino a quando l'app aumentate.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dell'host stesso e di un rapporto accettabile di efficienza sull'utilizzo delle risorse, come illustrato nella figura 4-2.

![](./media/image2.png)

Figura 4-2: un host che esegue più applicazioni/contenitori

È possibile distribuire applicazioni monolitiche in Azure utilizzando macchine virtuali dedicate per ogni istanza. Utilizzo [set di scalabilità di macchine Virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), è possibile scalare facilmente le macchine virtuali. I [Servizi app di Azure](https://azure.microsoft.com/en-us/services/app-service/) sono in grado di eseguire le applicazioni monolitiche e di ridimensionare facilmente le istanze senza la necessità di gestire le macchine virtuali. A partire da 2016, servizi di App di Azure può eseguito singole istanze di contenitori di Docker, nonché semplificando la distribuzione. E, usando Docker, è possibile distribuire una singola macchina virtuale come host Docker ed eseguire più istanze. Utilizza il servizio di bilanciamento Azure, come illustrato nella figura 4-3, è possibile gestire la scalabilità.

![](./media/image3.png)

Figura 4-3: più host la scalabilità orizzontale una singola applicazione App/contenitori di Docker

È possibile gestire la distribuzione di vari host tramite le tecniche tradizionali di distribuzione. È possibile gestire gli host Docker, utilizzando comandi quali `docker run` manualmente, tramite l'automazione, ad esempio le pipeline continui recapito (CD), che viene descritto più avanti in questo e-book.

## <a name="monolithic-application-deployed-as-a-container"></a>Applicazione monolitica distribuita come contenitore

Esistono vantaggi derivanti dall'utilizzo di contenitori per gestire le distribuzioni monolitiche. Il ridimensionamento di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive. Anche se il set di scalabilità di macchine Virtuali sono un'ottima funzionalità scalabilità di macchine virtuali, sono necessarie per ospitare i contenitori di Docker, accettano durata per la configurazione. Quando viene distribuita come istanza dell'app, la configurazione dell'app viene gestita nell'ambito della macchina virtuale.

La distribuzione degli aggiornamenti come immagini Docker è molto più veloce ed efficiente per la rete. Le istanze Vn possono essere impostate sugli stessi host le istanze di Vn-1, eliminando i costi e determinate dalle altre macchine virtuali. Le immagini docker iniziano in genere espresso in secondi, velocizzando l'implementazione. Fine di interoperare verso un'istanza di Docker è facile come richiamare il `docker stop` comando, in genere completato in meno di un secondo.

Poiché i contenitori sono intrinsecamente modificabili, per impostazione predefinita, è non necessario mai preoccuparsi di macchine virtuali danneggiate perché non è stato uno script di aggiornamento tenere conto per alcuni specifici file di configurazione o su disco.

Sebbene le app monolitiche possono trarre vantaggio da Docker, è in corso tocca su solo i suggerimenti dei vantaggi. I maggiori vantaggi della gestione dei contenitori proviene dalla distribuzione con orchestrators contenitore che gestiscono le varie istanze e ciclo di vita di ogni istanza del contenitore. La suddivisione dell'applicazione monolitica in sottosistemi scalabili, sviluppabili e distribuibili a livello individuale è il punto di ingresso al campo dei microservizi.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>La pubblicazione di una singola app contenitore Docker in Azure App Service

Sia perché si desidera ottenere una convalida rapida di un contenitore distribuito in Azure o l'app è semplicemente un'app singolo contenitore, servizi di App di Azure fornisce un ottimo modo per fornire servizi scalabili singolo contenitore.

Tramite Azure App Service è intuitivo neppure ed è possibile iniziare a in esecuzione e rapidamente perché offre grande Git integration per rendere il codice, compilarlo in Microsoft Visual Studio, direttamente distribuirla in Azure. Ma, in genere (con nessun Docker), se sono necessarie altre funzionalità, Framework o le dipendenze che non sono supportate in servizi di App, è necessario attendere fino a quando il team di Azure aggiorna tali dipendenze nel servizio App o si è passati ad altri servizi, ad esempio Service Fabric, servizi Cloud o macchine virtuali anche normale, per cui si ha un'ulteriore controllo e può installare un componente obbligatorio o framework per l'applicazione.

A questo punto, tuttavia, (annunciati in Microsoft Connect 2016 nel novembre 2016) e come illustrato nella figura 4‑4, quando si utilizza Visual Studio 2017, supporto contenitore nel servizio App di Azure offre la possibilità di includere le operazioni desiderate nel proprio ambiente di app. Se una dipendenza è stato aggiunto all'App, perché sono in esecuzione in un contenitore, si ottiene la capacità di tali dipendenze incluse nell'immagine del Dockerfile o Docker.

![](./media/image4.png)

Figura 4-4: pubblicare un contenitore di servizio App di Azure da Visual Studio. app/contenitori

Figura 4-4 mostra anche che il flusso di pubblicazione inserisce un'immagine tramite un contenitore del Registro di sistema, che può essere il Registro di sistema contenitore di Azure (un registro di sistema vicino per le distribuzioni in Azure e protetto dall'account e gruppi di Azure Active Directory) o qualsiasi altro Docker del Registro di sistema ad esempio i registri di Hub Docker oppure in locale.


>[!div class="step-by-step"]
[Precedente](common-container-design-principles.md)
[Successivo](state-and-data-in-docker-applications.md)
