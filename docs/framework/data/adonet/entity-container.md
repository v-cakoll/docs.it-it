---
title: contenitore di entità
ms.date: 03/30/2017
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
ms.openlocfilehash: ed2123629c61b179e07e86effa0c39d9a3222b62
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="entity-container"></a><span data-ttu-id="81da2-102">contenitore di entità</span><span class="sxs-lookup"><span data-stu-id="81da2-102">entity container</span></span>
<span data-ttu-id="81da2-103">Un *contenitore di entità* è un raggruppamento logico di [set di entità](../../../../docs/framework/data/adonet/entity-set.md), [set di associazioni](../../../../docs/framework/data/adonet/association-set.md), e [funzione importazioni](../../../../docs/framework/data/adonet/model-declared-function.md).</span><span class="sxs-lookup"><span data-stu-id="81da2-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="81da2-104">Le affermazioni seguenti relative a un contenitore di entità definito in un modello concettuale devono essere vere:</span><span class="sxs-lookup"><span data-stu-id="81da2-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
-   <span data-ttu-id="81da2-105">In ogni modello concettuale deve essere definito almeno un contenitore di entità.</span><span class="sxs-lookup"><span data-stu-id="81da2-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
-   <span data-ttu-id="81da2-106">Il contenitore di entità deve disporre di un nome univoco all'interno di ogni modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="81da2-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="81da2-107">Un contenitore di entità può definire set di entità o set di associazioni che usano i tipi o le associazioni di entità definite in uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="81da2-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="81da2-108">Per ulteriori informazioni, vedere [Entity Data Model: spazi dei nomi](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="81da2-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81da2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="81da2-109">Example</span></span>  
 <span data-ttu-id="81da2-110">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="81da2-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="81da2-111">Per altre informazioni, vedere l'esempio successivo.</span><span class="sxs-lookup"><span data-stu-id="81da2-111">See the next example for more information.</span></span>  
  
 <span data-ttu-id="81da2-112">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="81da2-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="81da2-113">Anche se nel diagramma non sono contenute informazioni sul contenitore di entità, il modello concettuale deve definire un contenitore di entità.</span><span class="sxs-lookup"><span data-stu-id="81da2-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="81da2-114">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio DSL detto linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="81da2-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="81da2-115">Il linguaggio CSDL seguente definisce un contenitore di entità per il modello concettuale illustrato nel diagramma precedente.</span><span class="sxs-lookup"><span data-stu-id="81da2-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="81da2-116">Si noti che il nome del contenitore di entità è definito in un attributo XML.</span><span class="sxs-lookup"><span data-stu-id="81da2-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="81da2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81da2-117">See Also</span></span>  
 [<span data-ttu-id="81da2-118">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="81da2-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="81da2-119">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="81da2-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
