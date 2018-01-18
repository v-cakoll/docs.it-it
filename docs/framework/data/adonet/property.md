---
title: "proprietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 50cd2f2678d304af8b898380645424e0635891d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="property"></a><span data-ttu-id="e5095-102">proprietà</span><span class="sxs-lookup"><span data-stu-id="e5095-102">property</span></span>
<span data-ttu-id="e5095-103">*Proprietà* sono gli elementi fondamentali di [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) e [tipi complessi](../../../../docs/framework/data/adonet/complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="e5095-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="e5095-104">Le proprietà definiscono la forma e le caratteristiche dei dati che saranno contenuti in un'istanza di un tipo di entità o in un'istanza di un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="e5095-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="e5095-105">Le proprietà in un modello concettuale sono analoghe alle proprietà definite su una classe.</span><span class="sxs-lookup"><span data-stu-id="e5095-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="e5095-106">Nello stesso modo in cui le proprietà su una classe definiscono la forma della classe e forniscono informazioni su oggetti, le proprietà in un modello concettuale definiscono la forma di un tipo di entità e forniscono informazioni su istanze del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="e5095-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5095-107">Le proprietà descritte in questo argomento sono diverse dalle proprietà di navigazione.</span><span class="sxs-lookup"><span data-stu-id="e5095-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="e5095-108">Per ulteriori informazioni, vedere [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="e5095-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="e5095-109">Una definizione di proprietà contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5095-109">A property definition contains the following information:</span></span>  
  
-   <span data-ttu-id="e5095-110">Un nome di proprietà</span><span class="sxs-lookup"><span data-stu-id="e5095-110">A property name.</span></span> <span data-ttu-id="e5095-111">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="e5095-111">(Required)</span></span>  
  
-   <span data-ttu-id="e5095-112">Un tipo di proprietà</span><span class="sxs-lookup"><span data-stu-id="e5095-112">A property type.</span></span> <span data-ttu-id="e5095-113">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="e5095-113">(Required)</span></span>  
  
-   <span data-ttu-id="e5095-114">Un set di [facet](../../../../docs/framework/data/adonet/facet.md).</span><span class="sxs-lookup"><span data-stu-id="e5095-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="e5095-115">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="e5095-115">(Optional)</span></span>  
  
 <span data-ttu-id="e5095-116">Una proprietà può contenere dati primitivi (ad esempio una stringa, un Integer o un valore booleano) o dati strutturati (ad esempio un tipo complesso).</span><span class="sxs-lookup"><span data-stu-id="e5095-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="e5095-117">Le proprietà di tipo primitivo sono dette anche proprietà scalari.</span><span class="sxs-lookup"><span data-stu-id="e5095-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="e5095-118">Per ulteriori informazioni, vedere [Entity Data Model: tipi di dati primitivi](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e5095-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5095-119">Un tipo complesso può, di per sé, disporre di proprietà che sono tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="e5095-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5095-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5095-120">Example</span></span>  
 <span data-ttu-id="e5095-121">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="e5095-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="e5095-122">Ogni tipo di entità dispone di diverse proprietà, anche se nel diagramma non sono contenute informazioni sul tipo per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="e5095-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="e5095-123">Le proprietà di [le chiavi di entità](../../../../docs/framework/data/adonet/entity-key.md) vengono indicate con (Key).</span><span class="sxs-lookup"><span data-stu-id="e5095-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 <span data-ttu-id="e5095-124">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="e5095-124">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="e5095-125">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="e5095-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e5095-126">Il seguente linguaggio CSDL definisce il tipo di entità `Book` (come illustrato nel diagramma precedente) e indica il tipo e il nome di ogni proprietà usando attributi XML.</span><span class="sxs-lookup"><span data-stu-id="e5095-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="e5095-127">Un facet facoltativo, `Nullable`, è definito anche tramite un attributo XML.</span><span class="sxs-lookup"><span data-stu-id="e5095-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="e5095-128">È possibile che una delle proprietà illustrate nel diagramma sia una proprietà di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="e5095-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="e5095-129">La proprietà `Address` sul tipo di entità `Publisher`, ad esempio, potrebbe essere una proprietà di tipo complesso costituita da diverse proprietà scalari, quali `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="e5095-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="e5095-130">La rappresentazione CSDL di tale tipo complesso sarà come segue:</span><span class="sxs-lookup"><span data-stu-id="e5095-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e5095-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5095-131">See Also</span></span>  
 [<span data-ttu-id="e5095-132">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e5095-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="e5095-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e5095-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
