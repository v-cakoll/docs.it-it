---
title: Clausola join - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- join
- join_CSharpKeyword
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
ms.openlocfilehash: 8e52e9db241392b67818b7316767dd97bd38432a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713401"
---
# <a name="join-clause-c-reference"></a>Clausola join (Riferimento C#)

Il clausola `join` è utile per l'associazione di elementi di sequenze di origine diverse che non hanno una relazione diretta nel modello a oggetti. L'unico requisito è che gli elementi in ogni origine condividano alcuni valori di cui può essere verificata l'uguaglianza. Un distributore di prodotti alimentari, ad esempio, potrebbe avere un elenco di fornitori di un determinato prodotto e un elenco di acquirenti. Con una clausola `join` è ad esempio possibile creare un elenco dei fornitori e degli acquirenti di tale prodotto che si trovano tutti nella stessa area specificata.

Una clausola `join` accetta due sequenze di origine come input. Gli elementi in ogni sequenza devono essere o devono contenere una proprietà che può essere confrontata con una proprietà corrispondente nell'altra sequenza. La clausola `join` verifica l'uguaglianza delle chiavi specificate usando la speciale parola chiave `equals`. Tutti i join eseguiti dalla clausola `join` sono equijoin. La forma dell'output di una clausola `join` dipende dal tipo specifico di join che si sta eseguendo. Di seguito vengono riportati i tre tipi di join più comuni:

- Inner join

- Group join

- Left outer join

## <a name="inner-join"></a>Inner join

In questo esempio viene illustrato un semplice inner equijoin. Questa query genera una sequenza semplice di coppie "nome prodotto / categoria". La stessa stringa della categoria verrà visualizzata in più elementi. Se per un elemento di `categories` non esistono `products` corrispondenti, tale categoria non verrà visualizzata nei risultati.

