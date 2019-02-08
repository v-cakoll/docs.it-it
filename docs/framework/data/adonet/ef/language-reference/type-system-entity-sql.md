---
title: Sistema di tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: a2748407703b90c60d3082b0e6c0b6aa2d3fb365
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904687"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="3c4b4-102">Sistema di tipi (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3c4b4-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3c4b4-103">supporta diversi tipi:</span><span class="sxs-lookup"><span data-stu-id="3c4b4-103">supports a number of types:</span></span>  
  
-   <span data-ttu-id="3c4b4-104">Tipi primitivi (semplici), come `Int32` e `String.`.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
-   <span data-ttu-id="3c4b4-105">Tipi nominali definiti nello schema, ad esempio <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> e <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
-   <span data-ttu-id="3c4b4-106">Tipi anonimi non definiti esplicitamente nello schema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> e <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="3c4b4-107">In questa sezione vengono descritti i tipi anonimi non definiti in modo esplicito nello schema ma supportati da Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="3c4b4-108">Per informazioni sui tipi primitivi e nominali, vedere [tipi di modello concettuale (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="3c4b4-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="3c4b4-109">Righe</span><span class="sxs-lookup"><span data-stu-id="3c4b4-109">Rows</span></span>  
 <span data-ttu-id="3c4b4-110">La struttura di una riga dipende dalla sequenza di membri tipizzati e denominati di cui è composta la riga stessa.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="3c4b4-111">Un tipo di riga non dispone dell'identità e non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="3c4b4-112">Le istanze dello stesso tipo di riga sono equivalenti se i membri sono rispettivamente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="3c4b4-113">Le righe non hanno alcun comportamento al di là dell'equivalenza strutturale e non dispongono di equivalenti in Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="3c4b4-114">Le query possono produrre strutture contenenti righe o raccolte di righe.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="3c4b4-115">L'associazione API tra le query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e il linguaggio host definisce la realizzazione delle righe nella query che ha prodotto il risultato.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="3c4b4-116">Per informazioni su come costruire un'istanza di riga, vedere [tipi di costruzione](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3c4b4-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="3c4b4-117">Raccolte</span><span class="sxs-lookup"><span data-stu-id="3c4b4-117">Collections</span></span>  
 <span data-ttu-id="3c4b4-118">I tipi di raccolta rappresentano zero o più istanze di altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="3c4b4-119">Per informazioni su come costruire una raccolta, vedere [tipi di costruzione](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3c4b4-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="3c4b4-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3c4b4-120">References</span></span>  
 <span data-ttu-id="3c4b4-121">Un riferimento è un puntatore logico a un'entità specifica in un set di entità specifico.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="3c4b4-122">supporta gli operatori seguenti per costruire o annullare i riferimenti, nonché eseguire la navigazione al loro interno:</span><span class="sxs-lookup"><span data-stu-id="3c4b4-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
-   [<span data-ttu-id="3c4b4-123">REF</span><span class="sxs-lookup"><span data-stu-id="3c4b4-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [<span data-ttu-id="3c4b4-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="3c4b4-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [<span data-ttu-id="3c4b4-125">KEY</span><span class="sxs-lookup"><span data-stu-id="3c4b4-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [<span data-ttu-id="3c4b4-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="3c4b4-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="3c4b4-127">È possibile navigare da un riferimento all'altro tramite l'operatore (punto) di accesso ai membri (`.`).</span><span class="sxs-lookup"><span data-stu-id="3c4b4-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="3c4b4-128">Nel frammento seguente viene estratta la proprietà Id (di Order) spostandosi nella proprietà r (riferimento).</span><span class="sxs-lookup"><span data-stu-id="3c4b4-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="3c4b4-129">Se il valore di riferimento è null o la destinazione del riferimento non esiste, il risultato è null.</span><span class="sxs-lookup"><span data-stu-id="3c4b4-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4b4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c4b4-130">See also</span></span>
- [<span data-ttu-id="3c4b4-131">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3c4b4-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="3c4b4-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3c4b4-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="3c4b4-133">CAST</span><span class="sxs-lookup"><span data-stu-id="3c4b4-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)
- [<span data-ttu-id="3c4b4-134">Specifiche CSDL, SSDL e MSL</span><span class="sxs-lookup"><span data-stu-id="3c4b4-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
