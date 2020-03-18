---
title: Eseguire un join usando una chiave composta (LINQ in C#)
description: Informazioni su come eseguire un join usando una chiave composta in LINQ.
ms.date: 12/01/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: 460a52da7e0c0a47b77d4c64e76641bae9da7cd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659878"
---
# <a name="join-by-using-composite-keys"></a>Eseguire un join usando chiavi composte

In questo esempio viene illustrato come eseguire operazioni di join in cui si vuole usare più di una chiave per definire una corrispondenza. Ciò è possibile usando una chiave composta, che viene creata come tipo anonimo o tipo denominato con i valori che si vogliono confrontare. Se la variabile di query viene passata attraverso i limiti del metodo, usare un tipo denominato che esegue l'override di <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> per la chiave. I nomi delle proprietà e l'ordine in cui si verificano devono essere identici in ogni chiave.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come usare una chiave composta per eseguire un join dei dati da tre tabelle:

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

L'inferenza del tipo nelle chiavi composte dipende dai nomi delle proprietà nelle chiavi e dall'ordine in cui si verificano. Se le proprietà nelle sequenze di origine non contengono gli stessi nomi, è necessario assegnare nuovi nomi nelle chiavi. Ad esempio, se nella tabella `Orders` e nella tabella `OrderDetails` vengono usati nomi diversi per le colonne, è possibile creare chiavi composte assegnando nomi identici nei tipi anonimi:

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

Le chiavi composte possono essere usate anche nella clausola `group`.

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
- [clausola join](../language-reference/keywords/join-clause.md)
- [Clausola group](../language-reference/keywords/group-clause.md)
