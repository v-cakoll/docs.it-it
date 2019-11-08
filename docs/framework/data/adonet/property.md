---
title: Proprietà
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: d1e20a6570c458041ec5d8ececbfa291ca9e4612
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735402"
---
# <a name="property"></a><span data-ttu-id="fd8ff-102">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fd8ff-102">property</span></span>
<span data-ttu-id="fd8ff-103">Le *Proprietà* sono i blocchi predefiniti fondamentali di [tipi di entità](entity-type.md) e [tipi complessi](complex-type.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-103">*Properties* are the fundamental building blocks of [entity types](entity-type.md) and [complex types](complex-type.md).</span></span> <span data-ttu-id="fd8ff-104">Le proprietà definiscono la forma e le caratteristiche dei dati che saranno contenuti in un'istanza di un tipo di entità o in un'istanza di un tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="fd8ff-105">Le proprietà in un modello concettuale sono analoghe alle proprietà definite su una classe.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="fd8ff-106">Nello stesso modo in cui le proprietà su una classe definiscono la forma della classe e forniscono informazioni su oggetti, le proprietà in un modello concettuale definiscono la forma di un tipo di entità e forniscono informazioni su istanze del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd8ff-107">Le proprietà descritte in questo argomento sono diverse dalle proprietà di navigazione.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="fd8ff-108">Per ulteriori informazioni, vedere [proprietà di navigazione](navigation-property.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-108">For more information, see [navigation properties](navigation-property.md).</span></span>  
  
 <span data-ttu-id="fd8ff-109">Una definizione di proprietà contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd8ff-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="fd8ff-110">Un nome di proprietà</span><span class="sxs-lookup"><span data-stu-id="fd8ff-110">A property name.</span></span> <span data-ttu-id="fd8ff-111">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-111">(Required)</span></span>  
  
- <span data-ttu-id="fd8ff-112">Un tipo di proprietà</span><span class="sxs-lookup"><span data-stu-id="fd8ff-112">A property type.</span></span> <span data-ttu-id="fd8ff-113">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-113">(Required)</span></span>  
  
- <span data-ttu-id="fd8ff-114">Set di [facet](facet.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-114">A set of [facets](facet.md).</span></span> <span data-ttu-id="fd8ff-115">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="fd8ff-115">(Optional)</span></span>  
  
 <span data-ttu-id="fd8ff-116">Una proprietà può contenere dati primitivi (ad esempio una stringa, un Integer o un valore booleano) o dati strutturati (ad esempio un tipo complesso).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="fd8ff-117">Le proprietà di tipo primitivo sono dette anche proprietà scalari.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="fd8ff-118">Per ulteriori informazioni, vedere [Entity Data Model: tipi di dati primitivi](entity-data-model-primitive-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-118">For more information, see [Entity Data Model: Primitive Data Types](entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd8ff-119">Un tipo complesso può, di per sé, disporre di proprietà che sono tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd8ff-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd8ff-120">Example</span></span>  
 <span data-ttu-id="fd8ff-121">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="fd8ff-122">Ogni tipo di entità dispone di diverse proprietà, anche se nel diagramma non sono contenute informazioni sul tipo per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="fd8ff-123">Le proprietà che sono [chiavi di entità](entity-key.md) sono denotate con (chiave).</span><span class="sxs-lookup"><span data-stu-id="fd8ff-123">Properties that are [entity keys](entity-key.md) are denoted with (Key).</span></span>  
  
 ![Modello di esempio con tre tipi di entità](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="fd8ff-125">Il [Entity Framework ADO.NET](./ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-125">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="fd8ff-126">Il seguente linguaggio CSDL definisce il tipo di entità `Book` (come illustrato nel diagramma precedente) e indica il tipo e il nome di ogni proprietà usando attributi XML.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="fd8ff-127">Un facet facoltativo, `Nullable`, è definito anche tramite un attributo XML.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="fd8ff-128">È possibile che una delle proprietà illustrate nel diagramma sia una proprietà di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="fd8ff-129">La proprietà `Address` sul tipo di entità `Publisher`, ad esempio, potrebbe essere una proprietà di tipo complesso costituita da diverse proprietà scalari, quali `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="fd8ff-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="fd8ff-130">La rappresentazione CSDL di tale tipo complesso sarà come segue:</span><span class="sxs-lookup"><span data-stu-id="fd8ff-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="fd8ff-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd8ff-131">See also</span></span>

- [<span data-ttu-id="fd8ff-132">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fd8ff-132">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="fd8ff-133">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="fd8ff-133">Entity Data Model</span></span>](entity-data-model.md)
