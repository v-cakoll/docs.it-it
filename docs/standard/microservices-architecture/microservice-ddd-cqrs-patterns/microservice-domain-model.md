---
title: Progettazione di un modello di dominio microservizio
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettazione di un modello di dominio microservizio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a>Progettazione di un modello di dominio microservizio

*Definire un modello di dominio completo per ogni business microservizio o contesto limitato*

L'obiettivo consiste nel creare un modello di dominio coesiva singolo per ogni business microservizio o contesto limitato (BC). Tenere presente, tuttavia, che a BC o microservizio business può talvolta essere costituito da diversi servizi fisici che condividono un modello di dominio singolo. Il modello di dominio è necessario acquisire le regole, comportamento, il linguaggio di business e i vincoli del singolo contesto delimitata o microservizio business che rappresenta.

## <a name="the-domain-entity-pattern"></a>Il modello di entità di dominio

Le entità rappresentano gli oggetti di dominio e vengono definite principalmente da identità, la continuità e persistenza nel tempo e non solo per gli attributi che costituiscono le. Come viene visualizzato, Eric Evans "di un oggetto definito principalmente tramite l'identità viene chiamato un'entità." Le entità sono molto importanti per il modello di dominio, poiché sono la base per un modello. Pertanto, identificare e progettare con attenzione.

*Identità di un'entità può attraversare più microservizi o contesti limitato.*

La stessa identità (anche se non è la stessa entità) possono essere modellate in più contesti delimitata o microservizi. Tuttavia, non implica che la stessa entità, con gli stessi attributi e logica potrebbe essere implementate in più contesti delimitata. Al contrario, le entità in ogni contesto delimitata limitare i relativi attributi e i comportamenti di quelli richiesti nel dominio del contesto che delimitata.

Ad esempio, l'entità dell'acquirente potrebbe essere la maggior parte degli attributi di una persona che sono definiti nell'entità in microservizio il profilo o l'identità, tra cui l'identità utente. L'entità buyer nell'ordinamento microservizio potrebbe invece essere meno attributi, perché solo determinati dati buyer sono correlati al processo di ordine. Il contesto di ogni microservizio o delimitata contesto ha un impatto relativo modello di dominio.

*Entità di dominio deve implementare il comportamento oltre all'implementazione di attributi dei dati*

Un'entità di dominio in DDD deve implementare la logica di dominio o il comportamento correlati ai dati di entità (oggetto cui si accede in memoria). Come parte di una classe di entità order, ad esempio, è necessario disporre della logica di business e le operazioni implementate come metodi per attività quali l'aggiunta di un elemento di ordine, la convalida dei dati e calcolo del totale. I metodi dell'entità svolgere le regole dell'entità anziché le regole di livello dell'applicazione vengono suddivisi e invarianti.

Figura 9-8 è illustrata un'entità di dominio che implementa non solo gli attributi di dati ma le operazioni o i metodi con la logica di dominio correlate.

![](./media/image9.png)

**Figura 9-8**. Esempio di un'entità di dominio progettare l'implementazione dei dati e comportamento

Naturalmente, in alcuni casi è possibile disporre le entità che non implementano qualsiasi logica come parte della classe di entità. Questa situazione può verificarsi nelle entità figlio all'interno di un'aggregazione se l'entità figlio non dispone di una logica speciale perché la maggior parte della logica di è definito nella radice di aggregazione. Se si dispone di un microservizio complesso con molta logica implementata nelle classi del servizio anziché le entità di dominio, è possibile che rientrano nel modello di dominio anemic, illustrato nella sezione seguente.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Modello di dominio Rich rispetto al modello di dominio anemic

