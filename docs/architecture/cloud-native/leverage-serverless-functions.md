---
title: Utilizzo di funzioni senza server
description: Uso di funzioni senza server e di Azure in applicazioni native del cloud
ms.date: 06/30/2019
ms.openlocfilehash: 61bf4db6d61160c7ec11ffa3f178cc3917ae6cf9
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182825"
---
# <a name="leveraging-serverless-functions"></a>Utilizzo di funzioni senza server

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nell'ambito della gestione di computer e sistemi operativi completi per sfruttare le funzionalità del cloud, la vita senza server è alla fine estremo, dove l'unica cosa che si è responsabile è il codice e si paga solo per il codice durante l'esecuzione. Funzioni di Azure offre un modo per creare funzionalità senza server nelle applicazioni. 

## <a name="what-is-serverless"></a>Che cos'è senza server?

L'elaborazione senza server non significa che non sia presente un server per l'esecuzione dell'applicazione. il codice viene comunque eseguito in un server. La distinzione è che il team di sviluppo di applicazioni non deve più preoccuparsi di gestire l'infrastruttura server. Le soluzioni di elaborazione senza server come funzioni di Azure consentono ai team di aumentare la produttività e consentire alle organizzazioni di ottimizzare le risorse e concentrarsi sulla distribuzione di soluzioni.

L'elaborazione senza server USA contenitori senza stato attivati da eventi per ospitare l'applicazione o parte dell'applicazione. Le piattaforme senza server possono aumentare e ridurre le prestazioni per soddisfare la domanda in base alle esigenze. Le piattaforme come funzioni di Azure offrono un accesso diretto facile ad altri servizi di Azure, come code, eventi e archiviazione.

## <a name="what-challenges-are-solved-by-serverless"></a>Quali problemi vengono risolti da server?

Senza server si tratta dell'astrazione definitiva dall'esecuzione di un hardware personalizzato. Gli sviluppatori possono concentrarsi esclusivamente sulla scrittura di codice per risolvere i problemi aziendali, senza preoccupazioni per le seguenti attività che potrebbero essere state necessarie per l'hosting dei propri server:

- Acquisto di computer e licenze software
- Housing, protezione, configurazione e manutenzione dei computer e dei requisiti di rete, alimentazione e A/C
- Applicazione di patch e aggiornamento dei sistemi operativi e del software
- Configurazione di server Web o servizi computer per ospitare il software dell'applicazione
- Configurazione del software dell'applicazione all'interno della piattaforma

Molte aziende usano dozzine di membri del personale e allocano budget di grandi dimensioni per supportare tali problemi di infrastruttura hardware. Il semplice passaggio al cloud elimina alcuni di questi problemi; lo spostamento delle applicazioni fino al server senza server eliminerà il resto.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>Quali scenari sono appropriati per i server?

Senza server vengono utilizzate singole funzioni a esecuzione breve chiamate in risposta a un trigger. Che li rende ideali per l'elaborazione di attività in background.

Ad esempio, un'applicazione potrebbe dover inviare un messaggio di posta elettronica come parte dell'elaborazione di una richiesta. Anziché inviare il messaggio di posta elettronica come parte della gestione della richiesta Web, i dettagli del messaggio di posta elettronica possono essere inseriti in una coda e una funzione di Azure può essere usata per prelevare il messaggio e inviare il messaggio di posta elettronica. Molte parti diverse dell'applicazione o anche molte applicazioni possono sfruttare questa stessa funzione di Azure, offrendo prestazioni e scalabilità migliorate per le applicazioni e usando il [livellamento del carico basato sulle code](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) per evitare colli di bottiglia correlati a invio dei messaggi di posta elettronica.

Sebbene un [modello di editore/sottoscrittore](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) tra applicazioni e funzioni di Azure sia il modello più comune, sono possibili altri modelli. Funzioni di Azure può essere attivato da altri eventi, ad esempio modifiche all'archivio BLOB di Azure. Un'applicazione che supporta il caricamento di immagini potrebbe avere una funzione di Azure responsabile della creazione di immagini di anteprima o il ridimensionamento delle immagini caricate in dimensioni coerenti o l'ottimizzazione delle dimensioni dell'immagine. Questa funzionalità può essere attivata direttamente da inserimenti nell'archivio BLOB di Azure, mantenendo la complessità e il carico di lavoro all'esterno dell'applicazione stessa.

Molte applicazioni hanno processi a esecuzione prolungata come parte dei propri flussi di lavoro. Spesso queste attività vengono eseguite nell'interazione dell'utente con l'applicazione, forzando l'utente ad attendere e a influire negativamente sulla propria esperienza. L'elaborazione senza server offre un ottimo modo per eseguire attività più lente al di fuori del ciclo interazione utente e queste attività possono essere facilmente ridimensionate con la richiesta senza richiedere la scalabilità dell'intera applicazione.

## <a name="when-should-you-avoid-serverless"></a>Quando è consigliabile evitare senza server?

L'elaborazione senza server è più usata per le attività che non bloccano l'interfaccia utente. Ciò significa che non sono ideali per ospitare direttamente le applicazioni Web o le API Web. Il motivo principale è che le soluzioni senza server vengono sottoposte a provisioning e ridimensionate su richiesta. Quando è necessaria una nuova istanza di una funzione, definita *avvio a freddo*, il provisioning richiede tempo. Questo tempo è in genere di pochi secondi, ma può essere più lungo a seconda di diversi fattori. Una singola istanza può spesso essere mantenuta a tempo indefinito (ad esempio, effettuando periodicamente una richiesta), ma il problema di avvio a freddo rimane se il numero di istanze deve essere ridimensionato.

![**Figura 3-10**di avvio](./media/cold-start-warm-start.png)
a freddo e a caldo. Avvio a freddo rispetto all'avvio a caldo.

Se è necessario evitare completamente l'avvio a freddo, è possibile scegliere di passare da un [piano a consumo a un piano dedicato](https://azure.microsoft.com/blog/understanding-serverless-cold-start/). È anche possibile [configurare una o più istanze già riscaldate](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) con il piano Premium, in modo che quando è necessario aggiungere un'altra istanza, il piano è già attivo e pronto per l'uso. Queste opzioni possono attenuare una delle problematiche principali associate all'elaborazione senza server.

Per le attività a esecuzione prolungata, è anche consigliabile evitare senza server. Sono ideali per piccoli pezzi di lavoro che possono essere completati rapidamente. La maggior parte delle piattaforme senza server richiede il completamento delle singole funzioni entro pochi minuti. Per impostazione predefinita, funzioni di Azure è una durata di timeout di 5 minuti (può essere configurata fino a 10 minuti). Il piano Premium di funzioni di Azure può attenuare questo problema, impostando come predefiniti i timeout per 30 minuti e consentendo la configurazione di un limite superiore non vincolato.

Infine, l'uso di server per determinate attività all'interno dell'applicazione aggiunge complessità. Spesso è preferibile progettare l'applicazione in modo modulare, a regime di controllo libero e quindi identificare se i vantaggi offerti dai server non sono più utili per la complessità aggiuntiva. Molte applicazioni più piccole vengono eseguite perfettamente in un'unica distribuzione monolitica, senza la necessità di un'architettura dell'applicazione distribuita che richiede l'elaborazione senza server.

## <a name="references"></a>Riferimenti

- [Informazioni sull'avvio a freddo senza server](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Istanze di funzioni di Azure pre-surriscaldate](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Creare una funzione in Linux usando un'immagine personalizzata](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)

>[!div class="step-by-step"]
>[Precedente](leverage-containers-orchestrators.md)
>[Successivo](combine-containers-serverless-approaches.md)
