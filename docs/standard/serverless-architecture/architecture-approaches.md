---
title: Architettura approcci - App senza server
description: Per la compilazione di applicazioni aziendali basate su cloud, da architetture a più livelli per senza server si avvicina un'introduzione all'architettura.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 21e191f17e7d0b4f2d64454fb14c46a4831a8375
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "49370020"
---
# <a name="architecture-approaches"></a>Approcci di architettura

La comprensione di approcci esistenti per la progettazione di App aziendali consente di chiarire il ruolo svolto da senza server. Esistono molti approcci e i modelli che si è evoluta negli decenni dello sviluppo software e tutti i propri vantaggi e svantaggi. In molti casi, la soluzione definitiva non può riguardare scelta di un unico approccio ma può essere integrato diversi approcci. Gli scenari di migrazione includono spesso shifting dall'approccio di uno architettura a altro tramite un approccio ibrido.

In questo capitolo viene fornita una panoramica di entrambi i modelli di architettura logica e fisica per le applicazioni aziendali.

## <a name="architecture-patterns"></a>Modelli di architettura

Le applicazioni aziendali moderne seguono un'ampia gamma di modelli di architettura. In questa sezione rappresenta un sondaggio di modelli comuni. I modelli elencati di seguito non sono necessariamente tutte le procedure consigliate, ma vengono illustrati diversi approcci.

Per altre informazioni, vedere [Guida all'architettura delle applicazione Azure](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Strutture monolitiche

Molte applicazioni aziendali seguono un modello di App monolitica. Le applicazioni legacy vengono spesso implementate come strutture monolitiche. Nel modello di struttura monolitica, tutti i problemi relativi all'applicazione sono contenuti in una singola distribuzione. Tutti gli elementi dell'interfaccia utente per le chiamate al database è incluso nella stessa codebase.

![Architettura monolite](./media/monolith-architecture.png)

Esistono diversi vantaggi dell'approccio monolite. Spesso è facile ottenga una singola codebase e iniziare a lavorare. Periodo di addestramento può essere inferiore e la creazione di ambienti di test è semplice come fornire una nuova copia. Il monolite può essere progettato per includere più componenti e applicazioni.

Sfortunatamente, il modello di struttura monolitica tende a suddividere su larga scala. Principali svantaggi dell'approccio monolite includono:

* Difficoltà di operare in parallelo nella stessa base di codice.
* Qualsiasi modifica, indipendentemente dal modo in cui banale, richiede la distribuzione di una nuova versione dell'intera applicazione.
* Refactoring potenzialmente interessa l'intera applicazione.
* Spesso l'unica soluzione per la scalabilità consiste nel creare più copie di elevato utilizzo di risorse dell'App monolitica.
* Come espandere i sistemi o vengono acquisiti altri sistemi, integrazione può essere difficile.
* Potrebbe essere difficile testare a causa della necessità di configurare il monolite intero.
* Riutilizzo del codice è complesso e spesso altre App finisce con le proprie copie del codice.

Molte aziende Cerca nel cloud come un'opportunità per la migrazione delle applicazioni monolite e allo stesso tempo il refactoring per più modelli utilizzabili. È comune per suddividere le singole applicazioni e i componenti in modo che possano essere gestiti, distribuire e ridimensionare separatamente.

## <a name="n-layer-applications"></a>Applicazioni a più livelli

Applicazione a più livelli partizione dell'applicazione per la logica in livelli specifici. I livelli più comuni includono:

* Interfaccia utente
* logica di Business
* Accesso ai dati

Possono includere altri livelli middleware, l'elaborazione batch e API. È importante tenere presente che i livelli sono logici. Sebbene svilupparono in isolamento, tutti di questi può essere distribuiti per la stessa piattaforma di destinazione.

![Architettura a più livelli](./media/n-layer-architecture.png)

Esistono diversi vantaggi dell'approccio a più livelli, tra cui:

* Il refactoring è isolata e prevede un livello.
* In modo indipendente i team possono creare, testare, distribuire e gestire livelli separati.
* I livelli possono essere scambiati in modo, ad esempio il livello dati può accedere a più database senza dover apportare modifiche a livello dell'interfaccia utente.

Serverless può essere utilizzato per implementare uno o più livelli.

## <a name="microservices"></a>Microservizi

**[I Microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  architetture contengano caratteristiche comuni che includono:

* Le applicazioni sono costituite da piccoli servizi diversi.
* Ogni servizio viene eseguito nel proprio processo.
* I servizi sono allineati intorno a domini aziendali.
* I servizi comunicano tramite API leggere, in genere Usa HTTP come trasporto.
* Servizi possono essere distribuiti e aggiornati in modo indipendente.
* Servizi non dipendenti da un unico archivio dati.
* Il sistema è progettato con un errore presente, e le app possono comunque eseguire anche quando determinati servizi hanno esito negativo.

I Microservizi non dovranno essere si escludono a vicenda per altri approcci di architettura. Ad esempio, un'architettura a più livelli può usare i microservizi per il livello intermedio. È anche possibile implementare i microservizi in svariati modi, dalle directory virtuali in host IIS per i contenitori. Caratteristiche dei microservizi li rendono ideali in particolare per le implementazioni senza server.

![Architettura di microservizi](./media/microservices-architecture.png)

I professionisti di architetture di microservizi includono:

* Spesso il refactoring è isolata e prevede un singolo servizio.
* I servizi possono essere aggiornati indipendentemente uno da altro.
* Resilienza e l'elasticità possono essere ottimizzate per le esigenze dei singoli servizi.
* Sviluppo può verificarsi in parallelo tra le piattaforme e diversi team.
* È più semplice scrivere i test completi per i servizi di tipo isolati.

I Microservizi sono dotate di proprie problematiche, tra cui:

* Determinare quali servizi sono disponibili e come chiamarle.
* Gestire il ciclo di vita dei servizi.
* Comprendere come i servizi si integrino in applicazione globale.
* Test di sistema completo delle chiamate effettuate tra i diversi servizi.

In definitiva sono disponibili soluzioni per soddisfare tutti questi problemi, tra cui attingere ai vantaggi degli strumenti senza server che verranno trattati più avanti.

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](architecture-deployment-approaches.md)
