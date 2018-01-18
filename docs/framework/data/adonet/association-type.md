---
title: tipo di associazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5349889017ea23701a17a92947d9750610a52f59
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="association-type"></a><span data-ttu-id="020e6-102">tipo di associazione</span><span class="sxs-lookup"><span data-stu-id="020e6-102">association type</span></span>
<span data-ttu-id="020e6-103">Un *tipo di associazione* (detto anche associazione) è il blocco predefinito fondamentale per una descrizione delle relazioni in Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="020e6-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="020e6-104">In un modello concettuale, un'associazione rappresenta una relazione tra due [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) (ad esempio `Customer` e `Order`).</span><span class="sxs-lookup"><span data-stu-id="020e6-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="020e6-105">In un'applicazione, un'istanza di un'associazione rappresenta un'associazione specifica (ad esempio, un'associazione tra un'istanza di `Customer` e una di `Order`).</span><span class="sxs-lookup"><span data-stu-id="020e6-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="020e6-106">Le istanze dell'associazione sono raggruppate logicamente in un [set di associazioni](../../../../docs/framework/data/adonet/association-set.md).</span><span class="sxs-lookup"><span data-stu-id="020e6-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="020e6-107">Una definizione di associazione contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="020e6-107">An association definition contains the following information:</span></span>  
  
-   <span data-ttu-id="020e6-108">Un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="020e6-108">A unique name.</span></span> <span data-ttu-id="020e6-109">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="020e6-109">(Required)</span></span>  
  
-   <span data-ttu-id="020e6-110">Due [estremità dell'associazione](../../../../docs/framework/data/adonet/association-end.md), uno per ogni tipo di entità nella relazione.</span><span class="sxs-lookup"><span data-stu-id="020e6-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="020e6-111">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="020e6-111">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="020e6-112">Un'associazione non può rappresentare una relazione tra più di due tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="020e6-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="020e6-113">Un'associazione può tuttavia definire una relazione interna specificando lo stesso tipo di entità per ognuna delle entità finali dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="020e6-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
-   <span data-ttu-id="020e6-114">Oggetto [vincolo di integrità referenziale](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="020e6-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="020e6-115">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="020e6-115">(Optional)</span></span>  
  
 <span data-ttu-id="020e6-116">Ogni entità finale dell'associazione deve specificare un [molteplicità di entità finale associazione](../../../../docs/framework/data/adonet/association-end-multiplicity.md) che indica il numero di istanze di tipi di entità che può essere un'estremità dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="020e6-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="020e6-117">Una molteplicità di entità finale dell'associazione può disporre di un valore pari a uno (1), zero o uno (0..1) o molti (\*).</span><span class="sxs-lookup"><span data-stu-id="020e6-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span> <span data-ttu-id="020e6-118">Le istanze di tipi di entità in un'entità finale di un'associazione è possibile accedere tramite [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) o le chiavi esterne se sono esposte in un tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="020e6-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="020e6-119">Per ulteriori informazioni, vedere [Entity Data Model: chiavi esterne](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="020e6-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="020e6-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="020e6-120">Example</span></span>  
 <span data-ttu-id="020e6-121">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `PublishedBy` e `WrittenBy`.</span><span class="sxs-lookup"><span data-stu-id="020e6-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="020e6-122">Le entità finali dell'associazione per l'associazione `PublishedBy` sono i tipi di entità `Book` e `Publisher`.</span><span class="sxs-lookup"><span data-stu-id="020e6-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="020e6-123">La molteplicità dell'entità finale `Publisher` è uno (1) e la molteplicità dell'entità finale `Book` è molti (\*), a indicare che un editore pubblica molti libri e un libro viene pubblicato da un solo editore.</span><span class="sxs-lookup"><span data-stu-id="020e6-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 <span data-ttu-id="020e6-124">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="020e6-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="020e6-125">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="020e6-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="020e6-126">Il linguaggio CSDL seguente definisce l'associazione `PublishedBy` illustrata nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="020e6-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="020e6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="020e6-127">See Also</span></span>  
 [<span data-ttu-id="020e6-128">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="020e6-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="020e6-129">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="020e6-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
