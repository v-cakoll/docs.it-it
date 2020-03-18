---
title: Identificazione dei limiti del modello di dominio per ogni microservizio
description: Esplorare l'essenza del partizionamento di un'applicazione di grandi dimensioni in microservizi per ottenere un'architettura solida.
ms.date: 09/20/2018
ms.openlocfilehash: 9c433066dd8e93dbb09b15e58c9c85617775723d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834410"
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identificare i limiti del modello di dominio per ogni microservizio

L'obiettivo durante l'identificazione dei limiti e delle dimensioni del modello per ogni microservizio non è quello di ottenere la separazione più granulare possibile, benché sia consigliabile, se possibile, tendere a microservizi di piccole dimensioni, ma piuttosto quello di ottenere la separazione più significativa guidata dalla propria conoscenza del dominio. L'accento viene posto non sulle dimensioni, ma piuttosto sulle funzionalità aziendali. Per di più, se è necessaria una chiara coesione per una determinata area dell'applicazione basata su un numero elevato di dipendenze, si evince la necessità di un singolo microservizio. La coesione è un modo per identificare come suddividere o raggruppare i microservizi. In definitiva, mentre si acquisiscono altre informazioni sul dominio, occorre adattare le dimensioni del microservizio in modo iterativo. Trovare le dimensioni giuste non è un processo facile.

