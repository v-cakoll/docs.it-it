---
title: Espressioni lambda
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249669"
---
# <a name="lambda-expressions-visual-basic"></a>Espressioni lambda (Visual Basic)

*Un'espressione lambda* è una funzione o una subroutine senza un nome che può essere utilizzata ovunque sia valido un delegato. Le espressioni lambda possono essere funzioni o subroutine e possono essere a riga singola o su più righe. È possibile passare valori dall'ambito corrente a un'espressione lambda.

> [!NOTE]
> L'istruzione è un'eccezione. `RemoveHandler` Non è possibile passare un'espressione `RemoveHandler`lambda per il parametro delegato di .

Le espressioni lambda vengono `Function` `Sub` create utilizzando la parola chiave o , così come si crea una funzione o una subroutine standard. Tuttavia, le espressioni lambda sono incluse in un'istruzione.

L'esempio seguente è un'espressione lambda che incrementa il relativo argomento e restituisce il valore. L'esempio mostra sia la sintassi dell'espressione lambda a riga singola che a più righe per una funzione.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

L'esempio seguente è un'espressione lambda che scrive un valore nella console. Nell'esempio viene illustrata la sintassi delle espressioni lambda a riga singola e su più righe per una subroutine.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Si noti che negli esempi precedenti le espressioni lambda vengono assegnate a un nome di variabile. Ogni volta che si fa riferimento alla variabile, si richiama l'espressione lambda. È anche possibile dichiarare e richiamare un'espressione lambda contemporaneamente, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Un'espressione lambda può essere restituita come valore di una chiamata di funzione (come illustrato nell'esempio nella sezione [Contesto](#context) più avanti in questo argomento) o passata come argomento a un parametro che accetta un tipo delegato, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Sintassi delle espressioni lambda

La sintassi di un'espressione lambda è simile a quella di una funzione o di una subroutine standard. Le differenze sono le seguenti:

- Un'espressione lambda non ha un nome.

- Le espressioni lambda non possono `Overloads` `Overrides`avere modificatori, ad esempio o .

- Le funzioni lambda a riga `As` singola non usano una clausola per designare il tipo restituito. Al contrario, il tipo viene dedotto dal valore che restituisce il corpo dell'espressione lambda. Ad esempio, se il corpo `cust.City = "London"`dell'espressione lambda `Boolean`è , il tipo restituito è .

- Nelle funzioni lambda su più righe è possibile specificare un tipo restituito usando una `As` clausola oppure omettere la `As` clausola in modo che il tipo restituito venga dedotto. Quando `As` la clausola viene omessa per una funzione lambda su più righe, il `Return` tipo restituito viene dedotto come tipo dominante da tutte le istruzioni nella funzione lambda su più righe. Il *tipo dominante* è un tipo univoco in cui tutti gli altri tipi possono ampliarsi. Se non è possibile determinare questo tipo univoco, il tipo dominante è il tipo univoco a cui tutti gli altri tipi nella matrice possono restringersi. Se nessuno di questi tipi univoci può essere determinato, il tipo dominante è `Object`. In questo caso, `Option Strict` se `On`è impostato su , si verifica un errore del compilatore.

     Se ad esempio le espressioni `Return` fornite all'istruzione `Integer` `Long`contengono `Double`valori di tipo `Double`, , e , la matrice risultante è di tipo . Sia `Integer` `Long` e `Double` ampliare `Double`a e solo . `Double` è pertanto il tipo dominante. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- Il corpo di una funzione a riga singola deve essere un'espressione che restituisce un valore, non un'istruzione. Non esiste `Return` alcuna istruzione per le funzioni a riga singola. Il valore restituito dalla funzione a riga singola è il valore dell'espressione nel corpo della funzione.

- Il corpo di una subroutine a riga singola deve essere un'istruzione a riga singola.

- Le funzioni e le subroutine a `End Function` `End Sub` riga singola non includono un'istruzione o .

- È possibile specificare il tipo di dati `As` di un parametro dell'espressione lambda usando la parola chiave oppure il tipo di dati del parametro può essere dedotto. Tutti i parametri devono avere tipi di dati specificati o tutti devono essere dedotti.

- `Optional`e `Paramarray` parametri non sono consentiti.

- I parametri generici non sono consentiti.

## <a name="async-lambdas"></a>Espressioni lambda asincrone

È possibile creare facilmente espressioni lambda e istruzioni che incorporano l'elaborazione asincrona usando le parole chiave Async e [Await Operator.You](../../../../visual-basic/language-reference/operators/await-operator.md) can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and Await Operator keywords. Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.

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

È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona in [un'istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Per aggiungere il gestore, aggiungere un modificatore `Async` prima dell'elenco di parametri lambda, come illustrato di seguito.

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

Per ulteriori informazioni su come creare e utilizzare metodi asincroni, vedere [Programmazione asincrona con Async e Await](../../../../visual-basic/programming-guide/concepts/async/index.md).

## <a name="context"></a>Context

Un'espressione lambda condivide il contesto con l'ambito all'interno del quale è definita. Ha gli stessi diritti di accesso di qualsiasi codice scritto nell'ambito contenitore. Ciò include l'accesso a variabili `Me`membro, funzioni e sub, e parametri e variabili locali nell'ambito contenitore.

L'accesso alle variabili locali e ai parametri nell'ambito contenitore può estendersi oltre la durata di tale ambito. Finché un delegato che fa riferimento a un'espressione lambda non è disponibile per la procedura di Garbage Collection, l'accesso alle variabili nell'ambiente originale viene mantenuto. Nell'esempio seguente, `target` variabile `makeTheGame`è locale a , `playTheGame` il metodo in cui è definita l'espressione lambda. Si noti che l'espressione `takeAGuess` `Main`lambda restituita, assegnata `target`a in , ha ancora accesso alla variabile locale .

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

Nell'esempio seguente viene illustrata l'ampia gamma di diritti di accesso dell'espressione lambda annidata. Quando l'espressione lambda restituita `Main` `aDel`viene eseguita da come , accede a questi elementi:

- Campo della classe in cui è definito:`aField`

- Proprietà della classe in cui è definita:`aProp`

- Parametro del `functionWithNestedLambda`metodo , in cui è definito:`level1`

- Una variabile `functionWithNestedLambda`locale di :`localVar`

- Parametro dell'espressione lambda in cui è annidato:`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Conversione in un tipo delegatoConverting to a Delegate Type

Un'espressione lambda può essere convertita in modo implicito in un tipo delegato compatibile. Per informazioni sui requisiti generali per la compatibilità, vedere [Conversione di delegati Relaxed](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Ad esempio, nell'esempio di codice seguente viene `Func(Of Integer, Boolean)` illustrata un'espressione lambda che converte in modo implicito o una firma del delegato corrispondente.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

Nell'esempio di codice seguente viene illustrata `Sub(Of Double, String, Double)` un'espressione lambda che converte in modo implicito o una firma del delegato corrispondente.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

Quando si assegnano espressioni lambda ai delegati o le si passa come argomenti alle routine, è possibile specificare i nomi dei parametri ma omettere i relativi tipi di dati, consentendo ai tipi di essere ricavati dal delegato.

## <a name="examples"></a>Esempi

- Nell'esempio seguente viene definita `True` un'espressione lambda che restituisce se `False` all'argomento `Nothing`di tipo valore nullable è assegnato un valore e se il relativo valore è .

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- Nell'esempio seguente viene definita un'espressione lambda che restituisce l'indice dell'ultimo elemento in una matrice.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Tipi di valore nullableNullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Procedura: passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Procedura: creare un'espressione lambda](./how-to-create-a-lambda-expression.md)
- [Conversione di tipo relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
