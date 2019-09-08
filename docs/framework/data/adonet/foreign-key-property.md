---
title: proprietà di chiave esterna
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: e2f41c2db9aea26c7954a99ebf3f40b03e8df735
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795037"
---
# <a name="foreign-key-property"></a><span data-ttu-id="7dbaa-102">proprietà di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="7dbaa-102">foreign key property</span></span>
<span data-ttu-id="7dbaa-103">Una *proprietà di chiave esterna* nel Entity Data Model (EDM) è una [Proprietà](property.md) di tipo primitivo (o un set di proprietà di tipo primitivo) in un [tipo di entità](entity-type.md) che contiene la chiave di [entità](entity-key.md) di un altro tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](property.md) (or a set of primitive type properties) on an [entity type](entity-type.md) that contains the [entity key](entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="7dbaa-104">Una proprietà di chiave esterna è analoga a una colonna di chiave esterna in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="7dbaa-105">Nello stesso modo in cui le colonne chiave esterna vengono utilizzate in un database relazionale per creare relazioni tra le righe nelle tabelle, le proprietà di chiave esterna in un modello concettuale vengono utilizzate per stabilire [associazioni](association-type.md) tra tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](association-type.md) between entity types.</span></span> <span data-ttu-id="7dbaa-106">Un [vincolo di integrità referenziale](referential-integrity-constraint.md) viene utilizzato per definire un'associazione tra due tipi di entità quando uno dei tipi dispone di una proprietà di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-106">A [referential integrity constraint](referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dbaa-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7dbaa-107">Example</span></span>  
 <span data-ttu-id="7dbaa-108">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="7dbaa-109">Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="7dbaa-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Esempio di modello di vincolo referenziale")</span><span class="sxs-lookup"><span data-stu-id="7dbaa-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="7dbaa-111">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-111">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="7dbaa-112">Il linguaggio CSDL seguente usa la proprietà di chiave esterna `PublisherId` per definire un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.</span><span class="sxs-lookup"><span data-stu-id="7dbaa-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="7dbaa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7dbaa-113">See also</span></span>

- [<span data-ttu-id="7dbaa-114">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7dbaa-114">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="7dbaa-115">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7dbaa-115">Entity Data Model</span></span>](entity-data-model.md)
