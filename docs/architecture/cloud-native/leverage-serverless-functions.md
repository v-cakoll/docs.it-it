---
title: Uso di funzioni serverless
description: Uso di funzioni senza server e di Azure in applicazioni native del cloud
ms.date: 04/13/2020
ms.openlocfilehash: 176499e3cd0349cd689b9d13d1c237a6343d13f3
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199742"
---
# <a name="leveraging-serverless-functions"></a>Uso di funzioni serverless

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nell'ambito della gestione dei computer fisici per sfruttare le funzionalità del cloud, le vite senza server sono alla fine estremo. L'unica responsabilità è il codice e si paga solo quando viene eseguito il codice. Funzioni di Azure offre un modo per creare funzionalità senza server nelle applicazioni native del cloud.

## <a name="what-is-serverless"></a>Cosa significa "senza server"?

Senza server è un modello di servizio relativamente nuovo cloud computing. Non significa che i server sono facoltativi. il codice viene comunque eseguito in un server in un punto qualsiasi. La differenza è che il team di applicazioni non è più in grado di gestire l'infrastruttura server. Al contrario, il fornitore del cloud è proprietario di questa responsabilità. Il team di sviluppo aumenta la produttività grazie a soluzioni aziendali per i clienti, senza plumbing.

L'elaborazione senza server USA contenitori senza stato attivati dagli eventi per ospitare i servizi. È possibile scalare in orizzontale e in per soddisfare la domanda in base alle esigenze. Le piattaforme senza server come funzioni di Azure hanno una stretta integrazione con altri servizi di Azure, come code, eventi e archiviazione.

## <a name="what-challenges-are-solved-by-serverless"></a>Quali problemi vengono risolti da server?

Le piattaforme senza server risolvono molti problemi costosi e dispendiosi in termini di tempo:

- Acquisto di computer e licenze software
- Housing, protezione, configurazione e manutenzione dei computer e dei requisiti di rete, alimentazione e A/C
- Applicazione di patch e aggiornamento dei sistemi operativi e del software
- Configurazione di server Web o servizi computer per ospitare il software dell'applicazione
- Configurazione del software dell'applicazione all'interno della piattaforma

Molte aziende allocano budget di grandi dimensioni per supportare le problematiche dell'infrastruttura hardware. Il passaggio al cloud può contribuire a ridurre i costi. lo spostamento di applicazioni in server senza server può essere utile per eliminarli.

## <a name="what-is-the-difference-between-a-microservice-and-a-serverless-function"></a>Qual è la differenza tra un microservizio e una funzione senza server?

In genere, un microservizio incapsula una funzionalità aziendale, ad esempio un carrello acquisti per un sito di eCommerce online. Espone più operazioni che consentono a un utente di gestire l'esperienza di acquisto. Una funzione, tuttavia, è un piccolo blocco di codice leggero che esegue un'operazione a scopo singolo in risposta a un evento.
I microservizi vengono in genere costruiti per rispondere alle richieste, spesso da un'interfaccia. Le richieste possono essere basate su HTTP REST o gRPC. I servizi senza server rispondono agli eventi. L'architettura basata su eventi è ideale per l'elaborazione di attività in background di breve durata.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>Quali scenari sono appropriati per i server?

Senza server espone singole funzioni a esecuzione breve richiamate in risposta a un trigger. Che li rende ideali per l'elaborazione di attività in background.

Un'applicazione potrebbe dover inviare un messaggio di posta elettronica come passaggio di un flusso di lavoro. Anziché inviare la notifica come parte di una richiesta di microservizio, inserire i dettagli del messaggio in una coda. Una funzione di Azure può rimuovere dalla coda il messaggio e inviare il messaggio di posta elettronica in modo asincrono. Questa operazione può migliorare le prestazioni e la scalabilità del microservizio. È possibile implementare il [livellamento del carico basato sulle code](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) per evitare colli di bottiglia correlati all'invio dei messaggi di posta elettronica. Questo servizio autonomo, inoltre, può essere riutilizzato come utilità in molte applicazioni diverse.

