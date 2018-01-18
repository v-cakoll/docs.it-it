---
title: facet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 23346fe2095cea2b3f0d705c7d6d8914c35c06f7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="facet"></a><span data-ttu-id="43548-102">facet</span><span class="sxs-lookup"><span data-stu-id="43548-102">facet</span></span>
<span data-ttu-id="43548-103">Oggetto *facet* viene utilizzato per aggiungere dettagli a una definizione di proprietà di tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="43548-103">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="43548-104">Oggetto [proprietà](../../../../docs/framework/data/adonet/property.md) definizione contiene informazioni sul tipo di proprietà, ma spesso sono necessari ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="43548-104">A [property](../../../../docs/framework/data/adonet/property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="43548-105">Un tipo di entità in un modello concettuale, ad esempio, potrebbe disporre di una proprietà di tipo `String` il cui valore non può essere impostato su null.</span><span class="sxs-lookup"><span data-stu-id="43548-105">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="43548-106">I facet consentono di specificare questo livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="43548-106">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="43548-107">Nella tabella seguente vengono descritti i facet supportati in EDM.</span><span class="sxs-lookup"><span data-stu-id="43548-107">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43548-108">I valori e i comportamenti esatti dei facet sono determinati dall'ambiente di runtime che usa un'implementazione EDM.</span><span class="sxs-lookup"><span data-stu-id="43548-108">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="43548-109">Facet</span><span class="sxs-lookup"><span data-stu-id="43548-109">Facet</span></span>|<span data-ttu-id="43548-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43548-110">Description</span></span>|<span data-ttu-id="43548-111">Si applica a</span><span class="sxs-lookup"><span data-stu-id="43548-111">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="43548-112">Specifica la sequenza di ordinamento da usare quando si eseguono operazioni di confronto e di ordinamento su valori della proprietà.</span><span class="sxs-lookup"><span data-stu-id="43548-112">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="43548-113">Indica che il valore della proprietà deve essere usato per le verifiche della concorrenza ottimistica.</span><span class="sxs-lookup"><span data-stu-id="43548-113">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="43548-114">Tutte le proprietà di tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="43548-114">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="43548-115">Specifica il valore predefinito della proprietà se durante la creazione di istanze non viene fornito alcun valore.</span><span class="sxs-lookup"><span data-stu-id="43548-115">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="43548-116">Tutte le proprietà di tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="43548-116">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="43548-117">Specifica se la lunghezza del valore della proprietà può variare.</span><span class="sxs-lookup"><span data-stu-id="43548-117">Specifies whether the length of the property value can vary.</span></span>|<span data-ttu-id="43548-118">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="43548-118">`Binary`, `String`</span></span>|  
|`MaxLength`|<span data-ttu-id="43548-119">Specifica la lunghezza massima del valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="43548-119">Specifies the maximum length of the property value.</span></span>|<span data-ttu-id="43548-120">`Binary`, `String`</span><span class="sxs-lookup"><span data-stu-id="43548-120">`Binary`, `String`</span></span>|  
|`Nullable`|<span data-ttu-id="43548-121">Specifica se la proprietà può avere un valore null.</span><span class="sxs-lookup"><span data-stu-id="43548-121">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="43548-122">Tutte le proprietà di tipo primitivo</span><span class="sxs-lookup"><span data-stu-id="43548-122">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="43548-123">Per le proprietà di tipo `Decimal`, specifica il numero di cifre che un valore della proprietà può avere.</span><span class="sxs-lookup"><span data-stu-id="43548-123">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="43548-124">Per le proprietà di tipo `Time`, `DateTime` e `DateTimeOffset`, specifica il numero di cifre per la parte frazionaria di secondi del valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="43548-124">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|<span data-ttu-id="43548-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="43548-125">`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="43548-126">Specifica il numero di cifre a destra del separatore decimale per il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="43548-126">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="43548-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="43548-127">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="43548-128">Viene indicato se il valore della proprietà viene archiviato come Unicode.</span><span class="sxs-lookup"><span data-stu-id="43548-128">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="43548-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="43548-129">Example</span></span>  
 <span data-ttu-id="43548-130">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL), chiamato linguaggio conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="43548-130">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="43548-131">Nel linguaggio CSDL seguente viene definito un tipo di entità `Book`.</span><span class="sxs-lookup"><span data-stu-id="43548-131">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="43548-132">Si noti che i facet vengono implementati come attributi XML.</span><span class="sxs-lookup"><span data-stu-id="43548-132">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="43548-133">I valori dei facet indicano che nessuna proprietà può essere impostata su null e che `Scale` e `Precision` della proprietà `Revision` sono entrambi impostati su 29.</span><span class="sxs-lookup"><span data-stu-id="43548-133">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="43548-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43548-134">See Also</span></span>  
 [<span data-ttu-id="43548-135">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="43548-135">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="43548-136">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="43548-136">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
