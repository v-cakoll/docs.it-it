---
title: Resilienza della piattaforma Azure
description: Architettura di app .NET cloud native per Azure | Resilienza dell'infrastruttura cloud con Azure
ms.date: 06/30/2019
ms.openlocfilehash: 8b33c1cec1633c9fb25ae2b02e51f8be01c22941
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337382"
---
# <a name="azure-platform-resiliency"></a>Resilienza della piattaforma Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La creazione di un'applicazione affidabile nel cloud è diversa dallo sviluppo tradizionale di applicazioni locali. Mentre in passato è stato acquistato hardware di fascia superiore per la scalabilità verticale, in un ambiente cloud viene scalato in orizzontale. Invece di tentare di impedire errori, l'obiettivo è ridurre al minimo gli effetti e assicurare la stabilità del sistema.

Detto questo, le applicazioni cloud affidabili visualizzano caratteristiche distinte:

- Sono resilienti, si ripristinano normalmente dai problemi e continuano a funzionare.
- Sono a disponibilità elevata e vengono eseguiti come progettato in uno stato integro senza tempi di inattività significativi.

Comprendere il modo in cui queste caratteristiche interagiscono e il modo in cui influiscono sui costi è essenziale per la creazione di un'applicazione cloud nativa affidabile. Verranno ora esaminati i modi in cui è possibile creare resilienza e disponibilità nelle applicazioni native del cloud sfruttando le funzionalità del cloud di Azure.

## <a name="design-with-redundancy"></a>Progettazione con ridondanza

Gli errori variano nell'ambito dell'effetto. Un errore hardware, ad esempio un disco guasto, può interessare un singolo nodo in un cluster. Uno switch di rete con errore potrebbe influire su un intero rack server. Errori meno comuni, ad esempio la perdita di energia, potrebbero causare l'interruzione di un intero data center. Raramente, un'intera area diventa non disponibile.

La [ridondanza](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) è un modo per garantire la resilienza dell'applicazione. Il livello di ridondanza esatto necessario dipende dai requisiti aziendali e influirà sia sui costi che sulla complessità del sistema. Ad esempio, una distribuzione in più aree è più costosa e più complessa da gestire rispetto a una distribuzione in una singola area. Sono necessarie procedure operative per gestire il failover e il failback. L'incremento dei costi e la maggiore complessità potrebbero essere giustificabili per alcuni scenari aziendali e non per altri.

Per la ridondanza degli architetti, è necessario identificare i percorsi critici nell'applicazione e quindi determinare se è presente una ridondanza in ogni punto del percorso. Se un sottosistema ha esito negativo, verrà eseguito il failover dell'applicazione in un altro? Infine, è necessario conoscere in modo chiaro le funzionalità incorporate nella piattaforma cloud di Azure che è possibile sfruttare per soddisfare i requisiti di ridondanza. Di seguito sono riportati alcuni suggerimenti per l'architettura della ridondanza:

- *Distribuire più istanze di servizi.* Se l'applicazione dipende da una singola istanza di un servizio, crea un singolo punto di errore. Il provisioning di più istanze migliora sia la resilienza che la scalabilità. Quando si esegue l'hosting nel servizio Azure Kubernetes, è possibile configurare in modo dichiarativo istanze ridondanti (set di repliche) nel file manifesto Kubernetes. Il valore del numero di repliche può essere gestito a livello di codice, nel portale o tramite le funzionalità di scalabilità automatica, che verranno discusse in un secondo momento.

- *Uso di un servizio di bilanciamento del carico.* Il bilanciamento del carico distribuisce le richieste dell'applicazione a istanze del servizio integre e rimuove automaticamente le istanze non integre dalla rotazione. Quando si esegue la distribuzione in Kubernetes, il bilanciamento del carico può essere specificato nel file manifesto Kubernetes nella sezione dei servizi.

- *Pianificare la distribuzione in più aree.* Se l'applicazione viene distribuita in una singola area e l'area non è più disponibile, anche l'applicazione non sarà più disponibile. Questo può essere inaccettabile in base alle condizioni dei contratti di servizio dell'applicazione. In alternativa, è consigliabile distribuire l'applicazione e i relativi servizi in più aree. Ad esempio, un cluster Azure Kubernetes Service (AKS) viene distribuito in una singola area. Per proteggere il sistema da un errore a livello di area, è possibile distribuire l'applicazione in più cluster AKS in aree diverse e usare la funzionalità [aree abbinate](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) per coordinare gli aggiornamenti della piattaforma e assegnare priorità ai tentativi di ripristino.

