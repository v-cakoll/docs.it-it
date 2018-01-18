---
title: MULTISET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6389051ae1244a2a38699704c67217d9807fe7e4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="2bd36-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2bd36-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="2bd36-103">Crea un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="2bd36-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="2bd36-104">Tutti i valori nel costruttore MULTISET devono essere di un tipo `T`compatibile.</span><span class="sxs-lookup"><span data-stu-id="2bd36-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="2bd36-105">Non sono consentiti costruttori multiset vuoti.</span><span class="sxs-lookup"><span data-stu-id="2bd36-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bd36-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bd36-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="2bd36-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2bd36-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2bd36-108">Qualsiasi elenco valido di valori.</span><span class="sxs-lookup"><span data-stu-id="2bd36-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bd36-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2bd36-109">Return Value</span></span>  
 <span data-ttu-id="2bd36-110">Una raccolta di tipo MULTISET\<T >.</span><span class="sxs-lookup"><span data-stu-id="2bd36-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bd36-111">Note</span><span class="sxs-lookup"><span data-stu-id="2bd36-111">Remarks</span></span>  
 <span data-ttu-id="2bd36-112">In[!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili tre tipi di costruttori, ovvero costruttori di riga, costruttori di oggetti e costruttori di raccolte o multiset.</span><span class="sxs-lookup"><span data-stu-id="2bd36-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="2bd36-113">Per ulteriori informazioni, vedere [la costruzione di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="2bd36-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="2bd36-114">Il costruttore multiset crea un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="2bd36-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="2bd36-115">Tutti i valori nel costruttore devono essere di un tipo compatibile.</span><span class="sxs-lookup"><span data-stu-id="2bd36-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="2bd36-116">L'espressione seguente consente ad esempio di creare un multiset di valori interi.</span><span class="sxs-lookup"><span data-stu-id="2bd36-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="2bd36-117">I valori letterali di multiset annidati sono supportati solo quando un multiset di wrapping contiene un solo elemento multiset, ad esempio `{{1, 2, 3}}`.</span><span class="sxs-lookup"><span data-stu-id="2bd36-117">Nested multiset literals are only supported when a wrapping mutiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="2bd36-118">Quando il multiset di wrapping contiene più elementi multiset, ad esempio `{{1, 2}, {3, 4}}`, non sono supportati valori letterali di multiset annidati.</span><span class="sxs-lookup"><span data-stu-id="2bd36-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bd36-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2bd36-119">Example</span></span>  
 <span data-ttu-id="2bd36-120">Nella query Entity SQL seguente viene usato l'operatore MULTISET per creare un'istanza di un multiset da un elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="2bd36-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="2bd36-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="2bd36-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2bd36-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2bd36-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2bd36-123">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2bd36-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2bd36-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2bd36-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="2bd36-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bd36-125">See Also</span></span>  
 [<span data-ttu-id="2bd36-126">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="2bd36-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="2bd36-127">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2bd36-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
