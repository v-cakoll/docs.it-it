---
title: set di entità
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 5a2465801c270813dd7bca2144d05fa202571153
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738426"
---
# <a name="entity-set"></a><span data-ttu-id="cb933-102">set di entità</span><span class="sxs-lookup"><span data-stu-id="cb933-102">entity set</span></span>
<span data-ttu-id="cb933-103">Un *set di entità* è un contenitore logico per istanze di un [tipo di entità](entity-type.md) e istanze di qualsiasi tipo derivato da tale tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="cb933-103">An *entity set* is a logical container for instances of an [entity type](entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="cb933-104">Per informazioni sui tipi derivati, vedere [Entity Data Model: ereditarietà](entity-data-model-inheritance.md). La relazione tra un tipo di entità e un set di entità è analoga alla relazione tra una riga e una tabella in un database relazionale: come una riga, un tipo di entità descrive la struttura dei dati e, come una tabella, un set di entità contiene le istanze di una determinata struttura.</span><span class="sxs-lookup"><span data-stu-id="cb933-104">(For information about derived types, see [Entity Data Model: Inheritance](entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="cb933-105">Un set di entità non è un costrutto di modellazione dati e non descrive la struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="cb933-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="cb933-106">Un set di entità, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze del tipo di entità in modo che se ne possa eseguire il mapping a un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="cb933-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="cb933-107">Un set di entità viene definito all'interno di un [contenitore di entità](entity-container.md), ovvero un raggruppamento logico di set di entità e [set di associazioni](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="cb933-107">An entity set is defined within an [entity container](entity-container.md), which is a logical grouping of entity sets and [association sets](association-set.md).</span></span>  
  
 <span data-ttu-id="cb933-108">Perché un'istanza di un tipo di entità esista in un set di entità, devono essere osservate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="cb933-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
- <span data-ttu-id="cb933-109">Il tipo dell'istanza è lo stesso del tipo di entità su cui si basa il set di entità oppure il tipo dell'istanza è un sottotipo del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="cb933-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
- <span data-ttu-id="cb933-110">La [chiave di entità](entity-key.md) per l'istanza è univoca all'interno del set di entità.</span><span class="sxs-lookup"><span data-stu-id="cb933-110">The [entity key](entity-key.md) for the instance is unique within the entity set.</span></span>  
  
- <span data-ttu-id="cb933-111">L'istanza non esiste in nessun altro set di entità.</span><span class="sxs-lookup"><span data-stu-id="cb933-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cb933-112">È possibile definire più set di entità tramite lo stesso tipo di entità, ma un'istanza di un determinato tipo di entità può esistere in un solo set di entità.</span><span class="sxs-lookup"><span data-stu-id="cb933-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="cb933-113">Non è necessario definire un set di entità per ogni tipo di entità in un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="cb933-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb933-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb933-114">Example</span></span>  
 <span data-ttu-id="cb933-115">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="cb933-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="cb933-117">Nel diagramma seguente vengono illustrati due set di entità (`Books` e `Publishers`) e un set di associazioni (`PublishedBy`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cb933-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="cb933-118">Bi nel set di entità `Books` rappresenta un'istanza del tipo di entità `Book` in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb933-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="cb933-119">Analogamente, PJ rappresenta un'istanza di `Publisher` nel set di entità `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="cb933-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="cb933-120">BiPj rappresenta un'istanza dell'associazione `PublishedBy` nel set di associazioni `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="cb933-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot che mostra un esempio di set.](./media/entity-set/sets-example-association.gif)  
  
 <span data-ttu-id="cb933-122">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="cb933-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="cb933-123">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di entità per ogni tipo di entità nel modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cb933-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="cb933-124">Si noti che il nome e il tipo di entità per ogni set di entità sono definiti tramite attributi XML.</span><span class="sxs-lookup"><span data-stu-id="cb933-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="cb933-125">È possibile definire più set di entità per tipo (MEST).</span><span class="sxs-lookup"><span data-stu-id="cb933-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="cb933-126">Il linguaggio CSDL seguente definisce un contenitore di entità con due set di entità per il tipo di entità `Book`:</span><span class="sxs-lookup"><span data-stu-id="cb933-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="cb933-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb933-127">See also</span></span>

- [<span data-ttu-id="cb933-128">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="cb933-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="cb933-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="cb933-129">Entity Data Model</span></span>](entity-data-model.md)
