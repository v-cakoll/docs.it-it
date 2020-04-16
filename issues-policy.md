---
ms.openlocfilehash: 33178637c4fcfb21e8190c3d2593f09326ea5995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73554848"
---
# <a name="github-issues-process-and-policy"></a>Processo e criteri dei problemi GitHub

Gli obiettivi del processo sono i seguenti:

1. Assicurarsi che gli errori o le omissioni nei documenti non impediscano ai clienti di operare correttamente.
1. Rispondere ai commenti e alle considerazioni dei clienti.
1. Migliorare costantemente l'esperienza dei clienti.
1. Usare la finestra di dialogo Apri relativa a problemi e soluzioni per conoscere le esperienze dei clienti.

Il processo usa due fasi per assicurare velocità di risposta e al tempo stesso assegnare priorità al lavoro. La prima fase esegue la diagnosi del problema e lo valuta. La seconda fase risolve il problema. Quando un problema è sia semplice che urgente, è possibile combinare le due fasi.

Il processo implica attività con allocazioni di tempo fisse:

- Ogni membro del team dedica fino a mezz'ora al giorno lavorativo alla [classificazione dei problemi in ingresso](#diagnosis-phase). Sono incluse le risposte iniziali. In questo modo si garantisce velocità di risposta a nuovi problemi.
- Ogni membro del team dedica fino a mezza giornata alla settimana all'[aggiornamento dei documenti](#resolution-phase) al fine di risolvere i problemi di GitHub generati dai clienti.

## <a name="diagnosis-phase"></a>Fase di diagnosi

Ogni membro del team dedica fino a 30 minuti al giorno lavorativo alla categorizzazione di nuovi problemi. Si risponde alle domande seguenti:

- Il problema riguarda la documentazione o un prodotto?
- Non si tratta di un problema, ma di una domanda più adatta per un forum o un sito di supporto?
- Qual è la priorità del problema?
- Quale area gestisce questo tipo di problema?

Se non è possibile rispondere a queste domande nella valutazione iniziale, si chiedono chiarimenti nei commenti.

Esistono tipi di problemi che vengono chiusi durante la fase di diagnosi e valutazione:

- **complimenti**: Esprimiamo grazie, e chiudiamo il problema.
- **problema del prodotto**: I problemi relativi al prodotto e non alla relativa documentazione vengono chiusi. Si possono anche intraprendere azioni aggiuntive, come descritto di seguito.
- **Violazioni del CoC**: Questi problemi vengono chiusi e segnalati se la violazione del [CoC](https://dotnetfoundation.org/code-of-conduct) merita segnalazione e blocco.
- **duplicati**: I duplicati vengono chiusi con un commento che fa riferimento al problema esistente.
- **doc-ok**: Il cliente non è corretto e il documento è corretto.
- **forum**: I problemi che sono il supporto o le richieste del forum vengono indirizzati a Overflow dello stack o ad altri siti di supporto e chiusi.

### <a name="actions-on-product-issues"></a>Azioni su problemi del prodotto

A seconda della natura del problema del prodotto, è possibile scegliere una delle azioni seguenti:

- Trasferire il problema al repository del prodotto appropriato.
- Chiudere il problema come duplicato di richieste di prodotto esistenti.
- Chiudere il problema e consigliare di aprirlo nel repository del prodotto.

La valutazione sul comportamento corretto da assumere è soggettiva. L'azione corretta da intraprendere è a discrezione dei membri del team.

### <a name="actions-on-content-issues"></a>Azioni su problemi di contenuto

Per altri problemi, il team agisce nel modo seguente:

- Assegna una priorità
- Assegna un'attività cardine, in genere "backlog"
- Valuta se si tratta effettivamente di un problema oppure considera i [progetti per i collaboratori della community .NET](https://github.com/dotnet/docs/projects/35)

I livelli di priorità si basano sulle linee guida seguenti, ma sono soggettivi. Anche le attività cardine sono soggettive e si basano su altre priorità, ad esempio pianificazioni di rilasci di prodotti correnti e lanci imminenti.

- **P0:** Un errore osullpa la documentazione impedisce ai clienti di avere esito positivo in uno scenario comune.
  - I problemi **P0** vengono risolti entro le tre settimane successive, con precedenza rispetto al lavoro precedentemente pianificato.
- **P1:** Un errore osullisce o documenta rende uno scenario comune molto più difficile o blocca altri scenari noti.
  - I problemi **P1** vengono pianificati in modo tempestivo. Per i problemi P1 si pianifica spesso un'attività cardine imminente.
- **P2**: Problemi che causano piccoli inconvenienti o influiscono su un articolo con visualizzazione di pagina bassa.
  - I problemi **P2** vengono in genere corretti quando un articolo viene aggiornato per motivi di priorità più elevata.
- **P3**: Problemi che sono richieste per scenari di casi limite.
  - I problemi **P3** vengono inseriti nel backlog e vengono considerati per l'aggiornamento quando gli articoli vengono aggiornati per motivi di priorità più elevata.

I membri del team dedicano un tempo limitato alla diagnosi e alla valutazione, in modo da poter procedere con le attività pianificate. Ogni membro del team dedica al massimo 30 minuti al giorno alla diagnosi e alla valutazione.

L'etichetta **"disponibile"** viene applicata quando un problema è un valido candidato per un membro della community (possibilmente l'autore) affinché invii una correzione. Il membro del team che applica l'etichetta **"disponibile"** aiuterà e troverà qualcuno che supporti i membri della community a usare il processo di creazione di richiesta pull. I problemi etichettati come "disponibili" vengono spesso aggiunti ai [progetti dei collaboratori della community](https://github.com/dotnet/docs/projects/35)

> NOTA: abbiamo adottato solo di recente la convenzione precedente. La persona che ha aggiunto l'etichetta può fare riferimento a un altro membro del team che offrirà assistenza.

## <a name="resolution-phase"></a>Fase di risoluzione

I problemi generati dai clienti vengono considerati come parte della pianificazione delle attività programmate. Ogni membro del team alloca 4 ore alla settimana per risolvere i problemi di clienti che hanno la massima priorità.

La risoluzione del problema segue il livello di priorità assegnato durante la diagnosi. I problemi dei clienti in ingresso vengono classificati in ordine di priorità con altre attività pianificate di priorità simile

- **P0**: Non appena è ragionevole, durante le prossime tre settimane.
- **P1**: Programmato con altri lavori P1 pianificati. In genere significa nei tre mesi successivi.
- **P2**: Programmato con altri lavori P2 pianificati. I problemi P2 vengono regolarmente pianificati in base all'area e alla visibilità. I problemi P2 vengono più spesso risolti quando un articolo viene aggiornato.
- **P3**: Nessuna garanzia sulla data di fisso. Quando un articolo viene aggiornato, si esamina il backlog per altri problemi sullo stesso articolo.

I problemi possono essere riclassificati in base a nuovi commenti e suggerimenti e a dati sulla visibilità degli articoli.
