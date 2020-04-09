---
title: Progettazione di un microservizio orientato a DDD
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Progettazione del microservizio degli ordini orientato a DDD e dei relativi livelli dell'applicazione.
ms.date: 10/08/2018
ms.openlocfilehash: 583e103c8bd9d828731a658ea2fd2aa0758e7a12
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988739"
---
# <a name="design-a-ddd-oriented-microservice"></a>Progettare un microservizio orientato a DDD

La progettazione orientata al dominio (DDD) sostiene la modellazione basata sulla realtà di business in quanto rilevante per i casi d'uso. Nel contesto della compilazione delle applicazioni, DDD considera i problemi come domini. Vengono descritte singole aree di problemi, ad esempio i contesti delimitati (ogni contesto delimitato è correlato a un microservizio) e viene evidenziato un linguaggio comune che consente di comunicare su questi problemi. Vengono indicati inoltre numerosi schemi e concetti tecnici, ad esempio le entità di dominio con modelli avanzati (nessun [modello indipendente dal dominio](https://martinfowler.com/bliki/AnemicDomainModel.html)), oggetti valore, aggregazioni e regole di radici di aggregazione (o entità radice) per supportare l'implementazione interna. Questa sezione illustra la progettazione e l'implementazione di tali schemi interni.

Questi schemi e regole tecniche DDD talvolta vengono percepite come ostacoli per l'implementazione di approcci DDD a causa della curva di apprendimento profonda. L'aspetto più importante, in realtà, non riguarda gli schemi in sé, ma l'organizzazione del codice, che deve essere allineato ai problemi aziendali, e l'uso di termini di business comuni, ovvero di un linguaggio comune. Gli approcci DDD, inoltre, devono essere applicati solo se si implementano microservizi complessi con regole di business significative. Responsabilità più semplici, come un servizio CRUD, possono essere gestite con approcci più semplici.

L'attività chiave della progettazione e definizione di un microservizio è la determinazione dei limiti. Gli schemi DDD consentono di comprendere la complessità del dominio. Per il modello di dominio per ogni contesto delimitato occorre identificare e definire entità, oggetti valore e aggregazioni che modellano il dominio. Creare e perfezionare un modello di dominio all'interno di limiti che definiscono il contesto. Questo obiettivo si realizza esplicitamente sotto forma di microservizio. I componenti all'interno dei limiti definiti saranno i microservizi, anche se in alcuni casi un BC o microservizio di business può essere costituito da diversi servizi fisici. La progettazione DDD riguarda i limiti, come i microservizi.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>I limiti del contesto di un microservizio devono essere relativamente piccoli

La determinazione della posizione dei limiti tra contesti delimitati bilancia due obiettivi opposti. In primo luogo, si creano i microservizi più piccoli possibile, ma la dimensione non deve essere la motivazione principale: è necessario creare un limite attorno a elementi che richiedono coesione. In secondo luogo, occorre evitare le comunicazioni frammentate tra microservizi. Questi obiettivi possono essere in contraddizione. È consigliabile bilanciarli scomponendo il sistema in quanti più piccoli microservizi è possibile finché i limiti della comunicazione non crescono rapidamente con ogni tentativo aggiuntivo di separare un nuovo contesto delimitato. La coesione è la chiave di un singolo contesto delimitato.

È simile al [code smell Inappropriate Intimacy](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) per l'implementazione delle classi. Se due microservizi devono collaborare molto tra loro, è probabile che sia più opportuno riunirli in un solo microservizio.

Un altro modo in cui analizzare il problema è valutare l'autonomia. Se un microservizio deve basarsi su un altro servizio per soddisfare direttamente una richiesta, non è realmente autonomo.

## <a name="layers-in-ddd-microservices"></a>Livelli nei microservizi DDD

Generalmente le applicazioni aziendali con complessità tecniche e aziendali notevoli sono definite da più livelli. I livelli sono elementi logici e non sono correlati alla distribuzione del servizio. Consentono agli sviluppatori di gestire la complessità del codice. Livelli diversi (ad esempio il livello del modello di dominio, il livello di presentazione e così via) potrebbero avere tipi diversi, imponendo l'utilizzo di conversioni tra questi tipi.

Ad esempio, è stato possibile caricare un'entità dal database. Parte delle informazioni, o un'aggregazione di informazioni che comprende dati aggiuntivi di altre entità, può quindi essere inviata all'interfaccia utente del client tramite un'API Web REST. L'entità di dominio è tuttavia contenuta nel livello del modello di dominio e non deve essere propagata ad altre aree a cui non appartiene, ad esempio al livello di presentazione.

