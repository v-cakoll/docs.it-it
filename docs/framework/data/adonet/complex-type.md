---
title: tipo complesso
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: fac25ace69938e1245200e10285f4460ac216780
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948722"
---
# <a name="complex-type"></a><span data-ttu-id="14921-102">tipo complesso</span><span class="sxs-lookup"><span data-stu-id="14921-102">complex type</span></span>
<span data-ttu-id="14921-103">Un *tipo complesso* è un modello per la definizione di proprietà ricche e strutturate sui [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) o su altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="14921-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="14921-104">Ogni modello contiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="14921-104">Each template contains the following:</span></span>  
  
- <span data-ttu-id="14921-105">Un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="14921-105">A unique name.</span></span> <span data-ttu-id="14921-106">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="14921-106">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="14921-107">Il nome di un tipo complesso non può coincidere con il nome di un tipo di entità all'interno dello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="14921-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
- <span data-ttu-id="14921-108">Dati sotto forma di una o più [Proprietà](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="14921-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="14921-109">(Facoltative)</span><span class="sxs-lookup"><span data-stu-id="14921-109">(Optional.)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="14921-110">Una proprietà di un tipo complesso può essere un altro tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="14921-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="14921-111">Un tipo complesso è analogo a un tipo di entità in cui un tipo complesso può contenere un payload di dati sotto forma di proprietà di tipo primitivo o di altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="14921-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="14921-112">Tuttavia esistono alcune differenze importanti tra i tipi complessi e i tipi di entità:</span><span class="sxs-lookup"><span data-stu-id="14921-112">However, there are some key differences between complex types and entity types:</span></span>  
  
- <span data-ttu-id="14921-113">I tipi complessi non dispongono di identità e pertanto non possono esistere indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="14921-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="14921-114">I tipi complessi possono esistere solo come proprietà in tipi di entità o altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="14921-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
- <span data-ttu-id="14921-115">I tipi complessi non possono partecipare alle [associazioni](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="14921-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="14921-116">Nessuna entità finale di un'associazione può essere un tipo complesso e pertanto non è possibile definire [proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) su tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="14921-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14921-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="14921-117">Example</span></span>  
 <span data-ttu-id="14921-118">Il [Entity Framework ADO.NET](../../../../docs/framework/data/adonet/ef/index.md) utilizza un linguaggio specifico di dominio (DSL) denominato Conceptual Schema Definition Language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="14921-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="14921-119">Nel linguaggio CSDL seguente viene definito un tipo complesso, Address, con le proprietà di tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="14921-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="14921-120">Per definire il tipo complesso `Address` (sopra) come proprietà su un tipo di entità, è necessario dichiarare il tipo di proprietà nella definizione del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="14921-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="14921-121">Nel linguaggio CSDL seguente viene dichiarata la proprietà `Address` come un tipo complesso di un tipo di entità (Publisher):</span><span class="sxs-lookup"><span data-stu-id="14921-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="14921-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14921-122">See also</span></span>

- [<span data-ttu-id="14921-123">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="14921-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="14921-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="14921-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
