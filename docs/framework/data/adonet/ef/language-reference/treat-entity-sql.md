---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: e1382c4daa513477011a1d1c2132840dfae84de0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077342"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="51983-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="51983-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="51983-103">Consente di trattare un oggetto di un tipo di base particolare come oggetto del tipo derivato specificato.</span><span class="sxs-lookup"><span data-stu-id="51983-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51983-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51983-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="51983-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="51983-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="51983-106">Qualsiasi espressione di query valida che restituisce un'entità.</span><span class="sxs-lookup"><span data-stu-id="51983-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51983-107">Il tipo dell'espressione specificata deve essere un sottotipo del tipo di dati specificato oppure il tipo di dati deve essere un sottotipo del tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="51983-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="51983-108">Tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="51983-108">An entity type.</span></span> <span data-ttu-id="51983-109">Il tipo deve essere qualificato da uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="51983-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51983-110">L'espressione specificata deve essere un sottotipo del tipo di dati specificato oppure il tipo di dati deve essere un sottotipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="51983-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51983-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51983-111">Return Value</span></span>  
 <span data-ttu-id="51983-112">Valore del tipo di dati specificato.</span><span class="sxs-lookup"><span data-stu-id="51983-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51983-113">Note</span><span class="sxs-lookup"><span data-stu-id="51983-113">Remarks</span></span>  
 <span data-ttu-id="51983-114">TREAT viene usato per eseguire l'upcast tra classi correlate.</span><span class="sxs-lookup"><span data-stu-id="51983-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="51983-115">Se, ad esempio, `Employee` deriva da `Person` e p è di tipo `Person`, `TREAT(p AS NamespaceName.Employee)` consente di eseguire l'upcast di un'istanza generica di `Person` a `Employee`, ovvero consente di trattare p come `Employee`.</span><span class="sxs-lookup"><span data-stu-id="51983-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="51983-116">TREAT viene usato negli scenari di ereditarietà dove è possibile eseguire una query simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="51983-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="51983-117">Questa query consente di eseguire l'upcast delle entità `Person` al tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="51983-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="51983-118">Se il valore di p non è di tipo `Employee`, l'espressione restituisce il valore `null`.</span><span class="sxs-lookup"><span data-stu-id="51983-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51983-119">L'espressione specificata `Employee` deve essere un sottotipo del tipo di dati specificato `Person`, o il tipo di dati deve essere un sottotipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="51983-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="51983-120">In caso contrario, l'espressione comporterà la generazione di un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="51983-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="51983-121">Nella tabella seguente viene illustrato il comportamento di TREAT su alcuni modelli tipici e su alcuni modelli meno comuni.</span><span class="sxs-lookup"><span data-stu-id="51983-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="51983-122">Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:</span><span class="sxs-lookup"><span data-stu-id="51983-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="51983-123">Modello</span><span class="sxs-lookup"><span data-stu-id="51983-123">Pattern</span></span>|<span data-ttu-id="51983-124">Comportamento</span><span class="sxs-lookup"><span data-stu-id="51983-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="51983-125">Restituisce `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="51983-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="51983-126">Genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="51983-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="51983-127">Genera un'eccezione/</span><span class="sxs-lookup"><span data-stu-id="51983-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="51983-128">Restituisce `EntityType` o `null`.</span><span class="sxs-lookup"><span data-stu-id="51983-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="51983-129">Genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="51983-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="51983-130">Genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="51983-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="51983-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="51983-131">Example</span></span>  
 <span data-ttu-id="51983-132">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore TREAT per convertire un oggetto del tipo Course in una raccolta di oggetti del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="51983-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="51983-133">La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="51983-133">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="51983-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51983-134">See also</span></span>

- [<span data-ttu-id="51983-135">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="51983-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="51983-136">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="51983-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
