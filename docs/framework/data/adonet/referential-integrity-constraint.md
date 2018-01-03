---
title: "vincolo di integrità referenziale"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 232098a4940e223fd8553eefa4964777b1695c5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="288b9-102">vincolo di integrità referenziale</span><span class="sxs-lookup"><span data-stu-id="288b9-102">referential integrity constraint</span></span>
<span data-ttu-id="288b9-103">Oggetto *vincolo di integrità referenziale* in Entity Data Model (EDM) è simile a un vincolo di integrità referenziale in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="288b9-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="288b9-104">Nello stesso modo che una colonna (colonne) da una tabella di database può fare riferimento o la chiave primaria di un'altra tabella, una [proprietà](../../../../docs/framework/data/adonet/property.md) (o proprietà) di un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) possono fare riferimento il [chiave di entità ](../../../../docs/framework/data/adonet/entity-key.md) di un altro tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="288b9-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="288b9-105">Il tipo di entità a cui fa riferimento viene chiamato il *finale principale* del vincolo.</span><span class="sxs-lookup"><span data-stu-id="288b9-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="288b9-106">Il tipo di entità che fa riferimento l'entità finale principale viene chiamato il *estremità dipendente* del vincolo.</span><span class="sxs-lookup"><span data-stu-id="288b9-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="288b9-107">Un vincolo di integrità referenziale è definito come parte di un [associazione](../../../../docs/framework/data/adonet/association-type.md) tra due tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="288b9-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="288b9-108">La definizione per un vincolo di integrità referenziale specifica le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="288b9-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
-   <span data-ttu-id="288b9-109">Entità finale principale del vincolo</span><span class="sxs-lookup"><span data-stu-id="288b9-109">The principal end of the constraint.</span></span> <span data-ttu-id="288b9-110">(un tipo di entità alla cui chiave di entità è fatto riferimento dall'entità finale dipendente).</span><span class="sxs-lookup"><span data-stu-id="288b9-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
-   <span data-ttu-id="288b9-111">Chiave di entità dell'entità finale principale.</span><span class="sxs-lookup"><span data-stu-id="288b9-111">The entity key of the principal end.</span></span>  
  
-   <span data-ttu-id="288b9-112">Entità finale dipendente del vincolo</span><span class="sxs-lookup"><span data-stu-id="288b9-112">The dependent end of the constraint.</span></span> <span data-ttu-id="288b9-113">(un tipo di entità che dispone di una o più proprietà che fanno riferimento alla chiave di entità dell'entità finale principale).</span><span class="sxs-lookup"><span data-stu-id="288b9-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
-   <span data-ttu-id="288b9-114">La proprietà o le proprietà di riferimento dell'entità finale dipendente.</span><span class="sxs-lookup"><span data-stu-id="288b9-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="288b9-115">Lo scopo dei vincoli di integrità referenziali in EDM è di assicurare che esistano sempre associazioni valide.</span><span class="sxs-lookup"><span data-stu-id="288b9-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="288b9-116">Per ulteriori informazioni, vedere [proprietà di chiave esterna](../../../../docs/framework/data/adonet/foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="288b9-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="288b9-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="288b9-117">Example</span></span>  
 <span data-ttu-id="288b9-118">Nel diagramma seguente viene illustrato un modello concettuale con due associazioni: `WrittenBy` e `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="288b9-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="288b9-119">Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="288b9-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="288b9-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="288b9-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="288b9-121">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="288b9-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="288b9-122">Nel seguente linguaggio CSDL viene definito un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.</span><span class="sxs-lookup"><span data-stu-id="288b9-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="288b9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="288b9-123">See Also</span></span>  
 [<span data-ttu-id="288b9-124">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="288b9-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="288b9-125">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="288b9-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
