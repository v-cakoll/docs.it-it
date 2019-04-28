---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 993c07b824d30c89773c5cfea90c7c194c6b3869
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760415"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="66235-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="66235-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="66235-103">Consente di eseguire la navigazione nella relazione stabilita tra le entità.</span><span class="sxs-lookup"><span data-stu-id="66235-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="66235-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66235-104">Syntax</span></span>

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="66235-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="66235-105">Arguments</span></span>

<span data-ttu-id="66235-106">`instance-expression` Un'istanza di un'entità.</span><span class="sxs-lookup"><span data-stu-id="66235-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="66235-107">`relationship-type` Il nome del tipo della relazione, dal file conceptual schema definition language (CSDL).</span><span class="sxs-lookup"><span data-stu-id="66235-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="66235-108">Il `relationship-type` è qualificato come \<dello spazio dei nomi >.\< Nome tipo relazione >.</span><span class="sxs-lookup"><span data-stu-id="66235-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="66235-109">`to` Fine della relazione.</span><span class="sxs-lookup"><span data-stu-id="66235-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="66235-110">`from` Inizio della relazione.</span><span class="sxs-lookup"><span data-stu-id="66235-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="66235-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="66235-111">Return Value</span></span>

<span data-ttu-id="66235-112">Se la cardinalità dell'entità finale è 1, il valore restituito è `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="66235-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="66235-113">Se la cardinalità dell'entità finale è n, il valore restituito è `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="66235-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="66235-114">Note</span><span class="sxs-lookup"><span data-stu-id="66235-114">Remarks</span></span>

<span data-ttu-id="66235-115">Le relazioni sono costrutti di primaria importanza in [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span><span class="sxs-lookup"><span data-stu-id="66235-115">Relationships are first-class constructs in the [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM).</span></span> <span data-ttu-id="66235-116">È possibile stabilire relazioni tra due o più tipi di entità e navigare nella relazione da un'entità finale all'altra.</span><span class="sxs-lookup"><span data-stu-id="66235-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="66235-117">I parametri`from` e `to` sono condizionatamente facoltativi in assenza di ambiguità nella risoluzione dei nomi all'interno della relazione.</span><span class="sxs-lookup"><span data-stu-id="66235-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="66235-118">NAVIGATE è valido nello spazio O e C.</span><span class="sxs-lookup"><span data-stu-id="66235-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="66235-119">Il formato generale di un costrutto di navigazione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="66235-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="66235-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="66235-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="66235-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="66235-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="66235-122">Dove OrderCustomer è l'oggetto `relationship`, mentre Customer e Order rappresentano l'oggetto `to-end` (Customer) e l'oggetto `from-end` (Order) della relazione.</span><span class="sxs-lookup"><span data-stu-id="66235-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="66235-123">Se OrderCustomer è una relazione n:1, il tipo di risultato dell'espressione di navigazione è Ref\<cliente >.</span><span class="sxs-lookup"><span data-stu-id="66235-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="66235-124">La forma più semplice di questa espressione è la seguente:</span><span class="sxs-lookup"><span data-stu-id="66235-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="66235-125">Analogamente, in una query nel formato seguente, l'espressione di navigazione produrrebbe come risultato Collection < Ref\<ordine >>.</span><span class="sxs-lookup"><span data-stu-id="66235-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="66235-126">L'espressione dell'istanza deve essere un tipo di entità/riferimento.</span><span class="sxs-lookup"><span data-stu-id="66235-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="66235-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="66235-127">Example</span></span>

<span data-ttu-id="66235-128">Nella query Entity SQL seguente viene usato l'operatore NAVIGATE per eseguire la navigazione nella relazione stabilita tra i tipi di entità Address e SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="66235-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="66235-129">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="66235-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="66235-130">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66235-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="66235-131">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="66235-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="66235-132">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="66235-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a><span data-ttu-id="66235-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66235-133">See also</span></span>

- [<span data-ttu-id="66235-134">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="66235-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="66235-135">Procedura: Esplorare relazioni con l'operatore Navigate</span><span class="sxs-lookup"><span data-stu-id="66235-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
