---
title: Sistema di tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: 3470ad17ae16e57edbbef13f30186b7e58fd0d2b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="3e838-102">Sistema di tipi (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3e838-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="3e838-103"> supporta una serie di tipi:</span><span class="sxs-lookup"><span data-stu-id="3e838-103"> supports a number of types:</span></span>  
  
-   <span data-ttu-id="3e838-104">Tipi primitivi (semplici), come `Int32` e `String.`.</span><span class="sxs-lookup"><span data-stu-id="3e838-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
-   <span data-ttu-id="3e838-105">Tipi nominali definiti nello schema, ad esempio <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> e <xref:System.Data.Metadata.Edm.RelationshipType>.</span><span class="sxs-lookup"><span data-stu-id="3e838-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
-   <span data-ttu-id="3e838-106">Tipi anonimi non definiti esplicitamente nello schema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> e <xref:System.Data.Metadata.Edm.RefType>.</span><span class="sxs-lookup"><span data-stu-id="3e838-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="3e838-107">Contenuto della sezione vengono descritti i tipi anonimi non definiti in modo esplicito nello schema ma supportati da [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e838-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="3e838-108">Per informazioni sui tipi primitivi e nominale, vedere [tipi di modello concettuale (CSDL)](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4).</span><span class="sxs-lookup"><span data-stu-id="3e838-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="3e838-109">Righe</span><span class="sxs-lookup"><span data-stu-id="3e838-109">Rows</span></span>  
 <span data-ttu-id="3e838-110">La struttura di una riga dipende dalla sequenza di membri tipizzati e denominati di cui è composta la riga stessa.</span><span class="sxs-lookup"><span data-stu-id="3e838-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="3e838-111">Un tipo di riga non dispone dell'identità e non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="3e838-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="3e838-112">Le istanze dello stesso tipo di riga sono equivalenti se i membri sono rispettivamente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="3e838-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="3e838-113">Le righe non hanno alcun comportamento al di là dell'equivalenza strutturale e non dispongono di equivalenti in Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3e838-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="3e838-114">Le query possono produrre strutture contenenti righe o raccolte di righe.</span><span class="sxs-lookup"><span data-stu-id="3e838-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="3e838-115">L'associazione API tra le query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e il linguaggio host definisce la realizzazione delle righe nella query che ha prodotto il risultato.</span><span class="sxs-lookup"><span data-stu-id="3e838-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="3e838-116">Per informazioni su come costruire un'istanza di riga, vedere [la costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3e838-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="3e838-117">Raccolte</span><span class="sxs-lookup"><span data-stu-id="3e838-117">Collections</span></span>  
 <span data-ttu-id="3e838-118">I tipi di raccolta rappresentano zero o più istanze di altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="3e838-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="3e838-119">Per informazioni su come creare una raccolta, vedere [la costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3e838-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="3e838-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3e838-120">References</span></span>  
 <span data-ttu-id="3e838-121">Un riferimento è un puntatore logico a un'entità specifica in un set di entità specifico.</span><span class="sxs-lookup"><span data-stu-id="3e838-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="3e838-122"> supporta gli operatori seguenti per costruire o annullare i riferimenti, nonché eseguire la navigazione al loro interno:</span><span class="sxs-lookup"><span data-stu-id="3e838-122"> supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
-   [<span data-ttu-id="3e838-123">REF</span><span class="sxs-lookup"><span data-stu-id="3e838-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [<span data-ttu-id="3e838-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="3e838-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [<span data-ttu-id="3e838-125">KEY</span><span class="sxs-lookup"><span data-stu-id="3e838-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [<span data-ttu-id="3e838-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="3e838-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="3e838-127">È possibile navigare da un riferimento all'altro tramite l'operatore (punto) di accesso ai membri (`.`).</span><span class="sxs-lookup"><span data-stu-id="3e838-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="3e838-128">Nel frammento seguente viene estratta la proprietà Id (di Order) spostandosi nella proprietà r (riferimento).</span><span class="sxs-lookup"><span data-stu-id="3e838-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="3e838-129">Se il valore di riferimento è null o la destinazione del riferimento non esiste, il risultato è null.</span><span class="sxs-lookup"><span data-stu-id="3e838-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e838-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e838-130">See Also</span></span>  
 [<span data-ttu-id="3e838-131">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3e838-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="3e838-132">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3e838-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="3e838-133">CAST</span><span class="sxs-lookup"><span data-stu-id="3e838-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)  
 [<span data-ttu-id="3e838-134">Specifiche CSDL, SSDL e MSL</span><span class="sxs-lookup"><span data-stu-id="3e838-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
