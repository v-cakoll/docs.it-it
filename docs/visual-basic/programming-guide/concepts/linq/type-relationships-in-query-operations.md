---
title: Relazioni tra i tipi nelle operazioni di query (Visual Basic)
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
ms.openlocfilehash: 14f17e89e2a4143580b4a2ca7f9d30013ded58f9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327633"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relazioni tra i tipi nelle operazioni di query (Visual Basic)
Le variabili usate nella [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operazioni sono fortemente tipizzate e devono essere compatibili tra loro. Tipizzazione forte viene usata nell'origine dati, nella query stessa e nell'esecuzione della query. Nella figura seguente identifica i termini usati per descrivere un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. Per altre informazioni sulle parti di una query, vedere [operazioni di Query (Visual Basic) base](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Screenshot che mostra una query pseudocodice con elementi evidenziati.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 Il tipo della variabile di intervallo nella query deve essere compatibile con il tipo degli elementi nell'origine dati. Il tipo della variabile di query deve essere compatibile con l'elemento della sequenza definita nel `Select` clausola. Infine, il tipo degli elementi sequenza inoltre deve essere compatibile con il tipo della variabile di controllo del ciclo che viene utilizzata per il `For Each` istruzione che esegue la query. Questa forte tipizzazione forte semplifica l'identificazione degli errori di tipo in fase di compilazione.  
  
 Visual Basic tipizzazione forte viene applicata mediante l'implementazione di inferenza del tipo locale, noto anche come *tipizzazione implicita*. Funzionalità viene usata nell'esempio precedente che sarà possibile vederlo usata in tutta il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esempi e documentazione. In Visual Basic, l'inferenza del tipo locale viene eseguita usando semplicemente una `Dim` istruzione senza un `As` clausola. Nell'esempio seguente, `city` è fortemente tipizzata come una stringa.  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
>  L'inferenza del tipo locale funziona solo quando `Option Infer` è impostata su `On`. Per altre informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Tuttavia, anche se si usa l'inferenza del tipo locale in una query, le relazioni di tipo stesso sono presenti tra le variabili nell'origine dati, la variabile di query e il ciclo di esecuzione di query. È utile avere una conoscenza di base di queste relazioni di tipo quando si scrive [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] , query o dell'utilizzo con gli esempi e gli esempi di codice nella documentazione.  
  
 Si potrebbe essere necessario specificare un tipo esplicito per una variabile di intervallo che non corrisponde al tipo restituito dall'origine dati. È possibile specificare il tipo della variabile di intervallo usando un `As` clausola. Tuttavia, ciò comporta un errore se la conversione è un [conversione di narrowing](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e `Option Strict` è impostata su `On`. Pertanto, è consigliabile eseguire la conversione in base ai valori recuperati dall'origine dati. È possibile convertire i valori dall'origine dati per il tipo di variabile di intervallo esplicita tramite la <xref:System.Linq.Enumerable.Cast%2A> (metodo). È anche possibile eseguire il cast ai valori selezionati nel `Select` clausola per un tipo esplicito che è diverso dal tipo della variabile di intervallo. Questi aspetti sono illustrati nel codice seguente.  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Query che restituiscono gli elementi completi dei dati di origine  
 L'esempio seguente mostra un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operazione che restituisce una sequenza di elementi selezionati dall'origine dati di query. L'origine, `names`, contiene una matrice di stringhe, e l'output della query è una sequenza che contiene le stringhe che iniziano con la lettera M.  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 Ciò equivale al codice seguente, ma è molto più breve e facile da scrivere. Dipendenza dall'inferenza dei tipi locali nelle query è lo stile preferito in Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 Le relazioni seguenti disponibili in entrambi gli esempi di codice precedenti, se i tipi sono determinati in modo implicito o esplicito.  
  
1. Il tipo degli elementi nell'origine dati, `names`, è il tipo della variabile di intervallo, `name`, nella query.  
  
2. Il tipo dell'oggetto che sia selezionata `name`, determina il tipo della variabile di query, `mNames`. Di seguito `name` è una stringa, in modo che la variabile di query è IEnumerable (Of String) in Visual Basic.  
  
3. La query definita nella `mNames` viene eseguita nel `For Each` ciclo. Il ciclo scorre il risultato dell'esecuzione della query. In quanto `mNames`, quando eseguita, restituisce una sequenza di stringhe, la variabile di iterazione del ciclo, `nm`, inoltre è una stringa.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Query che restituiscono un campo da elementi selezionati  
 L'esempio seguente mostra un [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operazione che restituisce una sequenza che contiene solo una parte di ogni elemento selezionato dall'origine dati di query. La query accetta una raccolta di `Customer` oggetti come origine dati e solo progetti i `Name` proprietà nel risultato. Poiché il nome del cliente è una stringa, la query produce una sequenza di stringhe come output.  
  
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
  
1. Il tipo degli elementi nell'origine dati, `customers`, è il tipo della variabile di intervallo, `cust`, nella query. In questo esempio, il tipo è `Customer`.  
  
2. Il `Select` istruzione restituisce il `Name` proprietà di ciascuno `Customer` oggetto anziché l'intero oggetto. In quanto `Name` è una stringa, la variabile di query `custNames`, anche in questo caso sarà IEnumerable (Of String), non di `Customer`.  
  
3. In quanto `custNames` rappresenta una sequenza di stringhe, il `For Each` variabile di iterazione del ciclo, `custName`, deve essere una stringa.  
  
 Senza l'inferenza del tipo locale, nell'esempio precedente sarebbe più complicata da scrivere e capire, come illustrato nell'esempio seguente.  
  
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
  
## <a name="queries-that-require-anonymous-types"></a>Query che richiedono i tipi anonimi  
 L'esempio seguente illustra una situazione più complessa. Nell'esempio precedente, non era utile specificare tipi per tutte le variabili in modo esplicito. In questo esempio, è impossibile. Invece di selezionare l'intera `Customer` gli elementi dall'origine dati o un singolo campo da ogni elemento, il `Select` clausola in questa query restituisce due proprietà dell'originale `Customer` oggetto: `Name` e `City`. In risposta al `Select` clausola, il compilatore definisce un tipo anonimo che contiene queste due proprietà. Il risultato dell'esecuzione `nameCityQuery` nella `For Each` ciclo è una raccolta di istanze del nuovo tipo anonimo. Poiché il tipo anonimo non dispone di alcun nome utilizzabile, è possibile specificare il tipo di `nameCityQuery` o `custInfo` in modo esplicito. Vale a dire, con un tipo anonimo, non hai alcun nome del tipo da usare al posto di `String` in `IEnumerable(Of String)`. Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
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
  
 Anche se non è possibile specificare i tipi per tutte le variabili nell'esempio precedente, le relazioni rimangono invariati.  
  
1. Il tipo degli elementi nell'origine dati anche in questo caso è il tipo della variabile di intervallo nella query. In questo esempio `cust` è un'istanza di `Customer`.  
  
2. Poiché il `Select` istruzione produce un tipo anonimo, la variabile di query, `nameCityQuery`, deve essere tipizzata in modo implicito come un tipo anonimo. Un tipo anonimo non ha alcun nome utilizzabile e pertanto non è possibile specificare in modo esplicito.  
  
3. Il tipo della variabile di iterazione nel `For Each` ciclo è di tipo anonimo creato nel passaggio 2. Poiché il tipo ha un nome utilizzabile, il tipo della variabile di iterazione del ciclo deve essere determinato in modo implicito.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
