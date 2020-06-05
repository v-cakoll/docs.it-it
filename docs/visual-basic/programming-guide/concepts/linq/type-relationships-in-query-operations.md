---
title: Relazioni tra i tipi nelle operazioni di query
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 73a287541ddf115510bf6ab5c830eafac370cc3a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406729"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relazioni tra i tipi nelle operazioni di query (Visual Basic)

Le variabili utilizzate nelle operazioni di query LINQ (Language Integrated Query) sono fortemente tipizzate e devono essere compatibili tra loro. La tipizzazione forte viene utilizzata nell'origine dati, nella query stessa e nell'esecuzione della query. Nell'illustrazione seguente vengono identificati i termini utilizzati per descrivere una query LINQ. Per ulteriori informazioni sulle parti di una query, vedere [operazioni di query di base (Visual Basic)](basic-query-operations.md).

![Screenshot che mostra una query pseudocodice con elementi evidenziati.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

Il tipo della variabile di intervallo nella query deve essere compatibile con il tipo degli elementi nell'origine dati. Il tipo della variabile di query deve essere compatibile con l'elemento Sequence definito nella `Select` clausola. Infine, anche il tipo degli elementi di sequenza deve essere compatibile con il tipo della variabile di controllo del ciclo utilizzata nell' `For Each` istruzione che esegue la query. Questa tipizzazione forte facilita l'identificazione degli errori di tipo in fase di compilazione.

Visual Basic rende comoda la tipizzazione forte implementando l'inferenza del tipo locale, nota anche come *tipizzazione implicita*. Tale funzionalità viene utilizzata nell'esempio precedente e verrà utilizzata in tutti gli esempi e la documentazione di LINQ. In Visual Basic, l'inferenza del tipo locale viene eseguita semplicemente utilizzando un' `Dim` istruzione senza una `As` clausola. Nell'esempio seguente, `city` è fortemente tipizzato come stringa.

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> L'inferenza del tipo locale funziona solo quando `Option Infer` è impostato su `On` . Per altre informazioni, vedere [istruzione Option dedurre](../../../language-reference/statements/option-infer-statement.md).

Tuttavia, anche se si usa l'inferenza del tipo locale in una query, le stesse relazioni di tipo sono presenti tra le variabili nell'origine dati, la variabile di query e il ciclo di esecuzione della query. È utile avere una conoscenza di base di queste relazioni tra i tipi durante la scrittura di query LINQ o l'uso degli esempi e degli esempi di codice nella documentazione.

Potrebbe essere necessario specificare un tipo esplicito per una variabile di intervallo che non corrisponde al tipo restituito dall'origine dati. È possibile specificare il tipo della variabile di intervallo utilizzando una `As` clausola. Tuttavia, questo genera un errore se la conversione è una conversione verso un tipo di dati più [piccolo](../../language-features/data-types/widening-and-narrowing-conversions.md) e `Option Strict` viene impostata su `On` . Pertanto, è consigliabile eseguire la conversione sui valori recuperati dall'origine dati. È possibile convertire i valori dall'origine dati al tipo di variabile di intervallo esplicito usando il <xref:System.Linq.Enumerable.Cast%2A> metodo. È anche possibile eseguire il cast dei valori selezionati nella `Select` clausola a un tipo esplicito diverso dal tipo della variabile di intervallo. Questi punti vengono illustrati nel codice seguente.

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Query che restituiscono interi elementi dei dati di origine

Nell'esempio seguente viene illustrata un'operazione di query LINQ che restituisce una sequenza di elementi selezionati dai dati di origine. L'origine, `names` , contiene una matrice di stringhe e l'output della query è una sequenza contenente stringhe che iniziano con la lettera M.

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

Questo è equivalente al codice seguente, ma è molto più breve e più facile da scrivere. La dipendenza dall'inferenza del tipo locale nelle query è lo stile preferito in Visual Basic.

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

Le relazioni seguenti sono presenti in entrambi gli esempi di codice precedenti, indipendentemente dal fatto che i tipi vengano determinati in modo implicito o esplicito.

1. Il tipo degli elementi nell'origine dati, `names` , è il tipo della variabile di intervallo, `name` , nella query.

2. Il tipo dell'oggetto selezionato, `name` , determina il tipo della variabile di query, `mNames` . Ecco `name` una stringa, quindi la variabile di query è IEnumerable (Of String) in Visual Basic.

3. La query definita in `mNames` viene eseguita nel `For Each` ciclo. Il ciclo scorre il risultato dell'esecuzione della query. Poiché `mNames` , quando viene eseguita, restituirà una sequenza di stringhe, anche la variabile di iterazione del ciclo, `nm` , è una stringa.

## <a name="queries-that-return-one-field-from-selected-elements"></a>Query che restituiscono un campo da elementi selezionati

Nell'esempio seguente viene illustrata un' [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operazione di query che restituisce una sequenza contenente solo una parte di ogni elemento selezionato dall'origine dati. La query accetta una raccolta di `Customer` oggetti come origine dati e proietta solo la `Name` proprietà nel risultato. Poiché il nome del cliente è una stringa, la query genera una sequenza di stringhe come output.

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

Le relazioni tra le variabili sono simili a quelle nell'esempio più semplice.

1. Il tipo degli elementi nell'origine dati, `customers` , è il tipo della variabile di intervallo, `cust` , nella query. In questo esempio, il tipo è `Customer` .

2. L' `Select` istruzione restituisce la `Name` proprietà di ogni `Customer` oggetto anziché l'intero oggetto. Poiché `Name` è una stringa, la variabile di query, `custNames` , sarà di nuovo IEnumerable (Of String), non di `Customer` .

3. Poiché `custNames` rappresenta una sequenza di stringhe, la `For Each` variabile di iterazione del ciclo, `custName` , deve essere una stringa.

Senza inferenza del tipo locale, l'esempio precedente sarebbe più complesso da scrivere e comprendere, come illustrato nell'esempio seguente.

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a>Query che richiedono tipi anonimi

Nell'esempio seguente viene illustrata una situazione più complessa. Nell'esempio precedente, non era pratico specificare i tipi per tutte le variabili in modo esplicito. In questo esempio, non è possibile. Anziché selezionare interi `Customer` elementi dall'origine dati o un singolo campo da ogni elemento, la `Select` clausola in questa query restituisce due proprietà dell' `Customer` oggetto originale: `Name` e `City` . In risposta alla `Select` clausola, il compilatore definisce un tipo anonimo che contiene queste due proprietà. Il risultato dell'esecuzione `nameCityQuery` nel ciclo è costituito da `For Each` una raccolta di istanze del nuovo tipo anonimo. Poiché il tipo anonimo non ha un nome utilizzabile, non è possibile specificare il tipo di `nameCityQuery` o in `custInfo` modo esplicito. Ovvero, con un tipo anonimo, non è disponibile alcun nome di tipo da usare al posto di `String` in `IEnumerable(Of String)` . Per ulteriori informazioni, vedere [tipi anonimi](../../language-features/objects-and-classes/anonymous-types.md).

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

Sebbene non sia possibile specificare i tipi per tutte le variabili nell'esempio precedente, le relazioni rimangono invariate.

1. Il tipo degli elementi nell'origine dati è di nuovo il tipo della variabile di intervallo nella query. In questo esempio, `cust` è un'istanza di `Customer` .

2. Poiché l' `Select` istruzione genera un tipo anonimo, la variabile di query, `nameCityQuery` , deve essere tipizzata in modo implicito come tipo anonimo. Un tipo anonimo non ha un nome utilizzabile e pertanto non può essere specificato in modo esplicito.

3. Il tipo della variabile di iterazione nel `For Each` ciclo è il tipo anonimo creato nel passaggio 2. Poiché il tipo non ha un nome utilizzabile, il tipo della variabile di iterazione del ciclo deve essere determinato in modo implicito.

## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](getting-started-with-linq.md)
- [Tipi anonimi](../../language-features/objects-and-classes/anonymous-types.md)
- [Inferenza del tipo di variabile locale](../../language-features/variables/local-type-inference.md)
- [Introduzione a LINQ in Visual Basic](../../language-features/linq/introduction-to-linq.md)
- [LINQ](../../language-features/linq/index.md)
- [Query](../../../language-reference/queries/index.md)
