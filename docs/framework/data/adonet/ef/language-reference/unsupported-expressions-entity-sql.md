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
# <a name="unsupported-expressions"></a>Espressioni non supportate

In questo argomento vengono descritte le espressioni Transact-SQL non supportate [!INCLUDE[esql](../../../../../../includes/esql-md.md)]in. Per ulteriori informazioni, vedere [come Entity SQL differisce da Transact-SQL](how-entity-sql-differs-from-transact-sql.md).

## <a name="quantified-predicates"></a>Predicati quantificati

Transact-SQL consente i costrutti con il formato seguente:

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], tuttavia, tali costrutti non sono supportati. È possibile scrivere espressioni equivalenti in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] come indicato di seguito:

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a>* (operatore)

Transact-SQL supporta l'utilizzo dell'operatore * nella clausola SELECT per indicare che tutte le colonne devono essere proiettate. Questa opzione non è supportata in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

## <a name="see-also"></a>Vedere anche

- [Panoramica di Entity SQL](entity-sql-overview.md)
- [Differenze tra Entity SQL e Transact-SQL](how-entity-sql-differs-from-transact-sql.md)