[Sam Newman](https://samnewman.io/), promotore riconosciuto dei microservizi e autore del libro [Building Microservices](https://samnewman.io/books/building_microservices/), evidenzia la necessità di progettare i propri microservizi in base allo schema Bounded Context (BC), cioè una parte della progettazione basata su domini, già introdotta in precedenza. In alcuni casi, un BC potrebbe essere composto da diversi servizi fisici, ma non viceversa.

Un modello di dominio con entità di dominio specifiche si applica all'interno di un BC o microservizio concreto. Un BC delimita l'applicabilità di un modello di dominio e offre ai membri del team di sviluppo una comprensione chiara e condivisa di ciò che deve essere coeso e di ciò che può essere sviluppato in modo indipendente. Sono gli stessi obiettivi per i microservizi.

Un altro strumento che informa la scelta di progettazione è la [legge di Conway](https://en.wikipedia.org/wiki/Conway%27s_law), che asserisce che un'applicazione rifletterà i limiti sociali dell'organizzazione che l'ha prodotta. Ma in alcuni casi è vero il contrario: l'organizzazione dell'azienda è costituita dal software. Potrebbe essere necessario invertire la legge di Conway e creare i limiti nel modo in cui si vuole organizzare l'azienda, propendendo per la consulenza sui processi aziendali.

Per identificare i contesti limitati, è possibile usare uno schema DDD denominato [Context Mapping](https://www.infoq.com/articles/ddd-contextmapping), ovvero "mapping del contesto". Con il mapping del contesto è possibile identificare i vari contesti nell'applicazione e nei relativi limiti. È comune, ad esempio, avere contesto e limiti diversi per ogni piccolo sottosistema. La mappa del contesto è un modo per definire e rendere espliciti tali limiti tra un dominio e l'altro. Un BC è autonomo e include i dettagli di un singolo dominio, ad esempio le entità di dominio, e definisce i contratti di integrazione con altri BC. Questa operazione è simile alla definizione di un microservizio: è autonomo, implementa alcune funzionalità del dominio e deve specificare le interfacce. Ecco perché gli schemi Context Mapping e Bounded Context rappresentano ottimi approcci all'identificazione dei limiti del modello di dominio dei microservizi.

Quando si progetta un'applicazione di grandi dimensioni, viene visualizzato il modo in cui è possibile frammentare il modello di dominio. Ad esempio, un esperto di dominio dal dominio del catalogo assegnerà nomi diversi alle entità nei domini del catalogo e dell'inventario rispetto a un esperto dei domini di spedizione. In alternativa, l'entità del dominio utente potrebbe differire nelle dimensioni e nel numero di attributi quando gestita da un esperto CRM che volesse archiviare ogni dettaglio sul cliente rispetto a un esperto di dominio che necessitasse solo di dati parziali sul cliente. È molto difficile evitare ambiguità tra tutti i termini di dominio in tutti i domini correlati a un'applicazione di grandi dimensioni. Ma la cosa più importante è che non si deve provare a unificare i termini. Accettare invece le differenze e la ricchezza offerte da ogni dominio. Se si prova a unificare un database per l'intera applicazione, i tentativi di ottenere un vocabolario unificato saranno maldestri e non avranno alcun significato per nessuno degli esperti di domini. Di conseguenza, i BC (implementati come microservizi) aiutano a chiarire dove è possibile usare alcuni termini di dominio e dove è invece necessario suddividere il sistema e creare altri BC con domini diversi.

Si può dedurre che sono stati ottenuti i limiti e le dimensioni giusti per ogni BC e modello di dominio quando sono presenti poche relazioni forti tra modelli di dominio e solitamente non è necessario unire le informazioni di più modelli di dominio quando si eseguono operazioni di applicazioni tipiche.

Probabilmente la risposta migliore alla domanda su quali dovrebbero essere le dimensioni di un modello di dominio per ogni microservizio è la seguente: deve contenere un BC autonomo, che consente di lavorare senza dover continuamente passare ad altri contesti (altri modelli di microservizio). Nella figura 4-10 è possibile osservare che ciascuno dei molteplici microservizi (più BC) ha il proprio modello e che è possibile definire le relative entità, a seconda dei requisiti specifici per ognuno dei domini identificati nell'applicazione.

![Diagramma che mostra le entità in diversi contorni del modello.](./media/identify-microservice-domain-model-boundaries/identify-entities-microservice-model-boundries.png)

**Figura 4-10**. Identificazione di entità e dei limiti del modello di microservizio

La figura 4-10 illustra un esempio di scenario correlato a un sistema di gestione di conferenze online. La stessa entità viene visualizzata come "Utenti", "Acquirenti", "Pagamenti" e "Clienti" a seconda del contesto limitato. Sono stati identificati diversi BC implementabili come microservizi, in base ai domini definiti per l'utente dagli esperti di dominio. Come si può notare, ci sono entità presenti solo in un modello di microservizio singolo, ad esempio Payments nel microservizio Payment, che saranno facili da implementare.

Tuttavia, potrebbero esserci anche entità con una forma differente, ma che condividono la stessa identità tra più modelli di dominio di più microservizi. Ad esempio, l'entità User viene identificata nel microservizio Conferences Management. Lo stesso utente, con la stessa identità, è quello denominato Buyers nel microservizio degli ordini o Payer nel microservizio Payment, e persino quello denominato Customer nel microservizio Customer Service. Questo avviene perché, a seconda del [linguaggio comune](https://martinfowler.com/bliki/UbiquitousLanguage.html) usato da ogni esperto di dominio, un utente potrebbe avere una prospettiva diversa, anche con attributi diversi. L'entità utente nel modello di microservizio denominato Conferences Management potrebbe contenere la maggior parte dei relativi attributi dati personali. Tuttavia, lo stesso utente sotto forma di Payer nel microservizio Payment o sotto forma di Customer nel microservizio Customer Service potrebbe non aver bisogno dello stesso elenco di attributi.

Un approccio simile è illustrato nella figura 4-11.

![Diagramma che illustra come scomporre un modello di dati in più modelli di dominio.](./media/identify-microservice-domain-model-boundaries/decompose-traditional-data-models.png)

**Figura 4-11**. Scomposizione di modelli di dati tradizionali in più modelli di dominio

Quando si scompone un modello di dati tradizionali tra contesti delimitati, è possibile avere diverse entità che condividono la stessa identità (un acquirente è anche un utente) con attributi diversi in ogni contesto delimitato. Come si può osservare, l'utente è presente nel modello di microservizio Conferences Management come entità User, ma anche sotto forma di entità Buyer nel microservizio Pricing, con attributi o dettagli alternativi sull'utente quando si tratta effettivamente di un acquirente. Ogni microservizio o BC potrebbe non necessitare di tutti i dati relativi a un'entità User, ma solo di parte di essi, a seconda del contesto o del problema da risolvere. Ad esempio, nel modello di microservizio Pricing, non è necessario l'indirizzo o il nome dell'utente, ma sono sufficienti solo l'ID (come identità) e lo stato, che avranno un impatto sugli sconti quando si determinano i prezzi delle postazioni per ogni acquirente.

L'entità Seat ha lo stesso nome, ma diversi attributi in ciascun modello di dominio. Tuttavia, questa entità condivide l'identità basata sullo stesso ID, così come accade con User e Buyer.

In pratica, è un concetto condiviso di utente esistente in più servizi (domini), che condividono tutti l'identità di tale utente. Ma in ogni modello di dominio potrebbero essere presenti informazioni aggiuntive o diverse su tale entità utente. Di conseguenza, deve esserci un modo per eseguire il mapping di un'entità utente da un dominio (microservizio) a un altro.

La mancata condivisione tra domini della stessa entità utente con lo stesso numero di attributi comporta diversi vantaggi. Uno dei vantaggi consiste nella riduzione delle duplicazioni, così che i modelli di microservizio non contengano alcun dato superfluo. Un altro vantaggio consiste nell'avere un microservizio master che sia proprietario di un certo tipo di dati per ogni entità, in modo che gli aggiornamenti e le query per tale tipo di dati siano basati solo su tale microservizio.

>[!div class="step-by-step"]
>[Successivo](distributed-data-management.md)
>[precedente](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
