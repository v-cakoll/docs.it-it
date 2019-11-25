---
title: Operazioni di join
ms.date: 07/20/2015
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
ms.openlocfilehash: b09574369185be13664276c2e84697fc4969c6f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353300"
---
# <a name="join-operations-visual-basic"></a>Join Operations (Visual Basic)
Un *join* di due origini dati è un'associazione di oggetti in un'origine dati con oggetti che condividono un attributo comune in un'altra origine dati.  
  
 La creazione di un join è un'operazione importante nelle query che fanno riferimento a origini dati le cui relazioni reciproche non possono essere seguite direttamente. Nella programmazione orientata a oggetti ciò potrebbe corrispondere a una correlazione non modellata tra oggetti, ad esempio la direzione inversa di una relazione unidirezionale. Un esempio di relazione unidirezionale è costituito da una classe Customer che include una proprietà di tipo City, ma la classe City non include una proprietà che sia una raccolta di oggetti Customer. Se si ha un elenco di oggetti City e si vogliono trovare tutti i clienti in ogni città, è possibile usare un'operazione join per individuarli.  
  
 I metodi di join disponibili nel framework LINQ sono <xref:System.Linq.Enumerable.Join%2A> e <xref:System.Linq.Enumerable.GroupJoin%2A>. Questi metodi eseguono equijoin, ovvero join che associano due origini dati in base all'uguaglianza delle rispettive chiavi. (For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned. Il metodo <xref:System.Linq.Enumerable.GroupJoin%2A> non ha equivalenti diretti in termini di database relazionale, ma implementa un superset di inner join e left outer join. Un left outer join è un join che restituisce ogni elemento della prima origine dati (a sinistra), anche se non ha elementi correlati nell'altra origine dati.  
  
 L'illustrazione seguente mostra una visualizzazione concettuale dei due set e degli elementi dei set che sono inclusi in un inner join o in un left outer join.  
  
 ![Due cerchi sovrapposti che illustrano interno&#47;esterno.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Visual Basic Query Expression Syntax|Altre informazioni|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|Unisce due sequenze in base a funzioni selector chiave ed estrae coppie di valori|`From x In …, y In … Where x.a = y.a`<br /><br /> oppure<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Unisce due sequenze in base a funzioni selector chiave e raggruppa le corrispondenze risultanti per ogni elemento.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Formulare join e query di prodotto incrociato](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md)
- [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)
- [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
