---
title: Espressioni non supportate (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248786"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="3a2a0-102">Espressioni non supportate</span><span class="sxs-lookup"><span data-stu-id="3a2a0-102">Unsupported expressions</span></span>

<span data-ttu-id="3a2a0-103">In questo argomento vengono descritte le espressioni Transact-SQL non supportate [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="3a2a0-104">Per ulteriori informazioni, vedere [come Entity SQL differisce da Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3a2a0-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="3a2a0-105">Predicati quantificati</span><span class="sxs-lookup"><span data-stu-id="3a2a0-105">Quantified predicates</span></span>

<span data-ttu-id="3a2a0-106">Transact-SQL consente i costrutti con il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="3a2a0-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

<span data-ttu-id="3a2a0-107">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], tuttavia, tali costrutti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3a2a0-107">[!INCLUDE[esql](../../../../../../includes/esql-md.md)], however, does not support such constructs.</span></span> <span data-ttu-id="3a2a0-108">È possibile scrivere espressioni equivalenti in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3a2a0-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="3a2a0-109">\* (operatore)</span><span class="sxs-lookup"><span data-stu-id="3a2a0-109">\* operator</span></span>

<span data-ttu-id="3a2a0-110">Transact-SQL supporta l'utilizzo dell'operatore \* nella clausola SELECT per indicare che tutte le colonne devono essere proiettate. Questa opzione non è supportata in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a2a0-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="3a2a0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a2a0-111">See also</span></span>

- [<span data-ttu-id="3a2a0-112">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3a2a0-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="3a2a0-113">Differenze tra Entity SQL e Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a2a0-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
