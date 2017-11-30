---
title: Identificazione dei limiti di modello di dominio per ogni microservizio
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Identificazione dei limiti di modello di dominio per ogni microservizio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6fef11e5718706701abb29149c4c4a23ba39bde0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identificare i limiti di modello di dominio per ogni microservizio

L'obiettivo quando si identificano i limiti di modello e la dimensione di ogni microservizio è non per ottenere la separazione più granulare possibile, anche se si deve tende verso microservizi piccolo se possibile. Al contrario, l'obiettivo dovrebbe essere per ottenere la separazione di più significativa interattiva per le informazioni sul dominio. Non viene sulle dimensioni, ma le funzionalità di business. Inoltre, se è chiaro coesione necessari per una determinata area dell'applicazione in base a un numero elevato di dipendenze, che indica la necessità di un singolo microservizio, troppo. Coesione è un modo per identificare come separare o gruppo di microservizi insieme. Infine, ottenere ulteriori informazioni sul dominio, è necessario adattare le dimensioni del microservizio, in modo iterativo. Individuazione della dimensione giusta non è un processo monofase.

[SAM Newman](http://samnewman.io/), un promotore riconosciuto di microservizi e l'autore del libro [Microservizi compilazione](http://samnewman.io/books/building_microservices/), viene evidenziato che è necessario progettare il microservizi basato sul modello di contesto limitato (BC) (parte di basati su dominio progettazione), come descritto in precedenza. In alcuni casi, a BC potrebbe essere composte di diversi servizi fisici, ma non viceversa.

Si applica un modello di dominio con le entità di dominio specifico all'interno di un BC concreti o microservizio. Un BC delimita l'applicabilità di un modello di dominio e i membri del team developer offre una comprensione chiara e condivisa della quale deve essere coerente e cosa possono essere sviluppata in modo indipendente. Questi sono gli stessi obiettivi per microservizi.

Un altro strumento che segnala la scelta di progettazione è [legge di Conway](https://en.wikipedia.org/wiki/Conway%27s_law), che indica che un'applicazione non rifletteranno i limiti dell'organizzazione che ha prodotto sociali. Ma in alcuni casi è vero il contrario: organizzazione della società è costituita da software. Potrebbe essere necessario invertire legge di Conway e i limiti di compilazione nel modo desiderato all'azienda di essere organizzate, inclinati verso consulenza per processi di business.

Per identificare i contesti delimitati, un modello DDD che può essere utilizzato per questo è il [contesto Mapping modello](https://www.infoq.com/articles/ddd-contextmapping). Con il Mapping di contesto, si identificano i vari contesti in cui l'applicazione e i loro limiti. È comune disporre di un limite per ogni sottosistema, piccolo e un contesto diverso per l'istanza. La mappa di contesto è un modo per definire e rendere esplicito tali limiti tra domini. Un BC è autonomo e include i dettagli di un singolo dominio, dettagli come le entità di dominio e definisce contratti di integrazione con altri BCs. Questa operazione è simile alla definizione di un microservizio: è autonomo, implementa alcune funzionalità del dominio e deve fornire le interfacce. Ecco perché il Mapping di contesto e il criterio di contesto delimitata sono approcci corretti per identificare i limiti del modello di dominio del microservizi.

Quando si progetta un'applicazione di grandi dimensioni, verrà visualizzato come il modello di dominio possa essere frammentato, ovvero un esperto di dominio del dominio di catalogo il nome entità in modo diverso nei domini di catalogo e inventario rispetto a un dominio di spedizione esperto di dominio, per l'istanza. O l'entità utente di dominio potrebbe essere diverso in dimensioni e il numero di attributi quando si lavora con CRM esperti che desiderano archiviare ogni dettaglio sul cliente rispetto a per un ordinamento esperto di dominio che è necessario impostare solo dati parziali sul cliente. È molto difficile evitare ambiguità tra tutti i termini di dominio in tutti i domini correlati a un'applicazione di grandi dimensioni. Ma la cosa più importante è che non tentare di unificare le condizioni; al contrario, accettare le differenze e ricchezza fornite da ogni dominio. Se si tenta di disporre di un database unificato per l'intera applicazione, tentativi di un vocabolario unificato saranno difficili e non saranno chiaro a uno dei più esperti di dominio. Pertanto, BCs (implementato come microservizi) consentirà di chiarire in cui è possibile utilizzare alcuni termini di dominio e in cui è necessario suddividere il sistema e creare ulteriori BCs con domini diversi.

Si saprà che è stato ottenuto i limiti di destra e le dimensioni di ogni BC e modello di dominio se si dispone di alcune relazioni complesse tra i modelli di dominio e in genere non si desidera unire le informazioni da più modelli di dominio durante l'esecuzione di una tipica applicazione operazioni.

Ad esempio la risposta alla domanda di dimensioni deve essere un modello di dominio per ogni microservizio migliore è il seguente: deve essere un BC autonomi, isolata possibili, che consente di lavorare senza dover costantemente passare ad altri contesti (altro modelli del microservizio). Nella figura 4-10 è possibile visualizzare la modalità più microservizi (più BCs) ogni hanno i propri modelli e come è possono definire le relative entità, a seconda dei requisiti specifici per ogni dominio identificato nell'applicazione.

![](./media/image10.png)

**Figura 4-10**. Identificazione di entità e i limiti di modello microservizio

Figura 4-10 è illustrato uno scenario di esempio relative a un sistema di gestione di conferenza in linea. È stato identificato BCs diversi che possa essere implementata come microservizi, in base al dominio che gli esperti di dominio definiti per l'utente. Come si può notare, vi sono entità che sono presenti solo in un modello di microservizio singolo, ad esempio pagamenti in microservizio il pagamento. Quelli sarà facili da implementare.

Tuttavia, potrebbe essere anche le entità che dispongono di una forma diversa ma condividono la stessa identità tra più modelli di dominio da di microservizi più. Ad esempio, l'entità utente viene identificato in microservizio la gestione di conferenze. Dello stesso utente, con la stessa identità, è quello denominato acquirenti in microservizio l'ordinamento o quello denominato Payer microservizio il pagamento e anche di un cliente denominato in microservizio il servizio clienti. Questo avviene perché, a seconda di [linguaggio universale](https://martinfowler.com/bliki/UbiquitousLanguage.html) che usa ogni esperto di dominio, un utente potrebbe avere una prospettiva diversa, anche con attributi diversi. L'entità utente nel modello microservizio denominato gestione conferenze potrebbe essere la maggior parte dei relativi attributi dati personali. Tuttavia, nella forma del contribuente microservizio pagamento o nella forma del cliente microservizio servizio clienti dello stesso utente potrebbe non essere necessario lo stesso elenco di attributi.

Un approccio simile è illustrato nella figura 4-11.

![](./media/image11.png)

**Figura 4-11**. La scomposizione di modelli di dati tradizionali in più modelli di dominio

Si può notare come l'utente è presente nel modello microservizio conferenze gestione dell'entità utente è anche presente nel modulo dell'entità dell'acquirente in microservizio i prezzi, con attributi alternativi o i dettagli relativi all'utente quando è effettivamente un acquirente. Ogni microservizio o BC potrebbe non essere necessario tutti i dati relativi a un'entità utente solo parte di esso, a seconda del contesto o di problema da risolvere. Ad esempio, nel modello di determinazione dei prezzi microservizio, non è necessario l'indirizzo o l'ID dell'utente, è sufficiente ID (identità) e lo stato, che hanno un impatto su sconti prezzi alle postazioni per acquirente.

L'entità postazione ha lo stesso nome e attributi diversi in ogni modello di dominio. Tuttavia, postazione condivide identità in base all'ID stesso, come accade con l'utente e l'acquirente.

In pratica, è un concetto condiviso di un utente esistente in più servizi (domini), che condividono l'identità dell'utente. Ma in ogni modello di dominio potrebbero essere presenti informazioni aggiuntive o diverse entità utente. Pertanto, è necessario un modo per eseguire il mapping di un'entità utente da un dominio (microservizio) a un altro.

Esistono diversi vantaggi alle non condividere la stessa entità utente con lo stesso numero di attributi tra domini. Un vantaggio è ridurre la duplicazione, in modo che i modelli di microservizio non dispone di tutti i dati che non richiedono. Un altro vantaggio è che un microservizio master a cui appartiene un determinato tipo di dati per ogni entità in modo che gli aggiornamenti e query per il tipo di dati sono dovute solo tale microservizio.


>[!div class="step-by-step"]
[Precedente] (distributed-data-management.md) [Avanti] (direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
