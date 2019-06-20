---
title: Applicazioni monolitiche
description: Concetti di base dell'inserimento di applicazioni monolitiche in contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: e577f9a8d9ce4f9d2c8180318b1df181db730e2f
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65641308"
---
# <a name="monolithic-applications"></a>Applicazioni monolitiche

In questo scenario si sta compilando un'unica applicazione o un unico servizio Web monolitico che deve essere distribuito come contenitore. All'interno l'applicazione potrebbe non essere monolitica, ma includere diverse librerie, componenti o persino livelli (livello dell'applicazione, livello del dominio, livello di accesso ai dati, e così via). Esternamente è un singolo contenitore, come un singolo processo, una singola applicazione Web o un singolo servizio.

Per gestire questo modello, distribuire un singolo contenitore per rappresentare l'applicazione. Per eseguirne la scalabilità orizzontale, basta aggiungere più copie con un bilanciamento del carico davanti. La semplicità deriva dalla gestione di un'unica distribuzione in un singolo contenitore o una singola macchina virtuale (VM).

Tuttavia, in base al principio secondo il quale un contenitore esegue solo un'operazione e la esegue in un unico processo, lo schema monolitico potrebbe generare conflitti. È possibile includere più componenti/librerie o livelli interni in ogni contenitore, come illustrato nella figura 4-1.

![La maggior parte delle funzionalità di un'app monolitica risiede in un unico processo o contenitore e l'app è suddivisa in componenti, librerie o livelli interni.](./media/image1.png)

**Figura 4-1.** Esempio di architettura di un'applicazione monolitica

Lo svantaggio di questo approccio diventa evidente con l'eventuale crescita dell'applicazione, che ne richiede il ridimensionamento. Se l'intera applicazione è stata ridimensionata, non ci sono problemi. Tuttavia, nella maggior parte dei casi, solo alcune parti dell'applicazione rappresentano colli di bottiglia che richiedono il ridimensionamento, mentre altri componenti vengono usati di meno.

Usando il tipico esempio di e-commerce, la parte che probabilmente sarà necessario ridimensionare è il componente relativo alle informazioni sui prodotti. Il numero di clienti che visualizzano i prodotti è molto superiore al numero di quelli che li acquistano. Molti più clienti usano il carrello per poi usare la pipeline di pagamento, meno clienti aggiungono commenti o visualizzano la cronologia degli acquisti. E probabilmente sono pochi i dipendenti, in una singola area, che avranno bisogno di gestire i contenuti e le campagne di marketing. Con il ridimensionamento della progettazione monolitica, tutto il codice viene distribuito più volte.

Oltre al problema del ridimensionamento di tutti i componenti, le modifiche apportate a un singolo componente richiedono la completa riesecuzione dei test sull'intera applicazione e una ridistribuzione completa di tutte le istanze.

L'approccio monolitico è comune e molte organizzazioni usano questo metodo nelle loro attività di sviluppo. Molte sono soddisfatte dei risultati ottenuti, mentre altre risentono delle limitazioni insite in questo metodo. Molte organizzazioni hanno progettato le proprie applicazioni usando questo modello perché gli strumenti e l'infrastruttura a loro disposizione erano troppo complesse per creare SOA e perché non ne hanno intravisto la necessità fino a quando le dimensioni dell'app non sono aumentate.

Dal punto di vista dell'infrastruttura, ogni server può eseguire molte applicazioni all'interno dello stesso host e avere un rapporto accettabile di efficienza nell'utilizzo di risorse, come illustrato nella figura 4-2.

![Un singolo host può eseguire più app in contenitori separati.](./media/image2.png)

**Figura 4-2**. Host che esegue più app in contenitori separati

Infine, dal punto di vista della disponibilità, le applicazioni monolitiche devono essere distribuite come un unico elemento. Questo significa che, in caso sia necessario eseguire un'operazione di *arresto e avvio*, questa interesserà tutte le funzionalità e tutti gli utenti durante la finestra di distribuzione. In alcuni casi, l'uso di Azure e di contenitori può ridurre al minimo queste situazioni e ridurre le probabilità di tempo di inattività dell'applicazione, come illustrato nella figura 4-3.

È possibile distribuire le applicazioni monolitiche in Azure usando VM dedicate per ogni istanza. Con i [set di scalabilità di macchine virtuali di Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/) è possibile ridimensionare facilmente le VM.

