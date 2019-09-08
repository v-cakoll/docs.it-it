---
title: entità finale del set di associazioni
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 48ba84d46e380462405551cc2d826d84368b351a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786939"
---
# <a name="association-set-end"></a><span data-ttu-id="d13c5-102">entità finale del set di associazioni</span><span class="sxs-lookup"><span data-stu-id="d13c5-102">association set end</span></span>
<span data-ttu-id="d13c5-103">Un'entità *finale del set di associazioni* identifica il tipo di [entità](entity-type.md) e il [set di entità](entity-set.md) alla fine di un set di [associazioni](association-set.md).</span><span class="sxs-lookup"><span data-stu-id="d13c5-103">An *association set end* identifies the [entity type](entity-type.md) and the [entity set](entity-set.md) at the end of an [association set](association-set.md).</span></span> <span data-ttu-id="d13c5-104">Le entità finali del set di associazioni sono definite come parte di un set di associazioni. Un set di associazioni deve disporre esattamente di due entità finali.</span><span class="sxs-lookup"><span data-stu-id="d13c5-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="d13c5-105">Una definizione di entità finale del set di associazioni contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d13c5-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="d13c5-106">Uno dei tipi di entità coinvolti nel set di associazioni</span><span class="sxs-lookup"><span data-stu-id="d13c5-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="d13c5-107">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="d13c5-107">(Required)</span></span>  
  
- <span data-ttu-id="d13c5-108">Il set di entità per il tipo di entità coinvolto nel set di associazioni</span><span class="sxs-lookup"><span data-stu-id="d13c5-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="d13c5-109">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="d13c5-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13c5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d13c5-110">Example</span></span>  
 <span data-ttu-id="d13c5-111">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="d13c5-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="d13c5-113">Nel diagramma seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d13c5-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="d13c5-114">Le fini del set di associazioni sono i set di entità `Books` e `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="d13c5-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="d13c5-115">Bi nel set `Books` di entità rappresenta un'istanza `Book` del tipo di entità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d13c5-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="d13c5-116">Analogamente, PJ rappresenta `Publisher` un'istanza `Publishers` nel set di entità.</span><span class="sxs-lookup"><span data-stu-id="d13c5-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="d13c5-117">BiPj rappresenta un'istanza dell' `PublishedBy` associazione `PublishedBy` nel set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="d13c5-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot che mostra un esempio di set.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="d13c5-119">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio DSL denominato Conceptual Schema Definition Language ([CSDL](./ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="d13c5-119">The [ADO.NET Entity Framework](./ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d13c5-120">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente.</span><span class="sxs-lookup"><span data-stu-id="d13c5-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="d13c5-121">Si noti che le entità finali del set di associazioni sono definite come parte di ogni definizione di set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="d13c5-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d13c5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d13c5-122">See also</span></span>

- [<span data-ttu-id="d13c5-123">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d13c5-123">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="d13c5-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d13c5-124">Entity Data Model</span></span>](entity-data-model.md)