Nel suo post [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler descrive un modello di dominio anemic in questo modo:

Il sintomo di un modello di dominio Anemic base è inizialmente sembra reali. Sono presenti oggetti, molti denominato dopo i nomi nello spazio di dominio e questi oggetti sono connessi con le relazioni avanzate e la struttura con i modelli di dominio true. Catch viene fornito quando si osserva il comportamento e ci si accorge che è praticamente qualsiasi comportamento di tali oggetti, rendendoli leggermente più contenitori di getter e Setter.

Naturalmente, quando si utilizza un modello di dominio anemic, i modelli di dati verranno utilizzati da un set di oggetti servizio (denominata in genere il *livello business*) cui acquisire tutta la logica di business o di dominio. Il livello business si trova nella parte superiore del modello di dati e utilizza il modello di dati come dati.

Il modello di dominio anemic è una progettazione di stile procedurale. Oggetti entità anemic non sono oggetti reali perché dispongono di un comportamento (metodi). Contengono solo le proprietà di dati e non è pertanto progettazione orientata agli oggetti. Inserendo tutti i comportamenti out in oggetti del servizio (il livello business) essenzialmente finire con [assai complicato](https://en.wikipedia.org/wiki/Spaghetti_code) o [script transazione](https://martinfowler.com/eaaCatalog/transactionScript.html), e pertanto persi i vantaggi che un modello di dominio fornisce.

Indipendentemente dal fatto che, se lo microservizio o il contesto limitato è molto semplice (un servizio CRUD), il modello di dominio anemic sotto forma di oggetti entità con solo le proprietà di dati potrebbe essere sufficiente e che non sia opportuno implementare modelli DDD più complessi. In tal caso, sarà sufficiente un modello di persistenza, poiché è stato creato intenzionalmente un'entità solo i dati per scopi CRUD.

Che è il motivo per cui le architetture di microservizi sono ideali per un approccio architetturale più a seconda del contesto ogni delimitata. Ad esempio, in eShopOnContainers, l'ordinamento microservizio implementa modelli DDD, ma non microservizio il catalogo, che è un semplice servizio CRUD.

Alcune persone, si supponga che il modello di dominio anemic è un anti-pattern. Questo dipende si sta implementando. Se il microservizio si sta creando è semplice sufficientemente (ad esempio, un servizio CRUD), al modello di dominio anemic non è un anti-pattern. Tuttavia, se è necessario affrontare la complessità del dominio di un microservizio che dispone di molte delle regole di business in continua evoluzione, il modello di dominio anemic potrebbe essere un anti-pattern del microservizio o contesto limitato. In tal caso, impostandolo come potente modello con le entità che contengono dati e comportamento nonché implementare altri modelli DDD (valore oggetti aggregati, e così via) può presentare enormi vantaggi per il successo a lungo termine di questo tipo un microservizio.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **DevIQ. Entità di dominio**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)

-   **Martin Fowler. Il modello di dominio**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martin Fowler. Il modello di dominio Anemic**

    <https://martinfowler.com/bliki/AnemicDomainModel.HTML>

### <a name="the-value-object-pattern"></a>Il modello oggetto di valore

Come Eric Evans ha illustrato, "molti oggetti non hanno identità concettuale. Questi oggetti descrivono alcune caratteristiche di un elemento".

Un'entità richiede un'identità, ma sono presenti molti oggetti in un sistema che non, ad esempio il modello oggetto di valore. Un oggetto di valore è un oggetto con alcuna identità concettuale che descrive un aspetto di dominio. Si tratta di oggetti che si crea un'istanza per rappresentare gli elementi di progettazione che riguardano soltanto è temporaneamente. Si è interessati *cosa* , non sono *che* sono. Esempi includono numeri e stringhe, ma possono anche essere concetti di livello superiore quali gruppi di attributi.

Un elemento che è un'entità in un microservizio potrebbe non essere un'entità in un altro microservizio, poiché nel secondo caso, il contesto limitato potrebbe avere un significato diverso. Ad esempio, un indirizzo di un'applicazione di e-commerce potrebbe è un'identità, poiché potrebbe rappresentare solo un gruppo di attributi del profilo del cliente per una persona o della società. In questo caso, l'indirizzo deve essere classificato come un oggetto valore. Tuttavia, in un'applicazione per una società di energia elettrica utilità, l'indirizzo del cliente potrebbe essere importante per il dominio aziendale. Pertanto, l'indirizzo deve avere un'identità in modo il sistema di fatturazione può essere collegato direttamente all'indirizzo. In tal caso, un indirizzo deve essere classificato come un'entità di dominio.

Un utente con un nome e cognome in genere è un'entità perché una persona con un'identità, anche se il nome e cognome coincide con un altro set di valori, ad esempio se tali nomi fa riferimento anche a un utente diverso.

Gli oggetti di valore sono difficili da gestire nei database relazionali e ORM come Entity Framework, mentre nel documento orientata ai servizi sono più facili da implementare e utilizzare i database.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. Modello di oggetti valore**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Valore oggetto**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)

