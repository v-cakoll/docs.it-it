---
title: Definizioni dei tipi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 2e068db0ce202c26cad36c8ed7adf0acdfb8e363
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096023"
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="5c0fb-102">Definizioni dei tipi (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5c0fb-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="5c0fb-103">Una definizione del tipo viene usata nell'istruzione per la dichiarazione di una funzione inline [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0fb-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c0fb-104">Note</span><span class="sxs-lookup"><span data-stu-id="5c0fb-104">Remarks</span></span>  
 <span data-ttu-id="5c0fb-105">L'istruzione di dichiarazione per una funzione inline è costituito il [funzione](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) seguita da un identificatore che rappresenta il nome della funzione (ad esempio, "MyAvg") seguito da un elenco di definizioni di parametro in parentesi (per la parola chiave esempio, "dues Collection.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="5c0fb-106">L'elenco di definizioni dei parametri è costituito da zero o più definizioni di parametri.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="5c0fb-107">Ogni definizione di parametro consiste di un identificatore (il nome del parametro alla funzione, ad esempio, "dues") seguito da una definizione del tipo (ad esempio, "Collection(Decimal)").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="5c0fb-108">Le definizioni del tipo possono essere:</span><span class="sxs-lookup"><span data-stu-id="5c0fb-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="5c0fb-109">Il tipo dell'identificatore (ad esempio, "Int32" o "AdventureWorks.Order").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="5c0fb-110">La parola chiave `COLLECTION` seguita da un'altra definizione del tipo tra parentesi (ad esempio "Collection(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="5c0fb-111">La parola chiave ROW seguita da un elenco di definizioni di proprietà tra parentesi (ad esempio "Row(x AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="5c0fb-112">Le definizioni di proprietà hanno un formato, ad esempio "`identifier type_definition`, `identifier type_definition`,...".</span><span class="sxs-lookup"><span data-stu-id="5c0fb-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="5c0fb-113">La parola chiave REF seguita dal tipo dell'identificatore tra parentesi (ad esempio "Ref(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="5c0fb-114">L'operatore della definizione del tipo Ref richiede un tipo di entità come argomento.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="5c0fb-115">Non è possibile specificare un tipo primitivo come argomento.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="5c0fb-116">È inoltre possibile annidare definizioni del tipo (ad esempio "Collection(Row(x Ref(AdventureWorks.Order)))").</span><span class="sxs-lookup"><span data-stu-id="5c0fb-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="5c0fb-117">Le opzioni di definizione del tipo sono:</span><span class="sxs-lookup"><span data-stu-id="5c0fb-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="5c0fb-118">`IdentifierName supported_type`, o</span><span class="sxs-lookup"><span data-stu-id="5c0fb-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="5c0fb-119">`IdentifierName` COLLECTION(`type_definition`) o</span><span class="sxs-lookup"><span data-stu-id="5c0fb-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="5c0fb-120">`IdentifierName` ROW(`property_definition`) o</span><span class="sxs-lookup"><span data-stu-id="5c0fb-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="5c0fb-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="5c0fb-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="5c0fb-122">L'opzione di definizione delle proprietà è `IdentifierName type_definition`.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="5c0fb-123">I tipi supportati sono qualsiasi tipo nello spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="5c0fb-124">Questi includono sia i tipi primitivi che i tipi di entità.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="5c0fb-125">Tipi di entità supportati si riferiscono solo a tipi di entità nello spazio dei nomi corrente.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="5c0fb-126">Non includono i tipi primitivi.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5c0fb-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="5c0fb-127">Examples</span></span>  
 <span data-ttu-id="5c0fb-128">Di seguito è riportato un esempio di definizione del tipo semplice.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="5c0fb-129">Di seguito è riportato un esempio di definizione del tipo COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="5c0fb-130">Di seguito è riportato un esempio di definizione del tipo ROW.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="5c0fb-131">Di seguito è riportato un esempio di definizione del tipo REF.</span><span class="sxs-lookup"><span data-stu-id="5c0fb-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c0fb-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c0fb-132">See also</span></span>

- [<span data-ttu-id="5c0fb-133">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5c0fb-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="5c0fb-134">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5c0fb-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
