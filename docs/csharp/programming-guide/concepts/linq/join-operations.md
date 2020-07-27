---
title: :::no-loc(Join):::Operazioni (C#)
description: Un join di due origini dati associa gli oggetti a oggetti che condividono un attributo tra le origini dati. Informazioni sui metodi di join nel framework LINQ in C#.
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- ':::no-loc(Join):::'
- ':::no-loc(GroupJoin):::'
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165688"
---
# <a name="no-locjoin-operations-c"></a>:::no-loc(Join):::Operazioni (C#)

Un *join* di due origini dati è un'associazione di oggetti in un'origine dati con oggetti che condividono un attributo comune in un'altra origine dati.  
  
 :::no-loc(Join):::ING è un'operazione importante nelle query che hanno come destinazione origini dati le cui relazioni reciproche non possono essere seguite direttamente. Nella programmazione orientata a oggetti ciò potrebbe corrispondere a una correlazione non modellata tra oggetti, ad esempio la direzione inversa di una relazione unidirezionale. Un esempio di relazione unidirezionale è costituito da una classe Customer che include una proprietà di tipo City, ma la classe City non include una proprietà che sia una raccolta di oggetti Customer. Se si ha un elenco di oggetti City e si vogliono trovare tutti i clienti in ogni città, è possibile usare un'operazione join per individuarli.  
  
 I metodi di join disponibili nel framework LINQ sono <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> e <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A>. Questi metodi eseguono equijoin, ovvero join che associano due origini dati in base all'uguaglianza delle rispettive chiavi. Per il confronto, Transact-SQL supporta operatori join diversi da' Equals ', ad esempio l'operatore ' minore di '. In termini di database relazionale, <xref:System.Linq.Enumerable.:::no-loc(Join):::%2A> implementa un inner join, un tipo di join in cui vengono restituiti solo gli oggetti che hanno una corrispondenza nell'altro set di dati. Il metodo <xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A> non ha equivalenti diretti in termini di database relazionale, ma implementa un superset di inner join e left outer join. Un left outer join è un join che restituisce ogni elemento della prima origine dati (a sinistra), anche se non ha elementi correlati nell'altra origine dati.  
  
 L'illustrazione seguente mostra una visualizzazione concettuale dei due set e degli elementi dei set che sono inclusi in un inner join o in un left outer join.  
  
 ![Due cerchi sovrapposti che illustrano interno&#47;esterno.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|:::no-loc(Join):::|:::no-loc(Join):::s due sequenze basate sulle funzioni del selettore principale ed estrae coppie di valori.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.:::no-loc(Join):::%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.:::no-loc(Join):::%2A?displayProperty=nameWithType>|  
|:::no-loc(GroupJoin):::|:::no-loc(Join):::s due sequenze basate sulle funzioni del selettore di chiave e raggruppa le corrispondenze risultanti per ogni elemento.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.:::no-loc(GroupJoin):::%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.:::no-loc(GroupJoin):::%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query
  
### :::no-loc(Join):::  
  
Nell'esempio seguente viene usata la `join … in … on … equals …` clausola per unire in join due sequenze in base a un valore specifico:
  
[!code-csharp[:::no-loc(Join):::](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQ:::no-loc(Join):::Operation/CS/:::no-loc(Join):::Operation.cs#:::no-loc(Join):::)]  

### :::no-loc(GroupJoin):::  

Nell'esempio seguente viene usata la `join … in … on … equals … into …` clausola per unire in join due sequenze in base a un valore specifico e vengono raggruppate le corrispondenze risultanti per ogni elemento:
  
[!code-csharp[:::no-loc(GroupJoin):::](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQ:::no-loc(Join):::Operation/CS/:::no-loc(Join):::Operation.cs#:::no-loc(GroupJoin):::)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Tipi anonimi](../../classes-and-structs/anonymous-types.md)
- [Formulare :::no-loc(Join)::: le query e tra i prodotti](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [Clausola join](../../../language-reference/keywords/join-clause.md)
- [:::no-loc(Join):::usando chiavi composite](../../../linq/join-by-using-composite-keys.md)
- [Come unire il contenuto da file non analoghi (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md)
- [Ordinare i risultati di una clausola join](../../../linq/order-the-results-of-a-join-clause.md)
- [Eseguire operazioni di join personalizzate](../../../linq/perform-custom-join-operations.md)
- [Eseguire join raggruppati](../../../linq/perform-grouped-joins.md)
- [Eseguire inner join](../../../linq/perform-inner-joins.md)
- [Eseguire left outer join](../../../linq/perform-left-outer-joins.md)
- [Come popolare le raccolte di oggetti da più origini (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
