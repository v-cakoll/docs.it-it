---
title: molteplicità di entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 151b15a6df021a25f6c3ecea00af147c6b7196ff
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185675"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="8b018-102">molteplicità di entità finale dell'associazione</span><span class="sxs-lookup"><span data-stu-id="8b018-102">association end multiplicity</span></span>
<span data-ttu-id="8b018-103">*Molteplicità di estremità dell'associazione* definisce il numero di [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) istanze che possono essere a un estremo di una [associazione](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="8b018-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="8b018-104">Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b018-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="8b018-105">uno (1): Indica a che tale istanza del tipo esattamente un'entità è presente l'estremità dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="8b018-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="8b018-106">zero o uno (0..1): Indica che presenti zero o più istanze del tipo di entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="8b018-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="8b018-107">molte (\*): indica che da zero, uno o più istanze del tipo di entità sono presenti entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="8b018-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="8b018-108">Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="8b018-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="8b018-109">Ad esempio, se le entità finali di un'associazione dispongono di molteplicità uno (1) e molti (\*), l'associazione viene definita un'associazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="8b018-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="8b018-110">Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore).</span><span class="sxs-lookup"><span data-stu-id="8b018-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="8b018-111">L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).</span><span class="sxs-lookup"><span data-stu-id="8b018-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b018-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b018-112">Example</span></span>  
 <span data-ttu-id="8b018-113">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="8b018-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="8b018-114">Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="8b018-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="8b018-115">La molteplicità del `Publisher` finale è uno (1) e la molteplicità dell'entità la `Book` finale è molti (\*).</span><span class="sxs-lookup"><span data-stu-id="8b018-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 <span data-ttu-id="8b018-116">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="8b018-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="8b018-117">ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="8b018-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="8b018-118">Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="8b018-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="8b018-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b018-119">See also</span></span>
- [<span data-ttu-id="8b018-120">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8b018-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="8b018-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="8b018-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
