---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: fd7f484733e7135d2d6c8094b6527d672a988088
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150298"
---
# <a name="function-entity-sql"></a><span data-ttu-id="0ce08-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0ce08-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="0ce08-103">Definisce una funzione nell'ambito di un comando di query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="0ce08-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce08-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ce08-104">Syntax</span></span>  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>
        [ ,...n ]  
  ]  
) AS ( function_expression )
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )
                | REF ( data_type )
                | ROW ( row_expression )
        }
```  
  
## <a name="arguments"></a><span data-ttu-id="0ce08-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0ce08-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="0ce08-106">Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="0ce08-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="0ce08-107">Nome di un parametro nella funzione.</span><span class="sxs-lookup"><span data-stu-id="0ce08-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="0ce08-108">Espressione Entity SQL valida che è la funzione.</span><span class="sxs-lookup"><span data-stu-id="0ce08-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="0ce08-109">Il comando nella funzione può agire sui parametri `parameter_name` passati alla funzione.</span><span class="sxs-lookup"><span data-stu-id="0ce08-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="0ce08-110">Nome di un tipo supportato.</span><span class="sxs-lookup"><span data-stu-id="0ce08-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="0ce08-111">COLLECTION (`>` <type_definition )</span><span class="sxs-lookup"><span data-stu-id="0ce08-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="0ce08-112">Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0ce08-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="0ce08-113">REF **(**`data_type`**)**</span><span class="sxs-lookup"><span data-stu-id="0ce08-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="0ce08-114">Espressione che restituisce un riferimento a un tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="0ce08-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="0ce08-115">RIGA **(**`row_expression`**)**</span><span class="sxs-lookup"><span data-stu-id="0ce08-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="0ce08-116">Espressione che restituisce record anonimi strutturalmente tipizzati da uno o più valori.</span><span class="sxs-lookup"><span data-stu-id="0ce08-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="0ce08-117">Per altre informazioni, vedere [ROW](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0ce08-117">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ce08-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0ce08-118">Remarks</span></span>  
 <span data-ttu-id="0ce08-119">Più funzioni con lo stesso nome possono essere dichiarate inline, purché le firme delle funzioni siano differenti.</span><span class="sxs-lookup"><span data-stu-id="0ce08-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="0ce08-120">Per altre informazioni, vedere [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0ce08-120">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="0ce08-121">È possibile chiamare una funzione inline in un comando Entity SQL solo dopo che è stata definita in quel comando.</span><span class="sxs-lookup"><span data-stu-id="0ce08-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="0ce08-122">Tuttavia, una funzione inline può essere chiamata in un'altra funzione inline prima o dopo che la funzione chiamata è stata definita.</span><span class="sxs-lookup"><span data-stu-id="0ce08-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="0ce08-123">Nell'esempio seguente la funzione A chiama la funzione B prima che la funzione B sia definita:</span><span class="sxs-lookup"><span data-stu-id="0ce08-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="0ce08-124">Per altre informazioni, vedere [Procedura: chiamare una funzione definita dall'utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0ce08-124">For more information, see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="0ce08-125">Le funzioni possono essere dichiarate anche nel modello stesso.</span><span class="sxs-lookup"><span data-stu-id="0ce08-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="0ce08-126">Le funzioni dichiarate nel modello vengono eseguite nello stesso modo delle funzioni dichiarate inline nel comando.</span><span class="sxs-lookup"><span data-stu-id="0ce08-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="0ce08-127">Per ulteriori informazioni, vedere [Funzioni definite dall'utente](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="0ce08-127">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ce08-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ce08-128">Example</span></span>  
 <span data-ttu-id="0ce08-129">Nel comando Entity SQL seguente viene definita una funzione `Products` che usa un valore Integer per filtrare i prodotti restituiti.</span><span class="sxs-lookup"><span data-stu-id="0ce08-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="0ce08-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ce08-130">Example</span></span>  
 <span data-ttu-id="0ce08-131">Nel comando Entity SQL seguente viene definita una funzione `StringReturnsCollection` che usa una raccolta di stringhe per filtrare i contatti restituiti.</span><span class="sxs-lookup"><span data-stu-id="0ce08-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="0ce08-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ce08-132">See also</span></span>

- [<span data-ttu-id="0ce08-133">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0ce08-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="0ce08-134">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0ce08-134">Entity SQL Language</span></span>](entity-sql-language.md)
