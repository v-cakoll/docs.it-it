---
title: Sistema di tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: f99d63bd526981c4a9f079c25851dc9bbd89cf7c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738470"
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="a04fe-102">Sistema di tipi (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a04fe-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a04fe-103">supporta diversi tipi:</span><span class="sxs-lookup"><span data-stu-id="a04fe-103">supports a number of types:</span></span>  
  
- <span data-ttu-id="a04fe-104">Tipi primitivi (semplici), come `Int32` e `String.`.</span><span class="sxs-lookup"><span data-stu-id="a04fe-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
- <span data-ttu-id="a04fe-105">Tipi nominali definiti nello schema, ad esempio <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> e <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="a04fe-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
- <span data-ttu-id="a04fe-106">Tipi anonimi non definiti esplicitamente nello schema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> e <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="a04fe-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="a04fe-107">In questa sezione vengono illustrati i tipi anonimi che non sono definiti in modo esplicito nello schema, ma sono supportati da Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="a04fe-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by Entity SQL.</span></span> <span data-ttu-id="a04fe-108">Per informazioni sui tipi primitivi e nominali, vedere [tipi di modelli concettuali (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span><span class="sxs-lookup"><span data-stu-id="a04fe-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="a04fe-109">Righe</span><span class="sxs-lookup"><span data-stu-id="a04fe-109">Rows</span></span>  
 <span data-ttu-id="a04fe-110">La struttura di una riga dipende dalla sequenza di membri tipizzati e denominati di cui è composta la riga stessa.</span><span class="sxs-lookup"><span data-stu-id="a04fe-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="a04fe-111">Un tipo di riga non dispone dell'identità e non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="a04fe-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="a04fe-112">Le istanze dello stesso tipo di riga sono equivalenti se i membri sono rispettivamente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a04fe-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="a04fe-113">Le righe non hanno alcun comportamento al di là dell'equivalenza strutturale e non dispongono di equivalenti in Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a04fe-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="a04fe-114">Le query possono produrre strutture contenenti righe o raccolte di righe.</span><span class="sxs-lookup"><span data-stu-id="a04fe-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="a04fe-115">L'associazione API tra le query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e il linguaggio host definisce la realizzazione delle righe nella query che ha prodotto il risultato.</span><span class="sxs-lookup"><span data-stu-id="a04fe-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="a04fe-116">Per informazioni su come creare un'istanza di riga, vedere [costruzione di tipi](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a04fe-116">For information on how to construct a row instance, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="a04fe-117">Raccolte</span><span class="sxs-lookup"><span data-stu-id="a04fe-117">Collections</span></span>  
 <span data-ttu-id="a04fe-118">I tipi di raccolta rappresentano zero o più istanze di altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="a04fe-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="a04fe-119">Per informazioni su come costruire la raccolta, vedere [costruzione di tipi](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a04fe-119">For information on how to construct collection, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="a04fe-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a04fe-120">References</span></span>  
 <span data-ttu-id="a04fe-121">Un riferimento è un puntatore logico a un'entità specifica in un set di entità specifico.</span><span class="sxs-lookup"><span data-stu-id="a04fe-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a04fe-122">supporta gli operatori seguenti per costruire o annullare i riferimenti, nonché eseguire la navigazione al loro interno:</span><span class="sxs-lookup"><span data-stu-id="a04fe-122">supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
- [<span data-ttu-id="a04fe-123">REF</span><span class="sxs-lookup"><span data-stu-id="a04fe-123">REF</span></span>](ref-entity-sql.md)  
  
- [<span data-ttu-id="a04fe-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="a04fe-124">CREATEREF</span></span>](createref-entity-sql.md)  
  
- [<span data-ttu-id="a04fe-125">KEY</span><span class="sxs-lookup"><span data-stu-id="a04fe-125">KEY</span></span>](key-entity-sql.md)  
  
- [<span data-ttu-id="a04fe-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="a04fe-126">DEREF</span></span>](deref-entity-sql.md)  
  
 <span data-ttu-id="a04fe-127">È possibile navigare da un riferimento all'altro tramite l'operatore (punto) di accesso ai membri (`.`).</span><span class="sxs-lookup"><span data-stu-id="a04fe-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="a04fe-128">Nel frammento seguente viene estratta la proprietà Id (di Order) spostandosi nella proprietà r (riferimento).</span><span class="sxs-lookup"><span data-stu-id="a04fe-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```sql  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="a04fe-129">Se il valore di riferimento è null o la destinazione del riferimento non esiste, il risultato è null.</span><span class="sxs-lookup"><span data-stu-id="a04fe-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04fe-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a04fe-130">See also</span></span>

- [<span data-ttu-id="a04fe-131">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a04fe-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="a04fe-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a04fe-132">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a04fe-133">CAST</span><span class="sxs-lookup"><span data-stu-id="a04fe-133">CAST</span></span>](cast-entity-sql.md)
- [<span data-ttu-id="a04fe-134">Specifiche CSDL, SSDL e MSL</span><span class="sxs-lookup"><span data-stu-id="a04fe-134">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