[!code-csharp[cscsrefQueryKeywords#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#24)]

Per altre informazioni, vedere [Eseguire inner join](../../linq/perform-inner-joins.md).

## <a name="group-join"></a>Group join

Una clausola `join` con un'espressione `into` viene detta group join.

[!code-csharp[cscsrefQueryKeywords#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#25)]

Un group join genera una sequenza di risultati gerarchici, che associa gli elementi nella sequenza di origine a sinistra con uno o più elementi corrispondenti nella sequenza di origine a destra. Un group join non ha equivalente in termini relazionali. Si tratta essenzialmente di una sequenza di matrici di oggetti.

Se nessun elemento della sequenza di origine a destra corrisponde a un elemento nell'origine a sinistra, la clausola `join` genererà una matrice vuota per tale elemento. Il group join rimane fondamentalmente un inner equijoin tranne per il fatto che la sequenza di risultati è organizzata in gruppi.

Se si selezionano i risultati di un group join, è possibile accedere agli elementi, ma non è possibile identificare la chiave alla quale corrispondono. È quindi generalmente più utile selezionare i risultati del group join in un tipo nuovo che ha anche il nome della chiave, come illustrato nell'esempio precedente.

È ovviamente anche possibile usare il risultato di un group join come generatore di un'altra sottoquery:

[!code-csharp[cscsrefQueryKeywords#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#26)]

Per altre informazioni, vedere [Eseguire join raggruppati](../../linq/perform-grouped-joins.md).

## <a name="left-outer-join"></a>Left outer join

In un left outer join vengono restituiti tutti gli elementi nella sequenza di origine a sinistra, anche se non sono disponibili elementi corrispondenti nella sequenza a destra. Per eseguire un left outer join `DefaultIfEmpty` in LINQ, usare il metodo in combinazione con un group join per specificare un elemento del lato destro predefinito da produrre se un elemento del lato sinistro non ha corrispondenze. È possibile usare `null` come valore predefinito per qualsiasi tipo di riferimento oppure specificare un tipo predefinito definito dall'utente. Nell'esempio seguente viene illustrato un tipo predefinito definito dall'utente:

[!code-csharp[cscsrefQueryKeywords#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#27)]

Per altre informazioni, vedere [Eseguire left outer join](../../linq/perform-left-outer-joins.md).

## <a name="the-equals-operator"></a>Operatore di uguaglianza

Una clausola `join` esegue un equijoin. In altre parole, è possibile basare le corrispondenze solo sull'uguaglianza di due chiavi. Altri tipi di confronti, quale "maggiore di" o "diverso da", non sono supportati. Per specificare chiaramente che tutti i join sono equijoin, la clausola `join` usa la parola chiave `equals` anziché l'operatore `==`. La parola chiave `equals` può essere usata solo in una clausola `join` e differisce dall'operatore `==` per un aspetto importante. Con `equals` la chiave a sinistra usa la sequenza di origine esterna, mentre la chiave a destra usa l'origine interna. L'origine esterna si trova solo nell'ambito sul lato sinistro di `equals` e la sequenza di origine interna si trova solo nell'ambito sul lato destro.

## <a name="non-equijoins"></a>Non equijoin

È possibile eseguire non equijoin, cross join e altre operazioni di join personalizzate usando più clausole `from` per introdurre indipendentemente nuove sequenze in una query. Per altre informazioni, vedere [Eseguire operazioni di join personalizzate](../../linq/perform-custom-join-operations.md).

## <a name="joins-on-object-collections-vs-relational-tables"></a>Join su raccolte di oggetti e tabelle relazionali

In un'espressione di query LINQLINQ vengono eseguite operazioni di join sulle raccolte di oggetti. Le raccolte di oggetti non possono essere "aggiunte" nello stesso modo in cui si aggiungono due tabelle relazionali. In LINQ `join` le clausole esplicite sono necessarie solo quando due sequenze di origine non sono legate ad alcuna relazione. Quando si usa [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], le tabelle di chiavi esterne vengono rappresentate nel modello a oggetti come proprietà della tabella primaria. Nel database Northwind, ad esempio, la tabella Customer ha una relazione di chiavi esterne con la tabella Orders. Quando si esegue il mapping delle tabelle al modello a oggetti, la classe Customer presenta una proprietà Orders che contiene la raccolta degli ordini associati a tale cliente. In effetti, il join è già stato automaticamente eseguito.

Per altre informazioni sull'esecuzione di una query in tabelle correlate nel contesto di [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], vedere [Procedura: Eseguire il mapping delle relazioni di database](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md).

## <a name="composite-keys"></a>Chiavi composte

È possibile verificare l'uguaglianza di più valori usando una chiave composta. Per altre informazioni, vedere [Eseguire un join usando chiavi composte](../../linq/join-by-using-composite-keys.md). Le chiavi composte possono essere usate anche nella clausola `group`.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono confrontati i risultati di un inner join, di un group join e di un left outer join nelle stesse origini dati usando le medesime chiavi corrispondenti. A questi esempi viene aggiunto altro codice per chiarire i risultati nella visualizzazione della console.

[!code-csharp[cscsrefQueryKeywords#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Join.cs#23)]

## <a name="remarks"></a>Osservazioni

Una clausola `join` non seguita da `into` viene traslata in una chiamata al metodo <xref:System.Linq.Enumerable.Join%2A>. Una clausola `join` seguita da `into` viene traslata in una chiamata al metodo <xref:System.Linq.Enumerable.GroupJoin%2A>.

## <a name="see-also"></a>Vedere anche

- [Parole chiave di query (LINQ)Query Keywords (LINQ)](query-keywords.md)
- [Language Integrated Query (LINQ)](../../linq/index.md)
- [Operazioni di unione](../../programming-guide/concepts/linq/join-operations.md)
- [Clausola group](group-clause.md)
- [Eseguire outer join a sinistra](../../linq/perform-left-outer-joins.md)
- [Eseguire inner join](../../linq/perform-inner-joins.md)
- [Eseguire join raggruppati](../../linq/perform-grouped-joins.md)
- [Ordinare i risultati di una clausola join](../../linq/order-the-results-of-a-join-clause.md)
- [Eseguire un join usando chiavi composte](../../linq/join-by-using-composite-keys.md)
- [Sistemi di database compatibili per Visual Studio](/visualstudio/data-tools/installing-database-systems-tools-and-samples)
