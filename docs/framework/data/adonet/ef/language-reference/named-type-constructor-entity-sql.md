---
title: Costruttore di tipo denominato (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f40adce1a9e031ed0b7cd5d03d9c63db255aa610
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319567"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="f162e-102">Costruttore di tipo denominato (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f162e-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="f162e-103">Utilizzato per creare istanze di tipi nominali del modello concettuale, ad esempio i tipi di entità o i tipi complessi.</span><span class="sxs-lookup"><span data-stu-id="f162e-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f162e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f162e-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="f162e-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="f162e-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="f162e-106">Valore che rappresenta un identificatore semplice o delimitato.</span><span class="sxs-lookup"><span data-stu-id="f162e-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="f162e-107">Per ulteriori informazioni, vedere [identificatori](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="f162e-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="f162e-108">Attributi del tipo che si presuppone essere nello stesso ordine in cui appaiono nella dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="f162e-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f162e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f162e-109">Return Value</span></span>  
 <span data-ttu-id="f162e-110">Istanze di tipi di entità e di tipi complessi denominati.</span><span class="sxs-lookup"><span data-stu-id="f162e-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f162e-111">Note</span><span class="sxs-lookup"><span data-stu-id="f162e-111">Remarks</span></span>  
 <span data-ttu-id="f162e-112">Negli esempi seguenti viene illustrato come costruire i tipi nominali e complessi:</span><span class="sxs-lookup"><span data-stu-id="f162e-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="f162e-113">L'espressione seguente consente di creare un'istanza di un tipo `Person` :</span><span class="sxs-lookup"><span data-stu-id="f162e-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="f162e-114">L'espressione seguente consente di creare un'istanza di un tipo complesso:</span><span class="sxs-lookup"><span data-stu-id="f162e-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="f162e-115">L'espressione seguente consente di creare un'istanza di un tipo complesso annidato:</span><span class="sxs-lookup"><span data-stu-id="f162e-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="f162e-116">L'espressione seguente consente di creare un'istanza di un'entità con un tipo complesso annidato:</span><span class="sxs-lookup"><span data-stu-id="f162e-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="f162e-117">Nell'esempio seguente viene illustrato come inizializzare una proprietà di un tipo complesso impostandola su Null:`MyModel.ZipCode(‘98118’, null)`.</span><span class="sxs-lookup"><span data-stu-id="f162e-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="f162e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f162e-118">Example</span></span>  
 <span data-ttu-id="f162e-119">Nella query Entity SQL seguente viene usato il costruttore di tipi denominati per creare un'istanza di un tipo di modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="f162e-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="f162e-120">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f162e-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f162e-121">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f162e-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f162e-122">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="f162e-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f162e-123">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f162e-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="f162e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f162e-124">See also</span></span>

- [<span data-ttu-id="f162e-125">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="f162e-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="f162e-126">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f162e-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
