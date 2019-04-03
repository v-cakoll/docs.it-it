---
title: Espressioni lambda (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: c43739e098a91d54d300fa7074d1563da179c0e9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832112"
---
# <a name="lambda-expressions-visual-basic"></a>Espressioni lambda (Visual Basic)
Oggetto *espressione lambda* è una funzione o subroutine senza un nome che può essere usato ovunque un delegato è valido. Le espressioni lambda possono essere funzioni o subroutine e possono essere a riga singola o multilinea. È possibile passare i valori dall'ambito corrente a un'espressione lambda.  
  
> [!NOTE]
>  Il `RemoveHandler` istruzione è un'eccezione. Non è possibile passare un'espressione lambda in per il parametro del delegato `RemoveHandler`.  
  
 Creare le espressioni lambda tramite il `Function` o `Sub` (parola chiave), esattamente come si crea una subroutine o una funzione standard. Tuttavia, le espressioni lambda sono inclusi in un'istruzione.  
  
 Nell'esempio seguente è un'espressione lambda che incrementa il relativo argomento e restituisce il valore. L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe per una funzione.  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 Nell'esempio seguente è un'espressione lambda che scrive un valore nella console. L'esempio illustra sia la sintassi delle espressioni lambda a riga singola e a più righe di una subroutine.  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 Si noti che negli esempi precedenti le espressioni lambda assegnate a un nome di variabile. Ogni volta che si fa riferimento alla variabile, si richiama l'espressione lambda. È anche possibile dichiarare e chiamare un'espressione lambda nello stesso momento, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 Un'espressione lambda può essere restituita come valore di una chiamata di funzione (come illustrato nell'esempio il [contesto](#context) sezione più avanti in questo argomento), o passata come argomento a un parametro che accetta un tipo delegato, come illustrato di seguito esempio.  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda  
 La sintassi di un'espressione lambda è simile a quello di una subroutine o una funzione standard. Le differenze sono i seguenti:  
  
-   Un'espressione lambda non ha un nome.  
  
-   Le espressioni lambda non possono avere modificatori, ad esempio `Overloads` o `Overrides`.  
  
-   Le funzioni lambda a riga singola non utilizzano un `As` clausola per designare il tipo restituito. Al contrario, il tipo viene dedotto dal valore che restituisce il corpo dell'espressione lambda. Ad esempio, se il corpo dell'espressione lambda `cust.City = "London"`, il tipo restituito è `Boolean`.  
  
-   Nelle funzioni lambda su più righe, è possibile specificare un tipo restituito tramite un `As` clausola, oppure omettere la `As` clausola in modo che il tipo restituito è dedotto. Quando la `As` clausola viene omessa per una funzione lambda su più righe, il tipo restituito viene dedotto il tipo dominante da tutti i `Return` istruzioni nella funzione lambda su più righe. Il *tipo dominante* è un tipo univoco in cui tutti gli altri tipi possono ampliarsi. Se non è possibile determinare il tipo univoco, il tipo dominante è il tipo univoco in cui possono restringersi tutti gli altri tipi nella matrice. Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`. In questo caso, se `Option Strict` è impostata su `On`, si verifica un errore del compilatore.  
  
     Ad esempio, se le espressioni fornito per il `Return` istruzione contengono valori di tipo `Integer`, `Long`, e `Double`, la matrice risultante è di tipo `Double`. Entrambe `Integer` e `Long` ampliarsi `Double` e solo `Double`. `Double` è pertanto il tipo dominante. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   Il corpo di una funzione a riga singola deve essere un'espressione che restituisce un valore, non un'istruzione. È presente alcun `Return` istruzione per le funzioni a riga singola. Il valore restituito dalla funzione a riga singola è il valore dell'espressione nel corpo della funzione.  
  
-   Il corpo di una subroutine a riga singola deve essere a riga singola istruzione.  
  
-   Le funzioni a riga singola e le subroutine non includono un' `End Function` o `End Sub` istruzione.  
  
-   È possibile specificare il tipo di dati di un parametro di espressione lambda con la `As` parola chiave o il tipo di dati del parametro può essere dedotto. Tutti i parametri devono avere specificati tipi di dati o tutti devono essere dedotti.  
  
-   `Optional` e `Paramarray` parametri non sono consentiti.  
  
-   I parametri generici non sono consentiti.  
  
## <a name="async-lambdas"></a>Espressioni lambda asincrone  
 È possibile creare con facilità le espressioni lambda e le istruzioni che includono l'elaborazione asincrona usando il [Async](../../../../visual-basic/language-reference/modifiers/async.md) e [operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md) parole chiave. Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 È possibile aggiungere lo stesso gestore eventi usando un'espressione lambda asincrona in un [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Per aggiungere il gestore, aggiungere un modificatore `Async` prima dell'elenco di parametri lambda, come illustrato di seguito.  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 Per altre informazioni su come creare e usare i metodi asincroni, vedere [programmazione asincrona con Async e Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
## <a name="context"></a> Contesto  
 Un'espressione lambda condivide il contesto con l'ambito entro il quale è definito. Include gli stessi diritti di accesso di qualsiasi codice scritto nell'ambito che lo contiene. Ciò include l'accesso a membri variabili, funzioni e subroutine, `Me`e i parametri e variabili locali all'interno dell'ambito contenitore.  
  
 Accesso alle variabili locali e parametri nell'ambito che lo contiene può estendersi oltre la durata di tale ambito. Fino a quando un delegato che fa riferimento a un'espressione lambda non è disponibile per operazioni di garbage collection, accesso alle variabili dell'ambiente originale viene mantenuto. Nell'esempio seguente, variabile `target` è locale rispetto `makeTheGame`, il metodo in cui l'espressione lambda `playTheGame` è definito. Si noti che l'espressione lambda restituita, assegnato a `takeAGuess` nelle `Main`, ha ancora accesso alla variabile locale `target`.  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 L'esempio seguente illustra l'ampia gamma di diritti di accesso dell'espressione lambda annidata. Quando viene eseguita l'espressione lambda restituita da `Main` come `aDel`, accede a questi elementi:  
  
-   Un campo della classe in cui è definito: `aField`  
  
-   Una proprietà della classe in cui è definito: `aProp`  
  
-   Un parametro di metodo `functionWithNestedLambda`, in cui è definito: `level1`  
  
-   Una variabile locale di `functionWithNestedLambda`: `localVar`  
  
-   Un parametro dell'espressione lambda in cui è annidato: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a>La conversione in un tipo delegato  
 Un'espressione lambda può essere convertita in modo implicito in un tipo delegato compatibile. Per informazioni sui requisiti generali per la compatibilità, vedere [conversione di tipo Relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Ad esempio, il codice seguente viene illustrata un'espressione lambda che converte in modo implicito in `Func(Of Integer, Boolean)` o una firma del delegato corrispondente.  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 Esempio di codice seguente illustra un'espressione lambda che converte implicitamente a `Sub(Of Double, String, Double)` o una firma del delegato corrispondente.  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 Quando si assegnano le espressioni lambda in delegati o passarli come argomenti alle procedure, è possibile specificare i nomi dei parametri, ma omettere i tipi di dati, consentire i tipi di ricavare il delegato.  
  
## <a name="examples"></a>Esempi  
  
-   L'esempio seguente definisce un'espressione lambda che restituisce `True` se l'argomento che ammette valori null è stato assegnato un valore, e `False` ha valore `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
-   L'esempio seguente definisce un'espressione lambda che restituisce l'indice dell'ultimo elemento in una matrice.  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Tipi di valori nullable](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Procedura: Passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Procedura: Creare un'espressione Lambda](./how-to-create-a-lambda-expression.md)
- [Conversione di tipo relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
