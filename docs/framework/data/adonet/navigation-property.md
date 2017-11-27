---
title: "proprietà di navigazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1677ab1be071eeabd72b29c7ce61d01aaf6164a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-property"></a><span data-ttu-id="5f7b4-102">proprietà di navigazione</span><span class="sxs-lookup"><span data-stu-id="5f7b4-102">navigation property</span></span>
<span data-ttu-id="5f7b4-103">Oggetto *proprietà di navigazione* è una proprietà facoltativa su un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) che consente di navigare da un' [fine](../../../../docs/framework/data/adonet/association-end.md) di un [associazione](../../../../docs/framework/data/adonet/association-type.md) per l'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="5f7b4-104">A differenza degli altri [proprietà](../../../../docs/framework/data/adonet/property.md), le proprietà di navigazione non contengono dati.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="5f7b4-105">Una definizione di proprietà di navigazione include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5f7b4-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="5f7b4-106">Un nome</span><span class="sxs-lookup"><span data-stu-id="5f7b4-106">A name.</span></span> <span data-ttu-id="5f7b4-107">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-107">(Required)</span></span>  
  
-   <span data-ttu-id="5f7b4-108">L'associazione all'interno della quale naviga</span><span class="sxs-lookup"><span data-stu-id="5f7b4-108">The association that it navigates.</span></span> <span data-ttu-id="5f7b4-109">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-109">(Required)</span></span>  
  
-   <span data-ttu-id="5f7b4-110">Le entità finali dell'associazione all'interno della quale naviga</span><span class="sxs-lookup"><span data-stu-id="5f7b4-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="5f7b4-111">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-111">(Required)</span></span>  
  
 <span data-ttu-id="5f7b4-112">Si noti che le proprietà di navigazione sono facoltative in entrambi tipi di entità nelle entità finali di un'associazione.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="5f7b4-113">Se si definisce una proprietà di navigazione su un tipo di entità nell'entità finale di un'associazione, non è necessario definire una proprietà di navigazione sul tipo di entità nell'altra entità finale dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="5f7b4-114">Il tipo di dati di una proprietà di navigazione è determinato dal [molteplicità](../../../../docs/framework/data/adonet/association-end-multiplicity.md) del relativo remoto [finale dell'associazione](../../../../docs/framework/data/adonet/association-end.md).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="5f7b4-115">Si supponga ad esempio che esista una proprietà di navigazione, `OrdersNavProp`, in un tipo di entità `Customer` e che tale proprietà navighi in un'associazione uno-a-molti tra `Customer` e `Order`.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="5f7b4-116">Poiché l'entità finale dell'associazione remota per la proprietà di navigazione dispone della molteplicità molti (*), il relativo tipo di dati è una raccolta (di `Order`).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-116">Because the remote association end for the navigation property has multiplicity of many (*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="5f7b4-117">Analogamente, se esiste una proprietà di navigazione `CustomerNavProp` nel tipo di entità `Order`, il relativo tipo di dati sarebbe `Customer`, perché la molteplicità dell'entità finale remota è uno (1).</span><span class="sxs-lookup"><span data-stu-id="5f7b4-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f7b4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f7b4-118">Example</span></span>  
 <span data-ttu-id="5f7b4-119">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="5f7b4-120">Le proprietà di navigazione, `Publisher` e `Authors`, vengono definite nel tipo di entità Book.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="5f7b4-121">La proprietà di navigazione `Books` viene definita sia nel tipo di entità Publisher che nel tipo di entità `Author`.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="5f7b4-122">![Modello con le proprietà di navigazione](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="5f7b4-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="5f7b4-123">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5f7b4-124">Il linguaggio CSDL seguente definisce il tipo di entità `Book` illustrato nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="5f7b4-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="5f7b4-125">Si noti che, per comunicare le informazioni necessarie per definire una proprietà di navigazione, vengono usati attributi XML: l'attributo `Name` contiene il nome della proprietà, `Relationship` contiene il nome dell'associazione all'interno della quale naviga e `FromRole` e `ToRole` contengono le entità finali dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="5f7b4-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7b4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f7b4-126">See Also</span></span>  
 [<span data-ttu-id="5f7b4-127">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="5f7b4-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="5f7b4-128">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="5f7b4-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
