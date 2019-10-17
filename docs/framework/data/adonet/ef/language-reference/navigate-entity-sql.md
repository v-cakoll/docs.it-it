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
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Consente di eseguire la navigazione nella relazione stabilita tra le entità.

## <a name="syntax"></a>Sintassi

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>argomenti

`instance-expression` un'istanza di un'entità.

`relationship-type` il nome del tipo della relazione, dal file di Conceptual Schema Definition Language (CSDL). Il `relationship-type` è qualificato come \<namespace >. nome del tipo di \<relationship >.

`to` la fine della relazione.

`from` l'inizio della relazione.

## <a name="return-value"></a>Valore restituito

Se la cardinalità dell'entità finale è 1, il valore restituito è `Ref<T>`. Se la cardinalità dell'entità finale è n, il valore restituito è `Collection<Ref<T>>`.

## <a name="remarks"></a>Note

Le relazioni sono costrutti di prima classe nel Entity Data Model (EDM). È possibile stabilire relazioni tra due o più tipi di entità e navigare nella relazione da un'entità finale all'altra. I parametri`from` e `to` sono condizionatamente facoltativi in assenza di ambiguità nella risoluzione dei nomi all'interno della relazione.

NAVIGATE è valido nello spazio O e C.

Il formato generale di un costrutto di navigazione è il seguente:

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Esempio:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Dove OrderCustomer è l'oggetto `relationship`, mentre Customer e Order rappresentano l'oggetto `to-end` (Customer) e l'oggetto `from-end` (Order) della relazione. Se OrderCustomer è una relazione n:1, il tipo di risultato dell'espressione di navigazione è Ref \<Customer >.

La forma più semplice di questa espressione è la seguente:

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Analogamente, in una query con il formato seguente, l'espressione di navigazione produrrebbe una raccolta < Ref \<Order > >.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

L'espressione dell'istanza deve essere un tipo di entità/riferimento.

## <a name="example"></a>Esempio

Nella query Entity SQL seguente viene usato l'operatore NAVIGATE per eseguire la navigazione nella relazione stabilita tra i tipi di entità Address e SalesOrderHeader. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:

1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).

2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Procedura: esplorare relazioni con l'operatore Navigate](navigate-entity-sql.md)
