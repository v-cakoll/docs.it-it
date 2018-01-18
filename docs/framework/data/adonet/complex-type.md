---
title: tipo complesso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6a7fbdace6403d2f1037beff8fe28d7c934d3174
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="complex-type"></a><span data-ttu-id="e2372-102">tipo complesso</span><span class="sxs-lookup"><span data-stu-id="e2372-102">complex type</span></span>
<span data-ttu-id="e2372-103">Oggetto *tipo complesso* è un modello per la definizione di proprietà dettagliate e strutturate sui [tipi di entità](../../../../docs/framework/data/adonet/entity-type.md) o su altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="e2372-103">A *complex type* is a template for defining rich, structured properties on [entity types](../../../../docs/framework/data/adonet/entity-type.md) or on other complex types.</span></span> <span data-ttu-id="e2372-104">Ogni modello contiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e2372-104">Each template contains the following:</span></span>  
  
-   <span data-ttu-id="e2372-105">Un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="e2372-105">A unique name.</span></span> <span data-ttu-id="e2372-106">(obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="e2372-106">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2372-107">Il nome di un tipo complesso non può coincidere con il nome di un tipo di entità all'interno dello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e2372-107">The name of a complex type cannot be the same as an entity type name within the same namespace.</span></span>  
  
-   <span data-ttu-id="e2372-108">Dati sotto forma di uno o più [proprietà](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="e2372-108">Data in the form of one or more [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="e2372-109">(Facoltative)</span><span class="sxs-lookup"><span data-stu-id="e2372-109">(Optional.)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2372-110">Una proprietà di un tipo complesso può essere un altro tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="e2372-110">A property of a complex type can be another complex type.</span></span>  
  
 <span data-ttu-id="e2372-111">Un tipo complesso è analogo a un tipo di entità in cui un tipo complesso può contenere un payload di dati sotto forma di proprietà di tipo primitivo o di altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="e2372-111">A complex type is similar to an entity type in that a complex type can carry a data payload in the form of primitive type properties or other complex types.</span></span> <span data-ttu-id="e2372-112">Tuttavia esistono alcune differenze importanti tra i tipi complessi e i tipi di entità:</span><span class="sxs-lookup"><span data-stu-id="e2372-112">However, there are some key differences between complex types and entity types:</span></span>  
  
-   <span data-ttu-id="e2372-113">I tipi complessi non dispongono di identità e pertanto non possono esistere indipendentemente.</span><span class="sxs-lookup"><span data-stu-id="e2372-113">Complex types do not have identities and therefore cannot exist independently.</span></span> <span data-ttu-id="e2372-114">I tipi complessi possono esistere solo come proprietà in tipi di entità o altri tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="e2372-114">Complex types can only exist as properties on entity types or other complex types.</span></span>  
  
-   <span data-ttu-id="e2372-115">Tipi complessi non possono partecipare [associazioni](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="e2372-115">Complex types cannot participate in [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="e2372-116">Le entità finali di un'associazione possono essere un tipo complesso e pertanto [le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) non può essere definito per i tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="e2372-116">Neither end of an association can be a complex type, and therefore [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) cannot be defined on complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2372-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2372-117">Example</span></span>  
 <span data-ttu-id="e2372-118">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="e2372-118">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e2372-119">Nel linguaggio CSDL seguente viene definito un tipo complesso, Address, con le proprietà di tipo primitivo `StreetAddress`, `City`, `StateOrProvince`, `Country` e `PostalCode`.</span><span class="sxs-lookup"><span data-stu-id="e2372-119">The following CSDL defines a complex type, Address, with the primitive type properties `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 <span data-ttu-id="e2372-120">Per definire il tipo complesso `Address` (sopra) come proprietà su un tipo di entità, è necessario dichiarare il tipo di proprietà nella definizione del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="e2372-120">To define the complex type `Address` (above) as a property on an entity type, you must declare the property type in the entity type definition.</span></span> <span data-ttu-id="e2372-121">Nel linguaggio CSDL seguente viene dichiarata la proprietà `Address` come un tipo complesso di un tipo di entità (Publisher):</span><span class="sxs-lookup"><span data-stu-id="e2372-121">The following CSDL declares the `Address` property as a complex type on an entity type (Publisher):</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a><span data-ttu-id="e2372-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2372-122">See Also</span></span>  
 [<span data-ttu-id="e2372-123">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e2372-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="e2372-124">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="e2372-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
