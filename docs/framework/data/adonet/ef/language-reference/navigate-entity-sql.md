---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319548"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="f6f4f-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f6f4f-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="f6f4f-103">Consente di eseguire la navigazione nella relazione stabilita tra le entità.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6f4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6f4f-104">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="f6f4f-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="f6f4f-105">Arguments</span></span>

<span data-ttu-id="f6f4f-106">`instance-expression` un'istanza di un'entità.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="f6f4f-107">`relationship-type` il nome del tipo della relazione, dal file di Conceptual Schema Definition Language (CSDL).</span><span class="sxs-lookup"><span data-stu-id="f6f4f-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="f6f4f-108">Il `relationship-type` è qualificato come \<namespace >. nome del tipo di \<relationship >.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="f6f4f-109">`to` la fine della relazione.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="f6f4f-110">`from` l'inizio della relazione.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="f6f4f-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f6f4f-111">Return Value</span></span>

<span data-ttu-id="f6f4f-112">Se la cardinalità dell'entità finale è 1, il valore restituito è `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="f6f4f-113">Se la cardinalità dell'entità finale è n, il valore restituito è `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6f4f-114">Note</span><span class="sxs-lookup"><span data-stu-id="f6f4f-114">Remarks</span></span>

<span data-ttu-id="f6f4f-115">Le relazioni sono costrutti di prima classe nel Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="f6f4f-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="f6f4f-116">È possibile stabilire relazioni tra due o più tipi di entità e navigare nella relazione da un'entità finale all'altra.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="f6f4f-117">I parametri`from` e `to` sono condizionatamente facoltativi in assenza di ambiguità nella risoluzione dei nomi all'interno della relazione.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="f6f4f-118">NAVIGATE è valido nello spazio O e C.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="f6f4f-119">Il formato generale di un costrutto di navigazione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f6f4f-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="f6f4f-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="f6f4f-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="f6f4f-121">Esempio:</span><span class="sxs-lookup"><span data-stu-id="f6f4f-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="f6f4f-122">Dove OrderCustomer è l'oggetto `relationship`, mentre Customer e Order rappresentano l'oggetto `to-end` (Customer) e l'oggetto `from-end` (Order) della relazione.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="f6f4f-123">Se OrderCustomer è una relazione n:1, il tipo di risultato dell'espressione di navigazione è Ref \<Customer >.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="f6f4f-124">La forma più semplice di questa espressione è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f6f4f-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="f6f4f-125">Analogamente, in una query con il formato seguente, l'espressione di navigazione produrrebbe una raccolta < Ref \<Order > >.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="f6f4f-126">L'espressione dell'istanza deve essere un tipo di entità/riferimento.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="f6f4f-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6f4f-127">Example</span></span>

<span data-ttu-id="f6f4f-128">Nella query Entity SQL seguente viene usato l'operatore NAVIGATE per eseguire la navigazione nella relazione stabilita tra i tipi di entità Address e SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="f6f4f-129">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f6f4f-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f6f4f-130">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6f4f-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="f6f4f-131">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f6f4f-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="f6f4f-132">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f6f4f-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="f6f4f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f4f-133">See also</span></span>

- [<span data-ttu-id="f6f4f-134">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f6f4f-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f6f4f-135">Procedura: esplorare relazioni con l'operatore Navigate</span><span class="sxs-lookup"><span data-stu-id="f6f4f-135">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
