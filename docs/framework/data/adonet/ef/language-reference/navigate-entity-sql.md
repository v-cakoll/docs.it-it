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
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Consente di eseguire la navigazione nella relazione stabilita tra le entità.

## <a name="syntax"></a>Sintassi

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Argomenti

`instance-expression` Un'istanza di un'entità.

`relationship-type` Il nome del tipo della relazione, dal file conceptual schema definition language (CSDL). Il `relationship-type` è qualificato come \<dello spazio dei nomi >.\< Nome tipo relazione >.

`to` Fine della relazione.

`from` Inizio della relazione.

## <a name="return-value"></a>Valore restituito

Se la cardinalità dell'entità finale è 1, il valore restituito è `Ref<T>`. Se la cardinalità dell'entità finale è n, il valore restituito è `Collection<Ref<T>>`.

## <a name="remarks"></a>Note

Le relazioni sono costrutti di primaria importanza in [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM). È possibile stabilire relazioni tra due o più tipi di entità e navigare nella relazione da un'entità finale all'altra. I parametri`from` e `to` sono condizionatamente facoltativi in assenza di ambiguità nella risoluzione dei nomi all'interno della relazione.

NAVIGATE è valido nello spazio O e C.

Il formato generale di un costrutto di navigazione è il seguente:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Ad esempio:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Dove OrderCustomer è l'oggetto `relationship`, mentre Customer e Order rappresentano l'oggetto `to-end` (Customer) e l'oggetto `from-end` (Order) della relazione. Se OrderCustomer è una relazione n:1, il tipo di risultato dell'espressione di navigazione è Ref\<cliente >.

La forma più semplice di questa espressione è la seguente:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Analogamente, in una query nel formato seguente, l'espressione di navigazione produrrebbe come risultato Collection < Ref\<ordine >>.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

L'espressione dell'istanza deve essere un tipo di entità/riferimento.

## <a name="example"></a>Esempio

Nella query Entity SQL seguente viene usato l'operatore NAVIGATE per eseguire la navigazione nella relazione stabilita tra i tipi di entità Address e SalesOrderHeader. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:

1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Procedura: Esplorare relazioni con l'operatore Navigate](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
