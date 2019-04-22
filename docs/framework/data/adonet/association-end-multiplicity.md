---
title: molteplicità di entità finale dell'associazione
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 59eed56204543adf405cfc7c71a49697a9e18374
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135031"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="d8b10-102">molteplicità di entità finale dell'associazione</span><span class="sxs-lookup"><span data-stu-id="d8b10-102">association end multiplicity</span></span>
<span data-ttu-id="d8b10-103">*Molteplicità di estremità dell'associazione* definisce il numero di [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) istanze che possono essere a un estremo di una [associazione](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="d8b10-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="d8b10-104">Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8b10-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="d8b10-105">uno (1): Indica a che tale istanza del tipo esattamente un'entità è presente l'estremità dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d8b10-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="d8b10-106">zero o uno (0..1): Indica che presenti zero o più istanze del tipo di entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d8b10-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="d8b10-107">molte (\*): indica che da zero, uno o più istanze del tipo di entità sono presenti entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d8b10-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="d8b10-108">Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d8b10-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="d8b10-109">Ad esempio, se le entità finali di un'associazione dispongono di molteplicità uno (1) e molti (\*), l'associazione viene definita un'associazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="d8b10-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="d8b10-110">Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore).</span><span class="sxs-lookup"><span data-stu-id="d8b10-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="d8b10-111">L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).</span><span class="sxs-lookup"><span data-stu-id="d8b10-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b10-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8b10-112">Example</span></span>  
 <span data-ttu-id="d8b10-113">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="d8b10-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="d8b10-114">Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="d8b10-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="d8b10-115">La molteplicità del `Publisher` finale è uno (1) e la molteplicità dell'entità la `Book` finale è molti (\*).</span><span class="sxs-lookup"><span data-stu-id="d8b10-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="d8b10-117">ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="d8b10-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d8b10-118">Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="d8b10-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="d8b10-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b10-119">See also</span></span>

- [<span data-ttu-id="d8b10-120">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d8b10-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="d8b10-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="d8b10-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