È necessario, inoltre, disporre di entità sempre valide (vedere la sezione [Progettazione di convalide nel livello del modello di dominio](domain-model-layer-validations.md)) controllate da radici di aggregazione (entità radice). Di conseguenza, le entità non devono essere associate a viste del client, perché a livello di interfaccia utente alcuni dati potrebbero non essere ancora convalidati. È qui che entra in gioco l'elemento ViewModel. ViewModel è un modello di dati destinato esclusivamente al livello di presentazione. Le entità di dominio non appartengono direttamente all'elemento ViewModel. È necessario invece effettuare la conversione tra elementi ViewModel ed entità di dominio e viceversa.

Per gestire la complessità, è importante disporre di un modello di dominio controllato da radici di aggregazione che assicurano che tutte le invarianti e le regole relative al gruppo di entità (aggregazione) vengano eseguite tramite un singolo punto di ingresso o controllo, la radice di aggregazione.

La figura 7-5 illustra una progettazione a più livelli implementata nell'applicazione eShopOnContainers.

![Diagramma che mostra i livelli in un microservizio di progettazione basato su dominio.](./media/ddd-oriented-microservice/domain-driven-design-microservice.png)

**Figura 7-5.** Livelli DDD nel microservizio degli ordini in eShopOnContainers

I tre livelli in un microservizio DDD, ad esempio per gli ordini. Ogni livello è un progetto di Visual Studio: il livello dell'applicazione è Ordering.API, il livello del dominio è Ordering.Domain e il livello dell'infrastruttura è Ordering.Infrastructure. Si vuole progettare il sistema in modo che ogni livello comunichi solo con determinati altri livelli. Questo obiettivo può risultare più semplice se i livelli vengono implementati come librerie di classi diverse, in quanto è possibile identificare chiaramente quali dipendenze siano impostate tra le librerie. Ad esempio, il livello del modello di dominio non deve accettare una dipendenza da qualsiasi altro livello (le classi di modello di dominio devono essere oggetti Plain Old CLR Object, o[POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)). Come illustrato nella figura 7-6, la libreria del livello **Ordering.Domain** presenta dipendenze solo dalle librerie .NET Core o dai pacchetti NuGet, ma da nessun'altra libreria personalizzata, ad esempio una libreria di dati o di persistenza.

![Screenshot di Ordering.Domain dependencies.](./media/ddd-oriented-microservice/ordering-domain-dependencies.png)

**Figura 7-6**. I livelli implementati come librerie consentono un migliore controllo delle dipendenze tra i livelli

### <a name="the-domain-model-layer"></a>Livello del modello di dominio

L'eccellente libro di Eric Evans sulla [progettazione basata sui domini](https://domainlanguage.com/ddd/) descrive nel modo seguente il livello del modello di dominio e il livello dell'applicazione.

**Livello del modello di dominio**: responsabile della rappresentazione di concetti di business, informazioni sulla situazione aziendale e regole di business. A questo livello viene controllato e usato lo stato che riflette la situazione di business, anche se i dettagli tecnici dell'archiviazione vengono delegati all'infrastruttura. Questo livello è il cuore del software di business,

il livello in cui viene espresso il business. Quando si implementa un livello del modello di dominio del microservizio in .NET, tale livello viene codificato come libreria di classi con entità di dominio che consentono di acquisire i dati più il comportamento (metodi con logica).

