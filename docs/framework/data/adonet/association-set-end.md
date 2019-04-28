---
title: entità finale del set di associazioni
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769578"
---
# <a name="association-set-end"></a><span data-ttu-id="127ec-102">entità finale del set di associazioni</span><span class="sxs-lookup"><span data-stu-id="127ec-102">association set end</span></span>
<span data-ttu-id="127ec-103">Un *fine del set di associazioni* identifica le [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e il [set di entità](../../../../docs/framework/data/adonet/entity-set.md) alla fine di un [set di associazioni](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="127ec-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="127ec-104">Le entità finali del set di associazioni sono definite come parte di un set di associazioni. Un set di associazioni deve disporre esattamente di due entità finali.</span><span class="sxs-lookup"><span data-stu-id="127ec-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="127ec-105">Una definizione di entità finale del set di associazioni contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="127ec-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="127ec-106">Uno dei tipi di entità coinvolti nel set di associazioni</span><span class="sxs-lookup"><span data-stu-id="127ec-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="127ec-107">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="127ec-107">(Required)</span></span>  
  
- <span data-ttu-id="127ec-108">Il set di entità per il tipo di entità coinvolto nel set di associazioni</span><span class="sxs-lookup"><span data-stu-id="127ec-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="127ec-109">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="127ec-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="127ec-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="127ec-110">Example</span></span>  
 <span data-ttu-id="127ec-111">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="127ec-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="127ec-113">Nel diagramma seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="127ec-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="127ec-114">Le fini del set di associazioni sono i set di entità `Books` e `Publishers`.</span><span class="sxs-lookup"><span data-stu-id="127ec-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="127ec-115">Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` tipo di entità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="127ec-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="127ec-116">Analogamente, Pj rappresenta un `Publisher` dell'istanza nel `Publishers` set di entità.</span><span class="sxs-lookup"><span data-stu-id="127ec-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="127ec-117">BiPj rappresenta un'istanza del `PublishedBy` association nel `PublishedBy` set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="127ec-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![Screenshot che mostra un esempio di set.](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="127ec-119">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio DSL denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="127ec-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="127ec-120">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente.</span><span class="sxs-lookup"><span data-stu-id="127ec-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="127ec-121">Si noti che le entità finali del set di associazioni sono definite come parte di ogni definizione di set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="127ec-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="127ec-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127ec-122">See also</span></span>

- [<span data-ttu-id="127ec-123">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="127ec-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="127ec-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="127ec-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
