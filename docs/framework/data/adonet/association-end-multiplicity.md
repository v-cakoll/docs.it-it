---
title: "molteplicità di entità finale dell'associazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0d66c141b83402b011fdebbb04c0b2a9adc5ec29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="b1dc7-102">molteplicità di entità finale dell'associazione</span><span class="sxs-lookup"><span data-stu-id="b1dc7-102">association end multiplicity</span></span>
<span data-ttu-id="b1dc7-103">*Molteplicità di entità finale associazione* definisce il numero di [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) istanze che possono essere a un estremo di una [associazione](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="b1dc7-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="b1dc7-104">Una molteplicità di entità finale dell'associazione può disporre di uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1dc7-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="b1dc7-105">uno (1): indica che nell'entità finale dell'associazione è presente esattamente un'istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="b1dc7-106">zero o uno (0..1): indica che nell'entità finale dell'associazione sono presenti zero o una istanza del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="b1dc7-107">molte (*): indica che nell'entità finale dell'associazione sono presenti zero, una o più istanze del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-107">many (*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="b1dc7-108">Un'associazione è spesso caratterizzata dalle molteplicità di entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="b1dc7-109">Se, ad esempio, le entità finali di un'associazione dispongono di molteplicità uno (1) e molti (*), l'associazione è detta associazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-109">For example, if the ends of an association have multiplicities one (1) and many (*), the association is called a one-to-many association.</span></span> <span data-ttu-id="b1dc7-110">Nell'esempio seguente, l'associazione `PublishedBy` è un'associazione uno-a-molti (un editore pubblica molti libri e un libro viene pubblicato da un solo editore).</span><span class="sxs-lookup"><span data-stu-id="b1dc7-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="b1dc7-111">L'associazione `WrittenBy` è un'associazione molti-a-molti (un libro può avere più autori e un autore può scrivere più libri).</span><span class="sxs-lookup"><span data-stu-id="b1dc7-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1dc7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1dc7-112">Example</span></span>  
 <span data-ttu-id="b1dc7-113">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="b1dc7-114">Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="b1dc7-115">La molteplicità dell'entità finale `Publisher` è uno (1) e la molteplicità dell'entità finale `Book` è molti (*).</span><span class="sxs-lookup"><span data-stu-id="b1dc7-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (*).</span></span>  
  
 <span data-ttu-id="b1dc7-116">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="b1dc7-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="b1dc7-117">ADO.NET Entity Framework Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="b1dc7-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="b1dc7-118">Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="b1dc7-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="b1dc7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1dc7-119">See Also</span></span>  
 [<span data-ttu-id="b1dc7-120">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b1dc7-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="b1dc7-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="b1dc7-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
