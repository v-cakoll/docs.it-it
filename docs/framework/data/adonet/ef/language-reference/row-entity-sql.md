---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: eb5062399eec9d8453d8922e05698ca9124d94d7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765607"
---
# <a name="row-entity-sql"></a><span data-ttu-id="62f90-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="62f90-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="62f90-103">Consente di costruire record anonimi strutturalmente tipizzati da uno o più valori.</span><span class="sxs-lookup"><span data-stu-id="62f90-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62f90-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="62f90-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="62f90-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="62f90-106">Qualsiasi espressione di query valida che restituisce un valore da costruire in un tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="62f90-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="62f90-107">Specifica un alias per il valore specificato in un tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="62f90-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="62f90-108">Se non viene fornito un alias, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generare un alias usando le regole di generazione di alias [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62f90-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62f90-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="62f90-109">Return Value</span></span>  
 <span data-ttu-id="62f90-110">Tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="62f90-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62f90-111">Note</span><span class="sxs-lookup"><span data-stu-id="62f90-111">Remarks</span></span>  
 <span data-ttu-id="62f90-112">Si usano costruttori ROW in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per costruire record anonimi strutturalmente tipizzati da uno o più valori.</span><span class="sxs-lookup"><span data-stu-id="62f90-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="62f90-113">Il tipo di risultato di un costruttore ROW è un tipo di riga i cui tipi di campo corrispondono ai tipi dei valori usati per costruire la riga.</span><span class="sxs-lookup"><span data-stu-id="62f90-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="62f90-114">L'espressione seguente consente ad esempio di costruire un valore di tipo `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="62f90-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="62f90-115">Se non si fornisce un alias per un'espressione in un costruttore di riga, in Entity Framework viene eseguito un tentativo di generarne uno.</span><span class="sxs-lookup"><span data-stu-id="62f90-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="62f90-116">Per altre informazioni, vedere la sezione "Regole relative all'utilizzo degli alias" dell'argomento [Identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="62f90-116">For more information, see the "Aliasing Rules" section of the [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="62f90-117">Le regole seguenti riguardano l'uso di alias nelle espressioni in un costruttore di riga:</span><span class="sxs-lookup"><span data-stu-id="62f90-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="62f90-118">Le espressioni in un costruttore ROW non possono fare riferimento ad altri alias nello stesso costruttore.</span><span class="sxs-lookup"><span data-stu-id="62f90-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="62f90-119">Due espressioni nello stesso costruttore di riga non possono avere lo stesso alias.</span><span class="sxs-lookup"><span data-stu-id="62f90-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="62f90-120">Per ulteriori informazioni sui costruttori di query, vedere [la costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="62f90-120">For more information about query constructors, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62f90-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="62f90-121">Example</span></span>  
 <span data-ttu-id="62f90-122">Nella query Entity SQL seguente viene usato l'operatore ROW per costruire record anonimi strutturalmente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="62f90-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="62f90-123">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="62f90-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="62f90-124">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62f90-124">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="62f90-125">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="62f90-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="62f90-126">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="62f90-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="62f90-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f90-127">See Also</span></span>  
 [<span data-ttu-id="62f90-128">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="62f90-128">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="62f90-129">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62f90-129">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="62f90-130">Definizioni di tipo</span><span class="sxs-lookup"><span data-stu-id="62f90-130">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