- *Abilitare la [replica geografica](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication).* La replica geografica per servizi quali il database SQL di Azure e Cosmos DB creerà le repliche secondarie dei dati in più aree. Mentre entrambi i servizi eseguiranno automaticamente la replica dei dati all'interno della stessa area, la replica geografica proteggerà l'utente da un'interruzione a livello di area consentendo di eseguire il failover in un'area secondaria. Un'altra procedura consigliata per la replica geografica si concentra sull'archiviazione delle immagini del contenitore. Per distribuire un servizio in AKS, è necessario archiviare ed eseguire il pull dell'immagine da un repository. Azure Container Registry si integra con AKS ed è in grado di archiviare in modo sicuro le immagini del contenitore. Per migliorare le prestazioni e la disponibilità, prendere in considerazione la replica geografica delle immagini in un registro in ogni area in cui si dispone di un cluster AKS. Ogni cluster AKS estrae quindi le immagini del contenitore dal registro contenitori locale nella propria area, come illustrato nella figura 6-6:

![Risorse replicate tra le aree](./media/replicated-resources.png)

**Figura 6-6**. Risorse replicate tra le aree

- *Implementare un servizio di bilanciamento del carico del traffico DNS.* [Gestione traffico di Azure](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) offre disponibilità elevata per le applicazioni critiche tramite il bilanciamento del carico a livello di DNS. Può instradare il traffico a aree diverse in base a geografia, tempo di risposta del cluster e anche integrità dell'endpoint dell'applicazione. Gestione traffico di Azure, ad esempio, può indirizzare i clienti al cluster AKS più vicino e all'istanza dell'applicazione. Se si dispone di più cluster AKS in aree diverse, usare gestione traffico per controllare il flusso del traffico verso le applicazioni in esecuzione in ogni cluster. Nella figura 6-7 è illustrato questo scenario.

![AKS e gestione traffico di Azure](./media/aks-traffic-manager.png)

**Figura 6-7**. AKS e gestione traffico di Azure

## <a name="design-for-scalability"></a>Progettazione per la scalabilità

Il cloud si sviluppa in scala. La possibilità di aumentare o ridurre le risorse di sistema per risolvere un carico di sistema crescente/decrescente è un principio fondamentale del cloud di Azure. Tuttavia, per ridimensionare in modo efficace un'applicazione, è necessario conoscere le funzionalità di scalabilità di ogni servizio di Azure incluso nell'applicazione.  Ecco alcuni suggerimenti per implementare efficacemente il ridimensionamento nel sistema.

- *Progettazione per la scalabilità.* Un'applicazione deve essere progettata per la scalabilità. Per iniziare, i servizi devono essere senza stato, in modo che le richieste possano essere indirizzate a qualsiasi istanza. La presenza di servizi senza stato significa anche che l'aggiunta o la rimozione di un'istanza non influisce negativamente sugli utenti correnti.

- *Carichi di lavoro della partizione*. La scomposizione dei domini in microservizi indipendenti e indipendenti permette a ogni servizio di ridimensionarsi in modo indipendente dagli altri. In genere, i servizi avranno esigenze e requisiti di scalabilità diversi. Il partizionamento consente di ridimensionare solo gli elementi che è necessario ridimensionare senza il costo superfluo di ridimensionare un'intera applicazione.

- *Ottimizza la scalabilità orizzontale.* Le applicazioni basate sul cloud favoriscono la scalabilità orizzontale delle risorse anziché la scalabilità verticale. La scalabilità orizzontale (detta anche scalabilità orizzontale) comporta l'aggiunta di altre risorse del servizio a un sistema esistente per soddisfare e condividere un livello di prestazioni desiderato. La scalabilità verticale (anche nota come scalabilità verticale) comporta la sostituzione delle risorse esistenti con hardware più potente (più core di disco, memoria e elaborazione). La scalabilità orizzontale può essere richiamata automaticamente con le funzionalità di scalabilità automatica disponibili in alcune risorse cloud di Azure. La scalabilità orizzontale in più risorse consente inoltre di aggiungere ridondanza al sistema globale. Infine, la scalabilità verticale di una singola risorsa è in genere più costosa rispetto alla scalabilità orizzontale in molte risorse più piccole. La figura 6-8 illustra i due approcci seguenti:

![Scalabilità verticale rispetto a scalabilità orizzontale](./media/scale-up-scale-out.png)

