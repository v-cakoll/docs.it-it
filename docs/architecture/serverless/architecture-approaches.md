---
title: Approcci di architettura-app senza server
description: Introduzione agli approcci di architettura per la creazione di applicazioni aziendali basate su cloud, da architetture a più livelli a senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577804"
---
# <a name="architecture-approaches"></a>Approcci all'architettura

Comprendere gli approcci esistenti per l'architettura delle app aziendali consente di chiarire il ruolo svolto da server. Ci sono molti approcci e modelli che si sono evoluti oltre decenni di sviluppo del software e hanno tutti i propri vantaggi e svantaggi. In molti casi, la soluzione definitiva potrebbe non comportare la scelta di un singolo approccio, ma può integrare diversi approcci. Gli scenari di migrazione spesso coinvolgono lo spostamento da un approccio dell'architettura a un altro tramite un approccio ibrido.

In questo capitolo viene fornita una panoramica dei modelli di architettura logica e fisica per le applicazioni aziendali.

## <a name="architecture-patterns"></a>Modelli di architettura

Le applicazioni aziendali moderne seguono un'ampia gamma di modelli di architettura. Questa sezione rappresenta un sondaggio di modelli comuni. Gli schemi elencati di seguito non sono necessariamente tutte le procedure consigliate, ma illustrano approcci diversi.

Per altre informazioni, vedere [Guida all'architettura delle applicazioni di Azure](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Strutture monolitiche

Molte applicazioni aziendali seguono uno schema monolitico. Le applicazioni legacy vengono spesso implementate come monolitici. Nel modello monolitico, tutti i problemi relativi alle applicazioni sono contenuti in una singola distribuzione. Tutti gli elementi dall'interfaccia utente alle chiamate al database sono inclusi nella stessa codebase.

![Architettura monolitica](./media/monolith-architecture.png)

L'approccio monolitico presenta diversi vantaggi. Spesso è facile estrarre una singola codebase e iniziare a lavorare. Il tempo di preparazione della rampa può essere inferiore e la creazione di ambienti di test è semplice quanto fornire una nuova copia. Il monolito può essere progettato per includere più componenti e applicazioni.

Sfortunatamente, il modello monolitico tende a suddividere la scalabilità. Gli svantaggi principali dell'approccio monolitico includono:

* Difficile lavorare in parallelo nella stessa codebase.
* Qualsiasi modifica, indipendentemente dalla banalità, richiede la distribuzione di una nuova versione dell'intera applicazione.
* Il refactoring potrebbe influire sull'intera applicazione.
* Spesso l'unica soluzione per la scalabilità consiste nel creare più copie a elevato utilizzo di risorse del monolito.
* Con l'espansione dei sistemi o l'acquisizione di altri sistemi, l'integrazione può essere difficile.
* Potrebbe essere difficile eseguire il test a causa della necessità di configurare l'intero Monolith.
* Il riutilizzo del codice è complesso e spesso le altre app finiscono con le proprie copie di codice.

Molte aziende si affacciano sul cloud come opportunità per eseguire la migrazione di applicazioni monolitiche e allo stesso tempo effettuare il refactoring a modelli più utilizzabili. È comune suddividere i singoli componenti e applicazioni per consentirne la manutenzione, la distribuzione e la scalabilità separatamente.

## <a name="n-layer-applications"></a>Applicazioni a N livelli

Logica dell'applicazione della partizione di applicazione a più livelli in livelli specifici. I livelli più comuni includono:

* Interfaccia utente
* Logica di business
* Accesso ai dati

Altri livelli possono includere middleware, elaborazione batch e API. È importante notare che i livelli sono logici. Sebbene siano sviluppate in isolamento, possono essere tutte distribuite nella stessa piattaforma di destinazione.

![Architettura a N livelli](./media/n-layer-architecture.png)

L'approccio a N livelli presenta diversi vantaggi, tra cui:

* Il refactoring è isolato a un livello.
* I team possono compilare, testare, distribuire e gestire livelli separati in modo indipendente.
* I livelli possono essere scambiati, ad esempio il livello dati può accedere a più database senza richiedere modifiche al livello dell'interfaccia utente.

Il server può essere utilizzato per implementare uno o più livelli.

## <a name="microservices"></a>Microservizi

Le architetture di **[microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contengono caratteristiche comuni che includono:

* Le applicazioni sono costituite da diversi servizi di piccole dimensioni.
* Ogni servizio viene eseguito nel proprio processo.
* I servizi sono allineati intorno ai domini aziendali.
* I servizi comunicano tramite API semplici, in genere tramite HTTP come trasporto.
* I servizi possono essere distribuiti e aggiornati in modo indipendente.
* I servizi non dipendono da un singolo archivio dati.
* Il sistema è stato progettato in modo anomalo e l'app potrebbe essere ancora in esecuzione anche quando determinati servizi hanno esito negativo.

I microservizi non devono essere reciprocamente esclusivi ad altri approcci di architettura. Ad esempio, un'architettura a più livelli può usare microservizi per il livello intermedio. È anche possibile implementare i microservizi in diversi modi, dalle directory virtuali negli host IIS ai contenitori. Le caratteristiche dei microservizi li rendono particolarmente ideali per le implementazioni senza server.

![Architettura di microservizi](./media/microservices-architecture.png)

I vantaggi delle architetture di microservizi includono:

* Il refactoring è spesso isolato in un singolo servizio.
* I servizi possono essere aggiornati in modo indipendente l'uno dall'altro.
* La resilienza e l'elasticità possono essere ottimizzate in modo da soddisfare le esigenze dei singoli servizi.
* Lo sviluppo può avvenire in parallelo tra diversi team e piattaforme.
* È più facile scrivere test completi per i servizi isolati.

I microservizi vengono affrontati con le proprie esigenze, tra cui:

* Determinare quali servizi sono disponibili e come chiamarli.
* Gestione del ciclo di vita dei servizi.
* Informazioni sul modo in cui i servizi si integrano nell'applicazione complessiva.
* Test completi del sistema di chiamate effettuate in servizi diversi.

Infine, esistono soluzioni per risolvere tutti questi problemi, tra cui sfruttare i vantaggi offerti da server senza server descritti in seguito.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](architecture-deployment-approaches.md)
