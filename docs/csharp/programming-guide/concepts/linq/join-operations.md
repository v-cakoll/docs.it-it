---
title: JoinOperazioni (C )Operations (C
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 6e2ec1a0c8120f6869b7c0a196b77d118762a8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76868005"
---
# <a name="join-operations-c"></a>Operazioni di join (C#)

Un *join* di due origini dati è un'associazione di oggetti in un'origine dati con oggetti che condividono un attributo comune in un'altra origine dati.  
  
 La creazione di un join è un'operazione importante nelle query che fanno riferimento a origini dati le cui relazioni reciproche non possono essere seguite direttamente. Nella programmazione orientata a oggetti ciò potrebbe corrispondere a una correlazione non modellata tra oggetti, ad esempio la direzione inversa di una relazione unidirezionale. Un esempio di relazione unidirezionale è costituito da una classe Customer che include una proprietà di tipo City, ma la classe City non include una proprietà che sia una raccolta di oggetti Customer. Se si ha un elenco di oggetti City e si vogliono trovare tutti i clienti in ogni città, è possibile usare un'operazione join per individuarli.  
  
 I metodi di join disponibili nel framework LINQ sono <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A>. Questi metodi eseguono equijoin, ovvero join che associano due origini dati in base all'uguaglianza delle rispettive chiavi. Per confronto, Transact-SQLTransact-SQL supporta operatori di join diversi da 'equals', ad esempio l'operatore 'minore di'. In termini di <xref:System.Linq.Enumerable.Join%2A> database relazionale implementa un inner join, un tipo di join in cui vengono restituiti solo gli oggetti che hanno una corrispondenza nell'altro set di dati. Il metodo <xref:System.Linq.Enumerable.GroupJoin%2A> non ha equivalenti diretti in termini di database relazionale, ma implementa un superset di inner join e left outer join. Un left outer join è un join che restituisce ogni elemento della prima origine dati (a sinistra), anche se non ha elementi correlati nell'altra origine dati.  
  
 L'illustrazione seguente mostra una visualizzazione concettuale dei due set e degli elementi dei set che sono inclusi in un inner join o in un left outer join.  
  
 ![Due cerchi sovrapposti che illustrano interno&#47;esterno.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|Unisce due sequenze in base a funzioni selector chiave ed estrae coppie di valori|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Unisce due sequenze in base a funzioni selector chiave e raggruppa le corrispondenze risultanti per ogni elemento.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di queryQuery expression syntax examples
  
### Join  
  
Nell'esempio seguente `join … in … on … equals …` viene utilizzata la clausola per unire due sequenze in base a un valore specifico:The following example uses the clause to join two sequences based on specific value:
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

Nell'esempio seguente `join … in … on … equals … into …` viene utilizzata la clausola per unire due sequenze in base a un valore specifico e raggruppa le corrispondenze risultanti per ogni elemento:
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Tipi anonimi](../../classes-and-structs/anonymous-types.md)
- [Formulare join e query di prodotto incrociato](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [clausola join](../../../language-reference/keywords/join-clause.md)
- [Joinutilizzando chiavi composte](../../../linq/join-by-using-composite-keys.md)
- [Come unire il contenuto da file diversi (LINQ) (C](./how-to-join-content-from-dissimilar-files-linq.md)
- [Ordinare i risultati di una clausola join](../../../linq/order-the-results-of-a-join-clause.md)
- [Eseguire operazioni di join personalizzate](../../../linq/perform-custom-join-operations.md)
- [Eseguire join raggruppati](../../../linq/perform-grouped-joins.md)
- [Eseguire inner join](../../../linq/perform-inner-joins.md)
- [Eseguire outer join a sinistra](../../../linq/perform-left-outer-joins.md)
- [Come popolare le raccolte di oggetti da più origini (LINQ) (C](./how-to-populate-object-collections-from-multiple-sources-linq.md)
