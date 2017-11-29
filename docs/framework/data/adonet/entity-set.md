---
title: "set di entità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6b28be2b3bdddd9457874881e930ea978ef5c2b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="entity-set"></a><span data-ttu-id="62995-102">set di entità</span><span class="sxs-lookup"><span data-stu-id="62995-102">entity set</span></span>
<span data-ttu-id="62995-103">Un *set di entità* è un contenitore logico per istanze di un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e le istanze di qualsiasi tipo derivato da tale tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-103">An *entity set* is a logical container for instances of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="62995-104">(Per informazioni sui tipi derivati, vedere [Entity Data Model: ereditarietà](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) La relazione tra un tipo di entità e un set di entità è analoga alla relazione tra una riga e una tabella in un database relazionale: come una riga, un tipo di entità descrive la struttura di dati e, come una tabella, un set di entità contiene le istanze di una determinata struttura.</span><span class="sxs-lookup"><span data-stu-id="62995-104">(For information about derived types, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="62995-105">Un set di entità non è un costrutto di modellazione dati e non descrive la struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="62995-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="62995-106">Un set di entità, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze del tipo di entità in modo che se ne possa eseguire il mapping a un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="62995-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="62995-107">Un set di entità è definito all'interno di un [contenitore di entità](../../../../docs/framework/data/adonet/entity-container.md), ovvero un raggruppamento logico di set di entità e [set di associazioni](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="62995-107">An entity set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of entity sets and [association sets](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="62995-108">Perché un'istanza di un tipo di entità esista in un set di entità, devono essere osservate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="62995-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
-   <span data-ttu-id="62995-109">Il tipo dell'istanza è lo stesso del tipo di entità su cui si basa il set di entità oppure il tipo dell'istanza è un sottotipo del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
-   <span data-ttu-id="62995-110">Il [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) per l'istanza è univoco all'interno del set di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-110">The [entity key](../../../../docs/framework/data/adonet/entity-key.md) for the instance is unique within the entity set.</span></span>  
  
-   <span data-ttu-id="62995-111">L'istanza non esiste in nessun altro set di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62995-112">È possibile definire più set di entità tramite lo stesso tipo di entità, ma un'istanza di un determinato tipo di entità può esistere in un solo set di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="62995-113">Non è necessario definire un set di entità per ogni tipo di entità in un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="62995-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62995-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="62995-114">Example</span></span>  
 <span data-ttu-id="62995-115">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="62995-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="62995-116">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="62995-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="62995-117">Nel diagramma seguente vengono illustrati due set di entità (`Books` e `Publishers`) e un set di associazioni (`PublishedBy`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="62995-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="62995-118">Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` il tipo di entità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62995-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="62995-119">Analogamente, Pj rappresentano un `Publisher` dell'istanza nel `Publishers` set di entità.</span><span class="sxs-lookup"><span data-stu-id="62995-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="62995-120">BiPj rappresenta un'istanza di `PublishedBy` associazione nel `PublishedBy` set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="62995-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="62995-121">![Esempio](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="62995-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="62995-122">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="62995-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="62995-123">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di entità per ogni tipo di entità nel modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="62995-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="62995-124">Si noti che il nome e il tipo di entità per ogni set di entità sono definiti tramite attributi XML.</span><span class="sxs-lookup"><span data-stu-id="62995-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="62995-125">È possibile definire più set di entità per tipo (MEST).</span><span class="sxs-lookup"><span data-stu-id="62995-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="62995-126">Il linguaggio CSDL seguente definisce un contenitore di entità con due set di entità per il tipo di entità `Book`:</span><span class="sxs-lookup"><span data-stu-id="62995-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="62995-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62995-127">See Also</span></span>  
 [<span data-ttu-id="62995-128">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="62995-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="62995-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="62995-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