È anche possibile usare i [Servizi app di Azure](https://azure.microsoft.com/services/app-service/) per eseguire le applicazioni monolitiche e ridimensionare facilmente le istanze senza la necessità di gestire le VM. I Servizi app di Azure possono eseguire anche singole istanze di contenitori Docker, semplificando la distribuzione.

È possibile distribuire più VM come host Docker ed eseguire un numero qualsiasi di contenitori per VM. Quindi, usando Azure Load Balancer è possibile gestire la scalabilità, come illustrato nella figura 4-3.

![È possibile eseguire la scalabilità orizzontale di un'app monolitica in diversi host che eseguono l'app in contenitori.](./media/image3.png)

**Figura 4-3**. Più host che eseguono la scalabilità orizzontale di una singola applicazione in app/contenitori Docker

È possibile gestire la distribuzione degli stessi host tramite le tecniche di distribuzione tradizionali.

È possibile gestire i contenitori Docker dalla riga di comando, usando comandi quali `docker run` e `docker-compose up`, ed è anche possibile automatizzarli nelle pipeline di recapito continuo e distribuirli negli host Docker da Azure DevOps Services, ad esempio.

## <a name="monolithic-application-deployed-as-a-container"></a>Applicazione monolitica distribuita come contenitore

Esistono vantaggi derivanti dall'uso di contenitori per gestire le distribuzioni di applicazioni monolitiche. Il ridimensionamento di istanze di contenitori è molto più veloce e semplice rispetto alla distribuzione di macchine virtuali aggiuntive.

La distribuzione degli aggiornamenti come immagini Docker è molto più veloce ed efficiente per la rete. L'avvio dei contenitori Docker richiede in genere pochi secondi, consentendo implementazioni più veloci. Per chiudere un contenitore Docker, è sufficiente richiamare il comando `docker stop` che viene normalmente completato in meno di un secondo.

Poiché i contenitori sono implicitamente non modificabili per impostazione predefinita, non è un problema se una VM viene danneggiata perché gli script di aggiornamento hanno tralasciato alcune configurazioni specifiche o alcuni file rimasti su disco.

Anche se le applicazioni monolitiche possano trarre vantaggio da Docker, in questo articolo i vantaggi vengono trattati solo in modo rapido. I vantaggi maggiori della gestione dei contenitori derivano dalla distribuzione con agenti di orchestrazione del contenitore, che gestiscono le varie istanze e il ciclo di vita di ogni istanza del contenitore. La suddivisione dell'applicazione monolitica in sottosistemi scalabili, sviluppabili e distribuibili a livello individuale è il punto di ingresso al campo dei microservizi.

Per altre informazioni su come distribuire le applicazioni monolitiche con i contenitori e su come modernizzare le applicazioni, è possibile leggere questa Guida di Microsoft aggiuntiva, [Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori Windows ](../../modernize-with-azure-and-containers/index.md), che è anche possibile scaricare in formato PDF da <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Pubblicare una singola app contenitore Docker in Servizio app di Azure

Servizio app di Azure è un ottimo modo per offrire servizi scalabili basati su un singolo contenitore, sia per convalidare rapidamente un contenitore distribuito in Azure, sia nel caso di un'app costituita da un singolo contenitore.

Servizio app di Azure è intuitivo e consente di essere operativi in tempi rapidi perché offre un'integrazione ottimale con Git per compilare il codice in Microsoft Visual Studio e distribuirlo direttamente in Azure. Ma, tradizionalmente, ovvero senza Docker, se sono necessarie altre funzionalità, framework o dipendenze che non sono supportate in Servizi app, è necessario attendere fino a quando il team di Azure aggiorna tali dipendenze nel servizio app o passare ad altri servizi, come ad esempio Service Fabric, Servizi cloud o persino le normali VM, per cui si dispone di maggior controllo ed è possibile installare un componente o un framework richiesto per l'applicazione.

Ora quando si usa Visual Studio 2017, il supporto dei contenitori in Servizio app di Azure offre la possibilità di includere ciò che si vuole nell'ambiente dell'applicazione, come illustrato nella figura 4-4. Se è stata aggiunta una dipendenza all'app perché l'app viene eseguita in un contenitore, è possibile includere tale dipendenza nel Dockerfile o nell'immagine Docker.

![Procedura guidata di Visual Studio per la pubblicazione in Servizio app di Azure, con la selezione del registro contenitori evidenziata.](./media/image4.png)

**Figura 4-4**. Pubblicazione di un contenitore in Servizio app di Azure da app/contenitori di Visual Studio

La figura 4-4 illustra anche che il flusso di pubblicazione esegue il push di un'immagine tramite un Registro Azure Container, ovvero un registro vicino alle distribuzioni in Azure e protetto dai gruppi e dagli account di Azure Active Directory, oppure in qualsiasi altro registro Docker, come Docker Hub o i registri locali.

>[!div class="step-by-step"]
>[Precedente](common-container-design-principles.md)
>[Successivo](state-and-data-in-docker-applications.md)
