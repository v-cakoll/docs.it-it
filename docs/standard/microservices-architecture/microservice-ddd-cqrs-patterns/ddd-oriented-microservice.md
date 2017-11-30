---
title: Progettazione di un microservizio orientata ai servizi DDD
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettazione di un microservizio orientata ai servizi DDD
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df45441089fd59d5e0e52b4bcec409adcc11fb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-ddd-oriented-microservice"></a>Progettazione di un microservizio orientata ai servizi DDD

Progettazione basati su dominio (DDD) sostiene modellazione dipende in realtà di business come rilevanti per i casi di utilizzo. Nel contesto di compilazione di applicazioni, DDD parla problemi come domini. Vengono descritti problemi indipendente come delimitata contesti (ogni contesto delimitata è correlata a un microservizio), evidenziare un linguaggio comune per comunicare su questi problemi. Si consiglia inoltre di numerosi concetti tecnici e i modelli, analogamente alle entità di dominio con i modelli avanzati (nessun [anemic dominio modello](https://martinfowler.com/bliki/AnemicDomainModel.html)), valore oggetti, le aggregazioni e radice di aggregazione (o entità radice), le regole per supportare l'implementazione interna. Questa sezione presenta la progettazione e implementazione di tali modelli interni.

A volte queste regole tecniche DDD e modelli vengono considerati ostacoli che una curva di apprendimento profonda per l'implementazione DDD approcci. Ma la parte importante è non di modelli, ma organizzazione del codice in modo che sia allineato ai problemi aziendali e utilizzando gli stessi termini di business (linguaggio universale). Inoltre, gli approcci DDD devono essere applicati solo se si siano implementando microservizi complesso con regole di business significativo. Responsabilità più semplice, come un servizio CRUD, possono essere gestite con gli approcci più semplici.

Punto in cui disegnare i limiti è l'attività chiave durante la progettazione e la definizione di un microservizio. DDD criteri consentono di comprendere la complessità del dominio. Per il modello di dominio per ogni contesto delimitata identificare e definire aggregazioni che il dominio del modello, entità e oggetti. Compilare e modificare un modello di dominio all'interno di un limite che definisce il contesto. E che è molto esplicite sotto forma di un microservizio. I componenti all'interno di tali limiti finire dal microservizi, anche se in alcuni casi un BC o microservizi business possono essere costituito da diversi servizi fisici. DDD è sui limiti e quindi microservizi.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>Mantenere relativamente piccolo i limiti del contesto di microservizio

Determinare dove posizionare i confini tra contesti delimitata saldi due obiettivi principali concorrenti. In primo luogo, si desidera creare inizialmente il più piccolo possibile microservizi, sebbene che non deve essere il driver principale; è necessario creare un limite attorno necessario coesione aspetti. In secondo luogo, si desidera evitare le comunicazioni "frammentate" tra microservizi. Questi obiettivi possano che siano in contraddizione tra loro. È consigliabile valutare tali scomponendo il sistema in tanti microservizi piccoli possibile finché non vengono visualizzati i limiti di comunicazione in rapida crescita con ogni tentativo aggiuntiva per separare un nuovo contesto limitato. Coesione è chiave all'interno di un solo contesto associato.

È simile al [odore codice riservatezza inappropriato](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) nell'implementazione delle classi. Se due microservizi necessario molto collaborano tra loro, dovrebbero essere probabilmente la stessa microservizio.

A questo aspetto è autonomia. Se un microservizio deve basarsi su un altro servizio per una richiesta di servizio direttamente, non è realmente autonomo.

## <a name="layers-in-ddd-microservices"></a>Livelli DDD microservizi

La maggior parte delle applicazioni aziendali con business significativi e complessità tecnica sono definite da più livelli. I livelli sono un elemento logico e non sono correlati alla distribuzione del servizio. Essi consentono agli sviluppatori di gestire la complessità del codice. Livelli diversi (ad esempio, il livello del modello di dominio e il livello di presentazione e così via) potrebbero essere tipi diversi, che impone l'utilizzo di conversioni tra questi tipi.

Ad esempio, è stato possibile caricare un'entità dal database. Parte di tali informazioni o di un'aggregazione di informazioni tra i dati aggiuntivi da altre entità, possa quindi essere inviato al client dell'interfaccia utente mediante un'API Web REST. Il punto è che l'entità di dominio è contenuto all'interno del livello di modello di dominio e non deve essere propagata ad altre aree che non appartiene a, ad esempio al livello di presentazione.

Inoltre, è necessario disporre sempre valido entità (vedere il [progettazione convalide nel livello del modello di dominio](#designing-validations-in-the-domain-model-layer) sezione) controllata da radici di aggregazione (entità radice). Pertanto, le entità non devono essere associate a viste di client, perché a livello di interfaccia utente alcuni dati potrebbero comunque non è possibile convalidare. Questo è ciò che è il ViewModel per. L'elemento ViewModel è un modello di dati esclusivamente per i requisiti di livello presentazione. Le entità di dominio non appartengono direttamente per l'elemento ViewModel. In alternativa, è necessario convertire tra entità ViewModel e il dominio e viceversa.

Quando la complessità di gestione, è importante disporre di un modello di dominio controllato dall'aggregazione radici (si entra in questo in modo più dettagliato più avanti) che assicurarsi che tutte le invarianti e le regole relative al gruppo di entità (aggregazione) vengono eseguite tramite una singola voce il punto o controllo, la radice di aggregazione.

Nella figura 9-5 di seguito viene illustrata una progettazione a più livelli dell'applicazione eShopOnContainers.

![](./media/image6.png)

**Nella figura 9-5**. Livelli DDD l'ordinamento microservizio in eShopOnContainers

Si desidera progettare il sistema in modo che ogni livello comunica solo con alcuni altri livelli. Che può risultare più semplice applicare in caso di livelli vengono implementati come librerie di classi diverse, in quanto è possibile identificare chiaramente quali le dipendenze siano impostate tra le librerie. Ad esempio, il livello del modello di dominio non deve accettare una dipendenza su qualsiasi altro livello (le classi di modello di dominio devono essere Plain Old CLR Object, o [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object), classi). Come illustrato nella figura 9-6, il **Ordering.Domain** libreria layer dipendenze solo nelle librerie di .NET Core, ma non su qualsiasi altra libreria personalizzata (raccolta di dati, libreria di persistenza e così via).

![](./media/image7.PNG)

**Figura 9-6**. Implementato come librerie consentono un migliore controllo delle dipendenze tra i livelli di livelli

### <a name="the-domain-model-layer"></a>Il livello del modello di dominio

Libro eccellente di Eric Evans [progettazione basata su domini](http://domainlanguage.com/ddd/) il messaggio seguente sul livello del modello di dominio e il livello di applicazione.

**Livello del modello di dominio**: responsabile per la rappresentazione di concetti di business, le informazioni sulla situazione aziendale e le regole di business. Stato che riflette la situazione di business è controllato e usato in questo caso, anche se i dettagli tecnici di archiviare i dati vengono delegati all'infrastruttura. Questo livello è il cuore del software di business.

Il livello del modello di dominio è in cui viene espresso il business. Quando si implementa un livello del modello di dominio microservizio in .NET, tale livello viene codificato come una libreria di classi con le entità di dominio che consentono di acquisire i dati più comportamento (metodi con logica).

Dopo il [mancato riconoscimento della persistenza](http://deviq.com/persistence-ignorance/) e [mancato riconoscimento di infrastruttura](https://ayende.com/blog/3137/infrastructure-ignorance) principi, questo livello completamente devono ignorare i dettagli di persistenza di dati. Queste operazioni di persistenza devono essere eseguite dal livello di infrastruttura. Pertanto, questo livello non deve richiedere dipendenze dirette sull'infrastruttura, che significa che una regola importante è che le classi di entità del modello di dominio devono essere [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s.

Entità di dominio non deve essere qualsiasi dipendenza diretta (ad esempio, la derivazione da una classe di base) in qualsiasi framework di infrastruttura di accesso dati Entity Framework o NHibernate. In teoria, le entità di dominio non devono derivare da o implementare qualsiasi tipo definito in qualsiasi framework di infrastruttura.

Framework più recenti di ORM come Entity Framework Core consente questo approccio, in modo che le classi di modello di dominio non sono collegate all'infrastruttura. Tuttavia, con le entità POCO non è sempre possibile quando si utilizzano determinati database NoSQL e Framework, come gli attori e le raccolte affidabile in Azure Service Fabric.

Anche quando è importante seguire il principio di mancato riconoscimento della persistenza è modello di dominio, non è consigliabile ignorare i problemi di persistenza. È comunque importante comprendere il modello di dati fisici e come viene eseguito il mapping del modello a oggetti entità. In caso contrario è possibile creare progettazioni Impossibile.

Inoltre, questo non significa è possibile richiedere un modello progettato per un database relazionale e spostarlo direttamente al database orientato ai documenti o NoSQL. In alcuni modelli di entità, potrebbe essere adatta il modello, ma in genere non è presente. I vincoli che il modello di entità deve essere conformi alle, basata sulla tecnologia di archiviazione e la tecnologia ORM sono ancora presenti.

### <a name="the-application-layer"></a>Il livello di applicazione

Passare al livello dell'applicazione, è possibile riportare nuovamente Rubrica di Eric Evans [progettazione basata su domini](http://domainlanguage.com/ddd/):

**Livello di applicazione:** definisce i processi, il software dovrà per eseguire e ti indica gli oggetti dominio espressivo tenta di risolvere i problemi. Le attività che è responsabile per questo livello sono significative all'azienda o necessarie per l'interazione con i livelli di applicazione di altri sistemi. Questo livello viene mantenuto thin. Non contiene regole business o Knowledge Base, ma solo i delegati e le coordinate attività lavoro collaborazioni di oggetti dominio nel livello successivo verso il basso. Non è stato che riflettono la situazione di business, ma può avere lo stato che riflette lo stato di avanzamento di un'attività per l'utente o il programma.

Livello di applicazione di un microservizio in .NET in genere viene codificato come un progetto di API Web di ASP.NET Core. Il progetto implementa l'interazione del microservizio, accesso remoto alla rete e le API Web esterni utilizzati dalle App client o dell'interfaccia utente. Include le query se utilizzando un CQRS approccio comandi accettati, in quanto il microservizio anche la comunicazione tra microservizi (eventi di integrazione) basato su eventi. L'API Web di ASP.NET Core che rappresenta il livello di applicazione non può contenere regole business o le informazioni di dominio (in particolare regole di dominio per le transazioni o aggiornamenti); questi devono essere di proprietà dalla libreria di classi di modello di dominio. La coordinata di applicazione livello deve solo attività e non deve contenere o definire uno stato di dominio (modello di dominio). Delega l'esecuzione delle regole di business per le classi di modello dominio stessi (radici di aggregazione e le entità di dominio), che in ultima analisi per aggiornare i dati all'interno di tali entità di dominio.

In pratica, la logica dell'applicazione è in cui si implementano tutti i casi di utilizzo che dipendono da un front-end specificato. Ad esempio, l'implementazione relative a un servizio Web API.

L'obiettivo consiste nel fatto che la logica di dominio nel livello del modello di dominio, relativo invarianti, il modello di dati e regole business correlati deve essere completamente indipendente dai livelli presentazione e l'applicazione. Per lo più, il livello del modello di dominio non direttamente dipendano qualsiasi framework di infrastruttura.

### <a name="the-infrastructure-layer"></a>Il livello infrastruttura

Il livello di infrastruttura è la modalità con cui i dati inizialmente contenuta in entità di dominio (in memoria) sono persistenti nel database o un altro archivio persistente. Un esempio Usa codice di Entity Framework Core per implementare le classi di modello di Repository che usano un elemento DBContext per mantenere i dati in un database relazionale.

In base alle indicati in precedenza [mancato riconoscimento della persistenza](http://deviq.com/persistence-ignorance/) e [mancato riconoscimento di infrastruttura](https://ayende.com/blog/3137/infrastructure-ignorance) principi, il livello di infrastruttura necessario non "danneggiare" livello del modello di dominio. È necessario mantenere indipendente dal classi entità di modello di dominio dall'infrastruttura che consente di rendere persistenti i dati (Entity Framework o qualsiasi altro framework) effettuando non dipendenze rigide su Framework. La libreria di classi livello di modello di dominio deve avere solo il codice di dominio appena [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) entità le classi che implementano il cuore del software e completamente separata delle tecnologie di infrastruttura.

Di conseguenza, i livelli o le librerie di classi e i progetti devono dipenderà dal livello del modello di dominio (libreria), non viceversa, come illustrato nella figura 9-7.

![](./media/image8.png)

**Figura 9-7**. Dipendenze tra i livelli DDD

Questa struttura di livello deve essere indipendente per ogni microservizio. Come notato in precedenza, è possibile implementare il microservizi più complesso seguente modelli DDD, durante l'implementazione più semplice basato sui dati microservizi (CRUD semplice in un unico livello) in modo più semplice.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **DevIQ. Il principio di mancato riconoscimento della persistenza**
    [*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)

-   **Dichiarato Oren Eini. Possibilità di infrastruttura**
    [*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)

-   **Angelo Lopez. A più livelli di architettura basati su dominio progettazione**
    [*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)


>[!div class="step-by-step"]
[Precedente] (cqrs-microservizio-reads.md) [Avanti] (microservizio-dominio-model.md)