**Figura 6-8.** Scalabilità verticale rispetto a scalabilità orizzontale

- *Ridimensiona proporzionalmente.* Quando si ridimensiona un servizio, è opportuno pensare in termini di *set di risorse*. Se fosse necessario scalare in modo significativo un servizio specifico, quale impatto avrebbe sugli archivi dati back-end, le cache e i servizi dipendenti? Alcune risorse, ad esempio Cosmos DB possono scalare in modo proporzionale, mentre molte altre non possono. Si desidera assicurarsi di non aumentare la scalabilità orizzontale di una risorsa fino a un punto in cui si esauriranno altre risorse associate.

- *Evitare l'affinità.* Una procedura consigliata consiste nel garantire che un nodo non richieda affinità locale, spesso definita *sessione*permanente. Una richiesta deve essere in grado di indirizzare a qualsiasi istanza. Se è necessario salvare lo stato, è necessario salvarlo in una cache distribuita, ad esempio [cache Redis di Azure](https://azure.microsoft.com/services/cache/).

- *Sfrutta i vantaggi delle funzionalità di scalabilità automatica della piattaforma.* Usare le funzionalità di scalabilità automatica predefinite, laddove possibile, anziché meccanismi personalizzati o di terze parti. Laddove possibile, usare le regole di scalabilità pianificate per garantire che le risorse siano disponibili senza un ritardo di avvio, ma aggiungere la scalabilità automatica reattiva alle regole in base alle esigenze, per gestire modifiche impreviste della richiesta. Per altre informazioni, vedere [linee guida per la scalabilità](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)automatica.

- *Scalabilità orizzontale in modo aggressivo.* Una procedura finale è la scalabilità orizzontale in modo aggressivo, in modo che sia possibile raggiungere rapidamente i picchi di traffico immediatamente senza perdere il business. E, quindi applicare la scalabilità (ovvero rimuovere le istanze non necessarie) in modo conservativo per assicurare la stabilità del sistema. Un modo semplice per implementare questa operazione consiste nell'impostare il periodo di raffreddamento, ovvero il tempo di attesa tra le operazioni di ridimensionamento, fino a cinque minuti per l'aggiunta di risorse e fino a 15 minuti per la rimozione di istanze.

## <a name="built-in-retry-in-services"></a>Tentativi predefiniti nei servizi

È stata consigliata la procedura consigliata per implementare le operazioni di ripetizione a livello di codice in una sezione precedente. Tenere presente che molti servizi di Azure e gli SDK client corrispondenti includono anche meccanismi di ripetizione dei tentativi. L'elenco seguente riepiloga le funzionalità di ripetizione dei tentativi nei molti servizi di Azure trattati in questo libro:

- *Azure Cosmos DB.* La classe <xref:Microsoft.Azure.Documents.Client.DocumentClient> dall'API client ritira automaticamente i tentativi non riusciti. Il numero di tentativi e il tempo massimo di attesa sono configurabili. Le eccezioni generate dall'API client sono richieste che superano i criteri di ripetizione o gli errori non temporanei.

- *Cache Redis di Azure.* Il client Redis StackExchange usa una classe di gestione connessione che include tentativi per i tentativi non riusciti. Il numero di tentativi, i criteri di ripetizione e il tempo di attesa specifici sono configurabili.

- *Bus di servizio di Azure.* Il client del bus di servizio espone una [classe RetryPolicy](xref:Microsoft.ServiceBus.RetryPolicy) che può essere configurata con un intervallo di back-off, un numero di tentativi e un <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer%2A>, che specifica il tempo massimo che un'operazione può assumere. I criteri predefiniti sono nove tentativi di ripetizione massimi con un periodo di backoff di 30 secondi tra i tentativi.

- *Database SQL di Azure* Quando si usa la libreria [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) , viene fornito il supporto per i tentativi.

- *Archiviazione di Azure.* La libreria client di archiviazione supporta le operazioni di ripetizione dei tentativi. Le strategie variano tra le tabelle, i BLOB e le code di archiviazione di Azure. Inoltre, i tentativi alternativi passano tra i percorsi di servizi di archiviazione primari e secondari quando è abilitata la funzionalità di ridondanza geografica.

- *Hub eventi di Azure.* La libreria client dell'hub eventi presenta una proprietà RetryPolicy, che include una funzionalità backoff esponenziale configurabile.

>[!div class="step-by-step"]
>[Precedente](application-resiliency-patterns.md)
>[Successivo](resilient-communications.md)
