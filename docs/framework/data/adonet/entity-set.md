---
title: set di entità
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: b74d6bf373925ac90a998e2c4425c053e533f82a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784000"
---
# <a name="entity-set"></a><span data-ttu-id="97572-102">set di entità</span><span class="sxs-lookup"><span data-stu-id="97572-102">entity set</span></span>
<span data-ttu-id="97572-103">Un *set di entità* è un contenitore logico per istanze di un [tipo di entità](entity-type.md) e istanze di qualsiasi tipo derivato da tale tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-103">An *entity set* is a logical container for instances of an [entity type](entity-type.md) and instances of any type derived from that entity type.</span></span> <span data-ttu-id="97572-104">Per informazioni sui tipi derivati, [vedere Entity Data Model: Ereditarietà](entity-data-model-inheritance.md).) La relazione tra un tipo di entità e un set di entità è analoga alla relazione tra una riga e una tabella in un database relazionale: Analogamente a una riga, un tipo di entità descrive la struttura dei dati e, come una tabella, un set di entità contiene istanze di una determinata struttura.</span><span class="sxs-lookup"><span data-stu-id="97572-104">(For information about derived types, see [Entity Data Model: Inheritance](entity-data-model-inheritance.md).) The relationship between an entity type and an entity set is analogous to the relationship between a row and a table in a relational database: Like a row, an entity type describes data structure, and, like a table, an entity set contains instances of a given structure.</span></span> <span data-ttu-id="97572-105">Un set di entità non è un costrutto di modellazione dati e non descrive la struttura di dati.</span><span class="sxs-lookup"><span data-stu-id="97572-105">An entity set is not a data modeling construct; it does not describe the structure of data.</span></span> <span data-ttu-id="97572-106">Un set di entità, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze del tipo di entità in modo che se ne possa eseguire il mapping a un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="97572-106">Instead, an entity set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group entity type instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="97572-107">Un set di entità viene definito all'interno di un [contenitore di entità](entity-container.md), ovvero un raggruppamento logico di set di entità e [set di associazioni](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="97572-107">An entity set is defined within an [entity container](entity-container.md), which is a logical grouping of entity sets and [association sets](association-set.md).</span></span>  
  
 <span data-ttu-id="97572-108">Perché un'istanza di un tipo di entità esista in un set di entità, devono essere osservate le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="97572-108">For an entity type instance to exist in an entity set, the following must be true:</span></span>  
  
- <span data-ttu-id="97572-109">Il tipo dell'istanza è lo stesso del tipo di entità su cui si basa il set di entità oppure il tipo dell'istanza è un sottotipo del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-109">The type of the instance is either the same as the entity type on which the entity set is based, or the type of the instance is a subtype of the entity type.</span></span>  
  
- <span data-ttu-id="97572-110">La [chiave di entità](entity-key.md) per l'istanza è univoca all'interno del set di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-110">The [entity key](entity-key.md) for the instance is unique within the entity set.</span></span>  
  
- <span data-ttu-id="97572-111">L'istanza non esiste in nessun altro set di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-111">The instance does not exist in any other entity set.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="97572-112">È possibile definire più set di entità tramite lo stesso tipo di entità, ma un'istanza di un determinato tipo di entità può esistere in un solo set di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-112">Multiple entity sets can be defined using the same entity type, but an instance of a given entity type can only exist in one entity set.</span></span>  
  
 <span data-ttu-id="97572-113">Non è necessario definire un set di entità per ogni tipo di entità in un modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="97572-113">You do not have to define an entity set for each entity type in a conceptual model.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97572-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="97572-114">Example</span></span>  
 <span data-ttu-id="97572-115">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="97572-115">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/entity-set/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="97572-117">Nel diagramma seguente vengono illustrati due set di entità (`Books` e `Publishers`) e un set di associazioni (`PublishedBy`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="97572-117">The following diagram shows two entity sets (`Books` and `Publishers`) and an association set (`PublishedBy`) based on the conceptual model shown above.</span></span> <span data-ttu-id="97572-118">Bi nel set `Books` di entità rappresenta un'istanza `Book` del tipo di entità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="97572-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="97572-119">Analogamente, PJ rappresenta `Publisher` un'istanza `Publishers` nel set di entità.</span><span class="sxs-lookup"><span data-stu-id="97572-119">Similarly, Pj represent a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="97572-120">BiPj rappresenta un'istanza dell' `PublishedBy` associazione `PublishedBy` nel set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="97572-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot che mostra un esempio di set.](./media/entity-set/sets-example-association.gif)  
  
 <span data-ttu-id="97572-122">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="97572-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="97572-123">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di entità per ogni tipo di entità nel modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="97572-123">The following CSDL defines an entity container with one entity set for each entity type in the conceptual model shown above.</span></span> <span data-ttu-id="97572-124">Si noti che il nome e il tipo di entità per ogni set di entità sono definiti tramite attributi XML.</span><span class="sxs-lookup"><span data-stu-id="97572-124">Note that the name and entity type for each entity set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="97572-125">È possibile definire più set di entità per tipo (MEST).</span><span class="sxs-lookup"><span data-stu-id="97572-125">It is possible to define multiple entity sets per type (MEST).</span></span> <span data-ttu-id="97572-126">Il linguaggio CSDL seguente definisce un contenitore di entità con due set di entità per il tipo di entità `Book`:</span><span class="sxs-lookup"><span data-stu-id="97572-126">The following CSDL defines an entity container with two entity sets for the `Book` entity type:</span></span>  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a><span data-ttu-id="97572-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97572-127">See also</span></span>

- [<span data-ttu-id="97572-128">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="97572-128">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="97572-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="97572-129">Entity Data Model</span></span>](entity-data-model.md)
