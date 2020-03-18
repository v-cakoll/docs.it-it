---
title: Clausola group (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 75a366ec24e4e48af7e87d3372950aad8d76435b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713464"
---
# <a name="group-clause-c-reference"></a>Clausola group (Riferimento C#)

La clausola `group` restituisce una sequenza di oggetti <xref:System.Linq.IGrouping%602> che contengono zero o più elementi corrispondenti al valore chiave per il gruppo. Ad esempio, è possibile raggruppare una sequenza di stringhe in base alla prima lettera di ogni stringa. In questo caso, la prima lettera è la chiave con tipo [char](../builtin-types/char.md) e viene archiviata nella proprietà `Key` di ogni oggetto <xref:System.Linq.IGrouping%602>. Il compilatore deduce automaticamente il tipo della chiave.

È possibile terminare un'espressione di query con una clausola `group`, come illustrato nell'esempio seguente:

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

Per eseguire operazioni di query aggiuntive per ogni gruppo, è possibile specificare un identificatore temporaneo usando la parola chiave contestuale [into](into.md). Quando si usa `into`, è necessario continuare a eseguire la query ed eventualmente terminarla con un'istruzione `select` o un'altra clausola `group`, come illustrato nel seguente estratto di codice:

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

Esempi di utilizzo di più completi di `group` con e senza `into` sono disponibili nella sezione Esempio di questo articolo.

## <a name="enumerating-the-results-of-a-group-query"></a>Enumerazione dei risultati di una query con raggruppamento

Poiché gli oggetti <xref:System.Linq.IGrouping%602> prodotti da una query `group` sono essenzialmente un elenco di elenchi, è necessario usare un ciclo [foreach](foreach-in.md) nidificato per accedere agli elementi di ogni gruppo. Il ciclo esterno esegue l'iterazione delle chiavi del gruppo e il ciclo interno esegue l'iterazione di ogni voce nel gruppo. Un gruppo può avere una chiave ma non elementi. Di seguito è riportato il ciclo `foreach` che esegue la query negli esempi di codice precedenti:

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a>Tipi di chiave

Le chiavi di raggruppamento possono essere di qualsiasi tipo, ad esempio una stringa, un tipo numerico incorporato, un tipo con nome definito dall'utente o un tipo anonimo.

### <a name="grouping-by-string"></a>Raggruppamento per stringa

Negli esempi di codice precedenti è stato usato un oggetto `char`. Si potrebbe specificare in alternativa una chiave di stringa, ad esempio il cognome completo:

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a>Raggruppamento per valore booleano

L'esempio seguente illustra l'uso di un valore booleano per una chiave in modo da dividere i risultati in due gruppi. Si noti che il valore è generato da una sottoespressione nella clausola `group`.

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a>Raggruppamento per intervallo numerico

Nell'esempio seguente viene usata un'espressione per creare le chiavi di raggruppamento numeriche che rappresentano un intervallo percentile. Si noti l'uso di [let](let-clause.md) come comoda posizione di archiviazione del risultato della chiamata a un metodo, in modo da non dover chiamare il metodo due volte nella clausola `group`. Per ulteriori informazioni su come utilizzare in modo sicuro i metodi nelle espressioni di query, vedere [Gestire le eccezioni nelle espressioni](../../linq/handle-exceptions-in-query-expressions.md)di query.

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a>Raggruppamento per chiavi composte

Usare una chiave composta se si vuole raggruppare gli elementi in base a più di una chiave. Per creare una chiave composta, usare un tipo anonimo o un tipo denominato per contenere l'elemento key. Nell'esempio seguente si suppone che una classe `Person` sia stata dichiarata con i membri denominati `surname` e `city`. La clausola `group` determina la creazione di un gruppo separato per ogni insieme di persone con lo stesso cognome e la stessa città.

```csharp
group person by new {name = person.surname, city = person.city};
```

Usare un tipo denominato se è necessario passare la variabile di query a un altro metodo. Creare una classe speciale usando proprietà implementate automaticamente per le chiavi e quindi eseguire l'override dei metodi <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A>. È anche possibile usare uno struct e in questo caso non è strettamente necessario eseguire l'override dei metodi. Per ulteriori informazioni, vedere [Come implementare una classe leggera con proprietà implementate automaticamente](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) e Come eseguire query per i file duplicati in una struttura di [directory.](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md) Il secondo articolo contiene un esempio di codice che illustra come usare una chiave composta con un tipo denominato.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato il modello standard per l'ordinamento dei dati di origine nei gruppi quando non viene applicata una logica di query aggiuntiva ai gruppi. L'operazione è definita raggruppamento senza continuazione. Gli elementi in una matrice di stringhe vengono raggruppati in base alla prima lettera. Il risultato della query è un tipo <xref:System.Linq.IGrouping%602> che contiene una proprietà pubblica `Key` di tipo `char` e una raccolta <xref:System.Collections.Generic.IEnumerable%601> che contiene ogni elemento nel raggruppamento.

Il risultato di una clausola `group` è una sequenza di sequenze. Di conseguenza, per accedere ai singoli elementi all'interno di ogni gruppo restituito, usare un ciclo `foreach` nidificato all'interno del ciclo che esegue l'iterazione delle chiavi di raggruppamento, come illustrato nell'esempio seguente.

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a>Esempio

In questo esempio viene illustrato come eseguire la logica aggiuntiva per i gruppi dopo che sono stati creati, usando una *continuazione* con `into`. Per altre informazioni, vedere [into](into.md). Nell'esempio seguente viene eseguita una query di ogni gruppo per selezionare solo quelli il cui valore della chiave è una vocale.

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a>Osservazioni

In fase di compilazione le clausole `group` vengono convertite in chiamate al metodo <xref:System.Linq.Enumerable.GroupBy%2A>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [Parole chiave per le query](query-keywords.md)
- [Language Integrated Query (LINQ)](../../linq/index.md)
- [Creare un gruppo nidificato](../../linq/create-a-nested-group.md)
- [Raggruppare i risultati delle query](../../linq/group-query-results.md)
- [Eseguire una sottoquery su un'operazione di raggruppamento](../../linq/perform-a-subquery-on-a-grouping-operation.md)
