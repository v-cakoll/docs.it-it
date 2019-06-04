---
title: Espressioni non supportate (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: af0e00f470584883b6a65b63f2650c1c359b404c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489865"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="83c9c-102">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="83c9c-102">Unsupported expressions</span></span>

<span data-ttu-id="83c9c-103">In questo argomento descrive le espressioni di Transact-SQL che non sono supportate in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83c9c-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="83c9c-104">Per altre informazioni, vedere [modo in cui Entity SQL è diversa da Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="83c9c-104">For more information, see [How Entity SQL Differs from Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="83c9c-105">Predicati quantificati</span><span class="sxs-lookup"><span data-stu-id="83c9c-105">Quantified predicates</span></span>

<span data-ttu-id="83c9c-106">Transact-SQL consente i costrutti del form seguente:</span><span class="sxs-lookup"><span data-stu-id="83c9c-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="83c9c-107">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], tuttavia, tali costrutti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="83c9c-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="83c9c-108">È possibile scrivere espressioni equivalenti in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="83c9c-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="83c9c-109">\* (operatore)</span><span class="sxs-lookup"><span data-stu-id="83c9c-109">\* operator</span></span>

<span data-ttu-id="83c9c-110">Transact-SQL supporta l'uso del \* operatore nella clausola SELECT per indicare che tutte le colonne devono essere proiettate. Questa opzione non è supportata in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83c9c-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="83c9c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c9c-111">See also</span></span>

- [<span data-ttu-id="83c9c-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83c9c-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="83c9c-113">Differenze tra Entity SQL e Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="83c9c-113">How Entity SQL Differs from Transact-SQL</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)
