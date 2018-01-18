---
title: set di associazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fa977f69951184629f4e9555f524f074a09ce96a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="association-set"></a><span data-ttu-id="82c13-102">set di associazioni</span><span class="sxs-lookup"><span data-stu-id="82c13-102">association set</span></span>
<span data-ttu-id="82c13-103">Un *set di associazioni* è un contenitore logico per [associazione](../../../../docs/framework/data/adonet/association-type.md) istanze dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="82c13-103">An *association set* is a logical container for [association](../../../../docs/framework/data/adonet/association-type.md) instances of the same type.</span></span> <span data-ttu-id="82c13-104">Un set di associazioni non è un costrutto di modellazione dati, ovvero non descrive la struttura di dati o relazioni.</span><span class="sxs-lookup"><span data-stu-id="82c13-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="82c13-105">Un set di associazioni, invece, fornisce un costrutto per un ambiente host o di archiviazione (ad esempio Common Language Runtime o un database SQL Server) per raggruppare le istanze dell'associazione in modo che se ne possa eseguire il mapping a un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="82c13-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="82c13-106">Un set di associazioni è definito all'interno di un [contenitore di entità](../../../../docs/framework/data/adonet/entity-container.md), ovvero un raggruppamento logico di [set di entità](../../../../docs/framework/data/adonet/entity-set.md) e set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="82c13-106">An association set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="82c13-107">Una definizione per un set di associazioni contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82c13-107">A definition for an association set contains the following information:</span></span>  
  
-   <span data-ttu-id="82c13-108">Il nome del set di associazioni</span><span class="sxs-lookup"><span data-stu-id="82c13-108">The association set name.</span></span> <span data-ttu-id="82c13-109">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="82c13-109">(Required)</span></span>  
  
-   <span data-ttu-id="82c13-110">L'associazione della quale conterrà le istanze</span><span class="sxs-lookup"><span data-stu-id="82c13-110">The association of which it will contain instances.</span></span> <span data-ttu-id="82c13-111">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="82c13-111">(Required)</span></span>  
  
-   <span data-ttu-id="82c13-112">Due [estremità del set di associazioni](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="82c13-112">Two [association set ends](../../../../docs/framework/data/adonet/association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82c13-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="82c13-113">Example</span></span>  
 <span data-ttu-id="82c13-114">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="82c13-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="82c13-115">Anche se le informazioni sui set di associazioni non sono contenute nel diagramma, nel diagramma successivo viene illustrato un esempio di set di associazioni e di set di entità basato su questo modello.</span><span class="sxs-lookup"><span data-stu-id="82c13-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 <span data-ttu-id="82c13-116">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="82c13-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="82c13-117">Nell'esempio seguente vengono illustrati un set di associazioni (`PublishedBy`) e due set di entità (`Books` e `Publishers`) basati sul modello concettuale illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="82c13-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="82c13-118">Business Intelligence nel `Books` set di entità rappresenta un'istanza del `Book` il tipo di entità in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82c13-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="82c13-119">Analogamente, Pj rappresenta un `Publisher` dell'istanza nel `Publishers` set di entità.</span><span class="sxs-lookup"><span data-stu-id="82c13-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="82c13-120">BiPj rappresenta un'istanza di `PublishedBy` associazione nel `PublishedBy` set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="82c13-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="82c13-121">![Esempio](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="82c13-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="82c13-122">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="82c13-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="82c13-123">Il linguaggio CSDL seguente definisce un contenitore di entità con un set di associazioni per ogni associazione nel diagramma precedente.</span><span class="sxs-lookup"><span data-stu-id="82c13-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="82c13-124">Si noti che il nome e l'associazione per ogni set di associazioni sono definiti tramite attributi XML.</span><span class="sxs-lookup"><span data-stu-id="82c13-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="82c13-125">È possibile definire più set di associazioni per l'associazione, purché Nessuna condivisione di set di due entità un [fine del set di associazioni](../../../../docs/framework/data/adonet/association-set-end.md).</span><span class="sxs-lookup"><span data-stu-id="82c13-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](../../../../docs/framework/data/adonet/association-set-end.md).</span></span> <span data-ttu-id="82c13-126">Nel linguaggio seguente viene definito un contenitore di entità con due set di associazioni per l'associazione `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="82c13-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="82c13-127">Si noti che più set di entità sono stati definiti per i tipi di entità `Book` e `Author` e che nessun set di associazioni condivide un'entità finale del set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="82c13-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="82c13-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c13-128">See Also</span></span>  
 [<span data-ttu-id="82c13-129">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="82c13-129">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="82c13-130">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="82c13-130">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="82c13-131">proprietà di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="82c13-131">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)