Secondo i principi di [Persistence Ignorance](https://deviq.com/persistence-ignorance/) e [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance), questo livello deve ignorare completamente i dettagli della persistenza dei dati. Le attività relative alla persistenza devono essere eseguite dal livello infrastruttura. Di conseguenza, questo livello non deve accettare dipendenze dirette dall'infrastruttura. In altre parole, una regola importante impone che le classi di entità del modello di dominio siano oggetti [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object).

Le entità di dominio non devono presentare alcuna dipendenza diretta (ad esempio non devono derivare da una classe di base) da qualsiasi framework di infrastruttura di accesso dati come Entity Framework o NHibernate. In teoria, le entità di dominio non devono derivare da alcun tipo definito in un framework di infrastruttura né implementarlo.

Framework ORM più recenti come Entity Framework Core consentono questo approccio, in modo che le classi di modello di dominio non siano collegate all'infrastruttura. Tuttavia, non sempre è possibile usare entità POCO con determinati framework e database NoSQL, ad esempio Actors e Reliable Collections in Azure Service Fabric.

Anche quando è importante seguire il principio di mancato riconoscimento della persistenza per il proprio modello di dominio, non si devono ignorare i problemi di persistenza. È comunque molto importante comprendere il modello di dati fisici e il relativo mapping al proprio modello di oggetti entità. In caso contrario si potrebbero creare progetti impossibili.

Ciò non significa che sia possibile spostare un modello progettato per un database relazionale direttamente in un database orientato ai documenti o NoSQL. In alcuni modelli di entità il modello potrebbe essere adatto, ma in genere non lo è. Esistono ancora vincoli che il modello di entità deve rispettare, a seconda della tecnologia di archiviazione e della tecnologia ORM.

### <a name="the-application-layer"></a>Livello dell'applicazione

Passando al livello dell'applicazione, è possibile citare nuovamente il libro di Eric Evans sulla [progettazione basata su domini](https://domainlanguage.com/ddd/):

**Livello dell'applicazione:** definisce i processi che il software dovrà eseguire e indica agli oggetti di dominio espressivi per risolvere i problemi. Le attività di cui è responsabile questo livello sono significative per il business o necessarie per l'interazione con i livelli dell'applicazione di altri sistemi. Questo livello deve essere di ampiezza limitata. Non contiene regole business o informazioni, ma si limita a coordinare le attività e a delegare il lavoro a collaborazioni di oggetti di dominio nel livello immediatamente successivo. Non presenta uno stato che riflette la situazione di business, ma può avere uno stato che riflette l'avanzamento di un'attività per l'utente o il programma.

Il livello dell'applicazione di un microservizio in .NET è comunemente codificato come progetto API Web di ASP.NET Core. Il progetto implementa l'interazione del microservizio, l'accesso remoto alla rete e le API Web esterne usate dall'interfaccia utente o dalle app client. Include le query se si usa un approccio CQRS, i comandi accettati dal microservizio e la comunicazione basata su eventi tra microservizi (eventi di integrazione). L'API Web di ASP.NET Core che rappresenta il livello dell'applicazione non può contenere regole business o informazioni di dominio (in particolare regole di dominio per le transazioni o gli aggiornamenti); tali elementi devono appartenere alla libreria di classi del modello di dominio. Il livello dell'applicazione deve solo coordinare le attività e non deve contenere o definire uno stato di dominio (modello di dominio). Delega l'esecuzione delle regole di business alle classi di modello di dominio stesse (radici di aggregazione ed entità di dominio), che infine aggiorneranno i dati all'interno di tali entità di dominio.

In pratica, la logica dell'applicazione è il punto in cui si implementano tutti i casi d'uso che dipendono da un front-end specificato. Ad esempio, l'implementazione relativa a un servizio Web API.

Lo scopo è far sì che la logica di dominio nel livello del modello di dominio, le relative invarianti, il modello di dati e le regole business correlate siano completamente indipendenti dai livelli di presentazione e dell'applicazione. Il livello del modello di dominio, soprattutto, non deve dipendere direttamente da alcun framework di infrastruttura.

### <a name="the-infrastructure-layer"></a>Livello infrastruttura

Il livello infrastruttura è responsabile della persistenza dei dati inizialmente contenuti nelle entità di dominio (in memoria) nei database o altri archivi persistenti. Un esempio è costituito dall'uso del codice di Entity Framework Core per implementare le classi di schemi Repository che usano un elemento DBContext per rendere persistenti i dati in un database relazionale.

In conformità con i principi di [Persistence Ignorance](https://deviq.com/persistence-ignorance/) e [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) menzionati in precedenza, il livello dell'infrastruttura non deve "contaminare" il livello del modello di dominio. È necessario mantenere le classi di entità di modello indipendenti dall'infrastruttura usata per rendere persistenti i dati (Entity Framework o qualsiasi altro framework) non accettando dipendenze rigide dai framework. La libreria di classi del livello del modello di dominio deve contenere solo il codice di dominio, semplicemente classi di entità [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) che implementano il cuore del software e completamente scollegate delle tecnologie di infrastruttura.

I livelli o le librerie di classi e i progetti dipenderanno quindi dal livello del modello di dominio (libreria), non viceversa, come illustrato nella figura 7-7.

![Diagramma che mostra le dipendenze esistenti tra i livelli di servizio DDD.](./media/ddd-oriented-microservice/ddd-service-layer-dependencies.png)

**Figura 7-7**. Dipendenze tra livelli in DDD

Dipendenze in un servizio DDD, il livello dell'applicazione dipende da dominio e infrastruttura e l'infrastruttura dipende dal dominio, ma il dominio non dipende da alcun livello. Questa struttura di livello deve essere indipendente per ogni microservizio. Come notato in precedenza, è possibile implementare i microservizi più complessi seguendo gli schemi DDD e implementare microservizi più semplici basati sui dati (CRUD semplice in un unico livello) in modo più facile.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **DevIQ. Principio di persistenza dell'ignoranza** \
  <https://deviq.com/persistence-ignorance/>

- **Oren Eini. Ignoranza delle infrastrutture** \
  <https://ayende.com/blog/3137/infrastructure-ignorance>

- **Angel Lopez. Architettura basata su più livelli nella progettazione basata su dominio** \
  <https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/>

>[!div class="step-by-step"]
>[Successivo](cqrs-microservice-reads.md)
>[precedente](microservice-domain-model.md)
