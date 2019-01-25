---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: ad54450b8f987da9a7a502d6561a58794a24b207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655179"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="c2d19-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c2d19-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="c2d19-103">Crea un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="c2d19-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="c2d19-104">Tutti i valori nel costruttore MULTISET devono essere di un tipo `T`compatibile.</span><span class="sxs-lookup"><span data-stu-id="c2d19-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="c2d19-105">Non sono consentiti costruttori multiset vuoti.</span><span class="sxs-lookup"><span data-stu-id="c2d19-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d19-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2d19-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="c2d19-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c2d19-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c2d19-108">Qualsiasi elenco valido di valori.</span><span class="sxs-lookup"><span data-stu-id="c2d19-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2d19-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c2d19-109">Return Value</span></span>  
 <span data-ttu-id="c2d19-110">Una raccolta di tipo MULTISET\<T >.</span><span class="sxs-lookup"><span data-stu-id="c2d19-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2d19-111">Note</span><span class="sxs-lookup"><span data-stu-id="c2d19-111">Remarks</span></span>  
 <span data-ttu-id="c2d19-112">In[!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili tre tipi di costruttori, ovvero costruttori di riga, costruttori di oggetti e costruttori di raccolte o multiset.</span><span class="sxs-lookup"><span data-stu-id="c2d19-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="c2d19-113">Per altre informazioni, vedere [tipi di costruzione](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c2d19-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="c2d19-114">Il costruttore multiset crea un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="c2d19-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="c2d19-115">Tutti i valori nel costruttore devono essere di un tipo compatibile.</span><span class="sxs-lookup"><span data-stu-id="c2d19-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="c2d19-116">L'espressione seguente consente ad esempio di creare un multiset di valori interi.</span><span class="sxs-lookup"><span data-stu-id="c2d19-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="c2d19-117">Valori letterali di multiset annidati sono supportati solo quando un multiset di wrapping contiene un solo elemento multiset, ad esempio, `{{1, 2, 3}}`.</span><span class="sxs-lookup"><span data-stu-id="c2d19-117">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="c2d19-118">Quando il multiset di wrapping contiene più elementi multiset, ad esempio `{{1, 2}, {3, 4}}`, non sono supportati valori letterali di multiset annidati.</span><span class="sxs-lookup"><span data-stu-id="c2d19-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d19-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2d19-119">Example</span></span>  
 <span data-ttu-id="c2d19-120">Nella query Entity SQL seguente viene usato l'operatore MULTISET per creare un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="c2d19-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="c2d19-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c2d19-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c2d19-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2d19-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c2d19-123">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c2d19-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c2d19-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c2d19-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="c2d19-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2d19-125">See also</span></span>
- [<span data-ttu-id="c2d19-126">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="c2d19-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="c2d19-127">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c2d19-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