La messaggistica asincrona da code e argomenti è un modello comune per l'attivazione di funzioni senza server. Tuttavia, funzioni di Azure può essere attivato da altri eventi, ad esempio modifiche all'archivio BLOB di Azure. Un servizio che supporta il caricamento di immagini potrebbe avere una funzione di Azure responsabile dell'ottimizzazione delle dimensioni dell'immagine. La funzione può essere attivata direttamente da inserimenti nell'archivio BLOB di Azure, mantenendo la complessità delle operazioni di microservizio.

Molti servizi hanno processi a esecuzione prolungata come parte dei propri flussi di lavoro. Queste attività vengono spesso eseguite come parte dell'interazione dell'utente con l'applicazione. Queste attività possono forzare l'attesa dell'utente, con un impatto negativo sulla propria esperienza. L'elaborazione senza server offre un ottimo modo per spostare attività più lente all'esterno del ciclo interazione utente. Queste attività possono essere ridimensionate con la richiesta senza richiedere la scalabilità dell'intera applicazione.

## <a name="when-should-you-avoid-serverless"></a>Quando è consigliabile evitare senza server?

Le soluzioni senza server eseguono il provisioning e la scalabilità su richiesta. Quando viene richiamata una nuova istanza, l'avvio a freddo rappresenta un problema comune. Un inizio a freddo indica il periodo di tempo necessario per il provisioning di questa istanza. In genere, questo ritardo può essere di pochi secondi, ma può essere più lungo a seconda di diversi fattori. Una volta eseguito il provisioning, una singola istanza viene mantenuta attiva fino a quando riceve richieste periodiche. Tuttavia, se un servizio viene chiamato con minore frequenza, Azure può rimuoverlo dalla memoria e richiedere un avvio a freddo quando viene richiamato. Le partenze a freddo sono necessarie anche quando una funzione viene scalata in uscita in una nuova istanza.

La figura 3-10 Mostra un modello di avvio a freddo. Si notino i passaggi aggiuntivi necessari quando l'app è a freddo.

![](./media/cold-start-warm-start.png)
**Figura 3-10**di avvio a freddo e a caldo. Avvio a freddo rispetto all'avvio a caldo.

Per evitare che si avvii a freddo, è possibile passare da un [piano a consumo a un piano dedicato](https://azure.microsoft.com/blog/understanding-serverless-cold-start/). È anche possibile configurare una o più [istanze pre-surriscaldate](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) con l'aggiornamento del piano Premium. In questi casi, quando è necessario aggiungere un'altra istanza, è già attivo e pronto per l'uso. Queste opzioni consentono di attenuare il problema di avvio a freddo associato all'elaborazione senza server.

I provider di servizi cloud fatturano per server in base al tempo di esecuzione di calcolo e alla memoria utilizzata. Le operazioni a esecuzione prolungata o i carichi di lavoro con utilizzo elevato di memoria non sono sempre i migliori candidati per senza server. Le funzioni senza server favoriscono piccoli blocchi di lavoro che possono essere completati rapidamente. La maggior parte delle piattaforme senza server richiede il completamento delle singole funzioni entro pochi minuti. Per impostazione predefinita, funzioni di Azure è una durata di timeout di 5 minuti, che può essere configurata fino a 10 minuti. Il piano Premium di funzioni di Azure può attenuare questo problema, impostando i timeout predefiniti su 30 minuti con un limite superiore illimitato che può essere configurato. Il tempo di calcolo non è una data di calendario. Funzioni più avanzate con il [Framework di Durable Functions di Azure](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview?tabs=csharp) possono sospendere l'esecuzione in un corso di alcuni giorni. La fatturazione è basata sul tempo di esecuzione effettivo, quando la funzione viene riattivata e riprende l'elaborazione.

Infine, l'uso di funzioni di Azure per le attività dell'applicazione aggiunge complessità. Per prima cosa è consigliabile progettare l'applicazione con un progetto modulare, a regime di controllo libero. Quindi, identificare se i vantaggi offerti da server non sono disponibili per giustificare la complessità aggiuntiva.

>[!div class="step-by-step"]
>[Precedente](leverage-containers-orchestrators.md)
>[successivo](combine-containers-serverless-approaches.md)