-   **Valore di oggetti in fase di sviluppo TDD**
    [*https://leanpub.com/tdd-ebook/read\#oggetti valore di auto leanpub*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans. Progettazione basati su dominio: Affrontare complessità il cuore del Software.** (Una cartella di lavoro e include una descrizione di oggetti valore) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>Il modello di aggregazione

Un modello di dominio contiene cluster delle entità di dati diversi e i processi che è possono controllare un'area significativa di funzionalità, ad esempio l'evasione dell'ordine o inventario. Un'unità DDD con granularità fine è l'aggregazione, che descrive un cluster o un gruppo di entità e i comportamenti che possono essere considerati come un'unità coesiva.

Si definisce in genere un'aggregazione in base alle transazioni di cui è necessario. Un esempio classico è un ordine contenente un elenco di elementi di ordine. Un elemento order in genere è un'entità. Ma sarà un'entità figlio all'interno dell'aggregazione ordine, che conterrà anche l'entità ordine come relativa entità principale, in genere chiamato una radice di aggregazione.

Identificazione di funzioni di aggregazione può essere difficile. Un'aggregazione è un gruppo di oggetti che devono essere coerenti tra loro, ma non è possibile solo selezionare un gruppo di oggetti e contrassegnarli come un'aggregazione. È necessario iniziare con il concetto di dominio e considerare le entità che vengono utilizzate nelle transazioni più comuni relativi a questo concetto. Le entità che devono essere coerenti sono cosa costituisce un'aggregazione. Considerare le operazioni di transazioni è probabilmente il modo migliore per identificare le aggregazioni.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>Il modello radice di aggregazione o entità radice

Un'aggregazione è composta da almeno un'entità: la radice di aggregazione, definito anche come entità principale o primario ientity. Inoltre, può avere più entità figlio e gli oggetti di valore, con tutte le entità e oggetti che interagiscono per implementare le transazioni e il comportamento richiesto.

Lo scopo di una radice di aggregazione è garantire la coerenza della funzione di aggregazione; deve essere il solo punto di ingresso per l'aggregazione tramite i metodi di aggiornamenti o le operazioni di classe root. È necessario apportare modifiche alle entità all'interno dell'aggregazione solo tramite la radice di aggregazione. Si tratta di sorveglianza la coerenza dell'aggregazione, tenendo in considerazione tutte le invarianti e regole di uniformità che potrebbe essere necessario rispettare nell'aggregazione. Se si modifica un oggetto di entità o un valore figlio in modo indipendente, la radice di aggregazione non è possibile verificare che la funzione di aggregazione sia in uno stato valido. Sarebbe ad esempio una tabella con un segmento separato. Mantenere la coerenza è lo scopo principale della radice dell'aggregazione.

Nella figura 9-9, è possibile visualizzare le aggregazioni di esempio come acquirente aggregazione, che contiene una singola entità (la radice di aggregazione acquirente). L'aggregazione di ordine contiene più entità e un oggetto valore.

![](./media/image10.png)

**Figura 9-9**. Esempio di funzioni di aggregazione con più o singole entità

Si noti che l'aggregazione dell'acquirente potrebbe avere entità figlio aggiuntivi, a seconda del dominio, come avviene per l'ordinamento microservizio nell'applicazione di riferimento eShopOnContainers. Figura 9-9 è illustrato solo un caso in cui l'acquirente ha una singola entità, ad esempio di un'aggregazione che contiene una radice di aggregazione.

Per mantenere la separazione di aggregazioni e mantenere i limiti ben definiti tra di essi, è buona norma in un modello di dominio DDD a impedire l'esplorazione diretta tra funzioni di aggregazione e solo con il campo di chiave esterna (FK), come implementato nel [ Ordinamento di modello di dominio microservizio](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers. L'entità Order ha solo un campo di chiave esterna per l'acquirente, ma non una proprietà di navigazione principale di Entity Framework, come illustrato nel codice seguente:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

Identificazione e l'utilizzo di funzioni di aggregazione richiede esperienza e ricerca. Per ulteriori informazioni, vedere l'elenco di risorse aggiuntive seguenti.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Vaughn Vernon. Progettazione di aggregazione efficace - parte i: modellazione di una singola funzione di aggregazione**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_approfondimento\_ Funzioni di aggregazione\_parte\_pdf 1.*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon. Progettazione aggregazione efficace - parte II: Apportato aggregazioni collaborano**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*

-   **Vaughn Vernon. Progettazione aggregazione efficace - parte III: Ottenere informazioni dettagliate tramite individuazione**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*

-   **Sergey Grybniak. Modelli di progettazione tattico DDD**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Richardson. Sviluppo di Microservizi transazionale utilizzando funzioni di aggregazione**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ. Il modello di aggregazione**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)


>[!div class="step-by-step"]
[Precedente] (ddd-oriented-microservice.md) [Avanti] (net-core-microservizio-dominio-model.md)
