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
ms.openlocfilehash: ed0072eeb44a17201ddab2af6f6a44fd14461029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Relazioni tra i tipi nelle operazioni di query (Visual Basic)
Le variabili utilizzate [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operazioni sono fortemente tipizzate e devono essere compatibili tra loro. Tipizzazione forte viene utilizzata nell'origine dati, nella query stessa e nell'esecuzione della query. Nella figura seguente identifica i termini utilizzati per descrivere un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. Per ulteriori informazioni sulle parti di una query, vedere [operazioni di Query di base (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Query pseudocodice con elementi evidenziati. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Parti di una query LINQ  
  
 Il tipo della variabile di intervallo nella query deve essere compatibile con il tipo degli elementi nell'origine dati. Il tipo della variabile di query deve essere compatibile con l'elemento della sequenza definito nel `Select` clausola. Infine, il tipo degli elementi sequenza anche deve essere compatibile con il tipo della variabile di controllo del ciclo che viene utilizzata la `For Each` istruzione che esegue la query. La tipizzazione forte semplifica l'identificazione degli errori di tipo in fase di compilazione.  
  
 Visual Basic consente la tipizzazione forte facilmente implementando l'inferenza del tipo locale, noto anche come *tipizzazione implicita*. Che funzionalità viene utilizzata nell'esempio precedente, per visualizzare tutti i [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] esempi e documentazione. In Visual Basic, l'inferenza del tipo locale viene eseguita tramite un `Dim` istruzione senza un `As` clausola. Nell'esempio seguente, `city` è fortemente tipizzata come una stringa.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  L'inferenza del tipo locale funziona solo quando `Option Infer` è impostato su `On`. Per ulteriori informazioni, vedere [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Tuttavia, anche se si utilizza l'inferenza del tipo locale in una query, le stesse relazioni di tipo presenti tra le variabili nell'origine dati, la variabile di query e il ciclo di esecuzione di query. È utile avere una conoscenza di base di queste relazioni di tipo durante la scrittura di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query o lavoro con gli esempi e gli esempi di codice nella documentazione.  
  
 Si potrebbe essere necessario specificare un tipo esplicito per una variabile di intervallo che corrisponde al tipo restituito dall'origine dati. È possibile specificare il tipo della variabile di intervallo mediante un `As` clausola. Tuttavia, il risultato un errore se la conversione è un [conversione di restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e `Option Strict` è impostato su `On`. È pertanto consigliabile eseguire la conversione i valori recuperati dall'origine dati. È possibile convertire i valori dall'origine dati per il tipo di variabile di intervallo esplicito utilizzando il <xref:System.Linq.Enumerable.Cast%2A> metodo. È anche possibile eseguire il cast dei valori selezionati nel `Select` clausola per un tipo esplicito è diverso dal tipo della variabile di intervallo. Questi punti vengono illustrati nel codice seguente.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Query che restituiscono gli elementi completi dei dati di origine  
 Nell'esempio seguente un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operazione che restituisce una sequenza di elementi selezionati dall'origine dei dati di query. L'origine, `names`, contiene una matrice di stringhe, e l'output di query è una sequenza contenente stringhe che iniziano con la lettera M.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Equivale al codice seguente, ma è molto più brevi e facili da scrivere. Inferenza dei tipi locali nelle query l'affidabilità è lo stile preferito in Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Le relazioni seguenti disponibili in entrambi gli esempi di codice precedenti, se i tipi sono determinati in modo implicito o esplicito.  
  
1.  Il tipo degli elementi nell'origine dati, `names`, è il tipo della variabile di intervallo, `name`, nella query.  
  
2.  Il tipo di oggetto selezionato, `name`, determina il tipo di variabile di query `mNames`. Qui `name` è una stringa, pertanto la variabile di query è IEnumerable (Of String) in Visual Basic.  
  
3.  La query definita in `mNames` viene eseguita nel `For Each` ciclo. Il ciclo si scorre il risultato dell'esecuzione della query. Poiché `mNames`, quando eseguita, restituisce una sequenza di stringhe, la variabile di iterazione del ciclo, `nm`, è anche una stringa.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Query che restituiscono un campo da elementi selezionati  
 Nell'esempio seguente un [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] operazione che restituisce una sequenza che contiene solo una parte di ogni elemento selezionato dall'origine dati di query. La query accetta una raccolta di `Customer` oggetti come origine dati e proietta solo la `Name` proprietà nel risultato. Poiché il nome del cliente è una stringa, la query produce una sequenza di stringhe come output.  
  
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
  
 Le relazioni tra le variabili sono analoghe a quelle di esempio più semplice.  
  
1.  Il tipo degli elementi nell'origine dati, `customers`, è il tipo della variabile di intervallo, `cust`, nella query. In questo esempio, il tipo è `Customer`.  
  
2.  Il `Select` istruzione restituisce il `Name` proprietà di ogni `Customer` oggetto anziché l'intero oggetto. Poiché `Name` è una stringa, la variabile di query, `custNames`, verrà nuovamente essere IEnumerable (Of String), non di `Customer`.  
  
3.  Poiché `custNames` rappresenta una sequenza di stringhe, il `For Each` variabile di iterazione del ciclo, `custName`, deve essere una stringa.  
  
 Senza l'inferenza del tipo locale, l'esempio precedente sarebbe più complesso per scrivere e per comprendere, come illustrato nell'esempio seguente.  
  
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
 Nell'esempio seguente viene illustrata una situazione più complessa. Nell'esempio precedente, non era utile specificare tipi per tutte le variabili in modo esplicito. In questo esempio, non è possibile. Anziché selezionare l'intera `Customer` elementi dall'origine dei dati, o un singolo campo di ogni elemento, il `Select` clausola in questa query restituisce due proprietà dell'originale `Customer` oggetto: `Name` e `City`. In risposta al `Select` clausola, il compilatore definisce un tipo anonimo che contiene queste due proprietà. Il risultato dell'esecuzione `nameCityQuery` nel `For Each` ciclo è una raccolta di istanze del nuovo tipo anonimo. Poiché il tipo anonimo ha un nome utilizzabile, è possibile specificare il tipo di `nameCityQuery` o `custInfo` in modo esplicito. Ovvero, con un tipo anonimo, è non avere alcun nome di tipo da utilizzare al posto di `String` in `IEnumerable(Of String)`. Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
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
  
 Anche se non è possibile specificare tipi per tutte le variabili nell'esempio precedente, le relazioni rimangono invariati.  
  
1.  Il tipo degli elementi nell'origine dati è nuovamente il tipo della variabile di intervallo nella query. In questo esempio, `cust` è un'istanza di `Customer`.  
  
2.  Poiché il `Select` istruzione produce un tipo anonimo, la variabile di query, `nameCityQuery`, deve essere tipizzata in modo implicito come un tipo anonimo. Un tipo anonimo ha un nome utilizzabile e pertanto non può essere specificato in modo esplicito.  
  
3.  Il tipo della variabile di iterazione nel `For Each` ciclo è il tipo anonimo creato nel passaggio 2. Poiché il tipo ha un nome utilizzabile, il tipo della variabile di iterazione del ciclo deve essere determinato in modo implicito.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Query](../../../../visual-basic/language-reference/queries/queries.md)
