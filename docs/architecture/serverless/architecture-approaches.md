---
title: Approcci per l'architettura - App senza server
description: Introduzione agli approcci architetturali per la creazione di applicazioni aziendali basate su cloud, dalle architetture a più livelli a quella senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522892"
---
# <a name="architecture-approaches"></a>Approcci all'architettura

Comprendere gli approcci esistenti per l'architettura di app aziendali consente di chiarire il ruolo svolto da serverless. Ci sono molti approcci e modelli che si sono evoluti nel corso di decenni di sviluppo software, e tutti hanno i propri pro e contro. In molti casi, la soluzione definitiva non può comportare la decisione su un unico approccio, ma può integrare diversi approcci. Gli scenari di migrazione spesso comportano il passaggio da un approccio all'architettura all'altro attraverso un approccio ibrido.

In questo capitolo viene fornita una panoramica dei modelli di architettura logica e fisica per le applicazioni aziendali.

## <a name="architecture-patterns"></a>Modelli di architettura

Le applicazioni aziendali moderne seguono una varietà di modelli di architettura. Questa sezione rappresenta un'indagine sui modelli comuni. I modelli elencati di seguito non sono necessariamente tutte le procedure consigliate, ma illustrano approcci diversi.

Per altre informazioni, vedere [Guida all'architettura delle applicazioni](https://docs.microsoft.com/azure/architecture/guide/)di Azure .For more information, see Azure application architecture guide .

## <a name="monoliths"></a>Monoliti

Molte applicazioni aziendali seguono un modello monolito. Le applicazioni legacy vengono spesso implementate come monoliti. Nel modello monolito, tutti i problemi dell'applicazione sono contenuti in un'unica distribuzione. Tutto, dall'interfaccia utente alle chiamate al database, è incluso nella stessa codebase.

![Architettura monolite](./media/monolith-architecture.png)

L'approccio monolitico presenta diversi vantaggi. Spesso è facile tirare giù una singola base di codice e iniziare a lavorare. Il tempo di rampup può essere inferiore e la creazione di ambienti di test è semplice come fornire una nuova copia. Il monolite può essere progettato per includere più componenti e applicazioni.

Sfortunatamente, il modello monolito tende a rompersi su larga scala. I principali svantaggi dell'approccio monolitico includono:

- Difficile lavorare in parallelo nella stessa base di codice.
- Qualsiasi modifica, indipendentemente dal fatto che sia semplice, richiede la distribuzione di una nuova versione dell'intera applicazione.
- Il refactoring influisce potenzialmente sull'intera applicazione.
- Spesso l'unica soluzione per scalare è quella di creare più copie a uso elevato di risorse del monolite.
- Man mano che i sistemi si espandono o vengono acquisiti altri sistemi, l'integrazione può essere difficile.
- Può essere difficile da testare a causa della necessità di configurare l'intero monolite.
- Il riutilizzo del codice è impegnativo e spesso altre app finiscono per avere le proprie copie del codice.

Molte aziende considerano il cloud un'opportunità per migrare le applicazioni monolistiche e allo stesso tempo eseguirne il refactoring in modelli più utilizzabili. È comune suddividere le singole applicazioni e componenti per consentirne la manutenzione, la distribuzione e la scalabilità separata.

## <a name="n-layer-applications"></a>Applicazioni A N livelli

Logica dell'applicazione della partizione applicativa a più livelli in livelli specifici. I livelli più comuni includono:

- Interfaccia utente
- Logica di business
- Accesso ai dati

Altri livelli possono includere middleware, elaborazione batch e API. È importante notare che i layer sono logici. Anche se sono sviluppati in isolamento, possono essere tutti distribuiti nella stessa piattaforma di destinazione.

![Architettura A N livelli](./media/n-layer-architecture.png)

L'approccio N-Layer presenta diversi vantaggi, tra cui:

- Il refactoring è isolato in un livello.
- I team possono creare, testare, distribuire e gestire livelli separati in modo indipendente.
- I layer possono essere scambiati, ad esempio il livello dati può accedere a più database senza richiedere modifiche al livello dell'interfaccia utente.

Serverless può essere utilizzato per implementare uno o più livelli.

## <a name="microservices"></a>Microservizi

Le architetture di microservizi contengono caratteristiche comuni che **[includono:Microservicess](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contain common characteristics that include:

- Le applicazioni sono composte da diversi piccoli servizi.
- Ogni servizio viene eseguito nel proprio processo.
- I servizi sono allineati intorno ai domini aziendali.
- I servizi comunicano tramite API leggere, in genere usando HTTP come trasporto.
- I servizi possono essere distribuiti e aggiornati in modo indipendente.
- I servizi non dipendono da un singolo archivio dati.
- Il sistema è progettato tenendo presente un errore e l'app potrebbe comunque essere eseguita anche in caso di errore di alcuni servizi.

I microservizi non devono essere reciprocamente esclusivi ad altri approcci di architettura. Ad esempio, un'architettura a più livelli può utilizzare microservizi per il livello intermedio. È anche possibile implementare microservizi in diversi modi, dalle directory virtuali negli host IIS ai contenitori. Le caratteristiche dei microservizi li rendono particolarmente ideali per le implementazioni senza server.

![Architettura di microservizi](./media/microservices-architecture.png)

I pro delle architetture di microservizi includono:

- Il refactoring è spesso isolato in un singolo servizio.
- I servizi possono essere aggiornati indipendentemente l'uno dall'altro.
- Resilienza ed elasticità possono essere sintonizzate sulle esigenze dei singoli servizi.
- Lo sviluppo può avvenire in parallelo su team e piattaforme diversi.
- È più semplice scrivere test completi per i servizi isolati.

I microservizi sono dotati di sfide proprie, tra cui:

- Determinare quali servizi sono disponibili e come chiamarli.
- Gestione del ciclo di vita dei servizi.
- Comprendere in che modo i servizi si incastrano nell'applicazione complessiva.
- Test completo del sistema delle chiamate effettuate attraverso servizi diversi.

In definitiva ci sono soluzioni per affrontare tutte queste sfide, tra cui attingere ai vantaggi di serverless che vengono discussi più avanti.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](architecture-deployment-approaches.md)
