---
title: Istruzione Function
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404628"
---
# <a name="function-statement-visual-basic"></a>Istruzione Function (Visual Basic)

Dichiara il nome, i parametri e il codice che definiscono una `Function` routine.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativa. Vedere [elenco attributi](attribute-list.md).

- `accessmodifier`

  Facoltativa. Può essere uno dei seguenti:

  - [Pubblica](../modifiers/public.md)

  - [Protetto](../modifiers/protected.md)

  - [Amico](../modifiers/friend.md)

  - [Privata](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Privato protetto](../modifiers/private-protected.md)

  Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Facoltativa. Può essere uno dei seguenti:

  - [Overload](../modifiers/overloads.md)

  - [Override](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Facoltativa. Vedere [Shared](../modifiers/shared.md).

- `Shadows`

  Facoltativa. Vedere [Shadows](../modifiers/shadows.md).

- `Async`

  Facoltativa. Vedere [Async](../modifiers/async.md).

- `Iterator`

  Facoltativa. Vedere [iteratore](../modifiers/iterator.md).

- `name`

  Obbligatorio. Nome della procedura. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Facoltativa. Elenco di parametri di tipo per una routine generica. Vedere [elenco dei tipi](type-list.md).

- `parameterlist`

  Facoltativa. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco di parametri](parameter-list.md).

- `returntype`

  Obbligatorio se `Option Strict` è `On` . Tipo di dati del valore restituito da questa procedura.

- `Implements`

  Facoltativa. Indica che questa procedura implementa una o più `Function` procedure, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura. Vedere [istruzione Implements](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle routine `Function` implementate.

  `implementedprocedure [ , implementedprocedure ... ]`

  Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:

  `interface.definedname`

  |Parte|Descrizione|
  |---|---|
  |`interface`|Obbligatorio. Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.|
  |`definedname`|Obbligatorio. Nome mediante il quale la routine viene definita in `interface`.|

- `Handles`

  Facoltativa. Indica che questa procedura può gestire uno o più eventi specifici. Vedere [handle](handles-clause.md).

- `eventlist`

  Necessario se si fornisce `Handles`. Elenco di eventi gestiti da questa procedura.

  `eventspecifier [ , eventspecifier ... ]`

  Ogni `eventspecifier` presenta la sintassi e le parti seguenti:

  `eventvariable.event`

  |Parte|Descrizione|
  |---|---|
  |`eventvariable`|Obbligatorio. Variabile oggetto dichiarata con il tipo di dati della classe o della struttura che genera l'evento.|
  |`event`|Obbligatorio. Nome dell'evento gestito da questa procedura.|

- `statements`

  Facoltativa. Blocco di istruzioni da eseguire all'interno di questa procedura.

- `End Function`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Commenti

Tutto il codice eseguibile deve trovarsi all'interno di una routine. Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, di una struttura o di un modulo a cui viene fatto riferimento come classe, struttura o modulo contenitore.

Per restituire un valore al codice chiamante, utilizzare una `Function` stored procedure; in caso contrario, utilizzare una `Sub` routine.

## <a name="defining-a-function"></a>Definizione di una funzione

È possibile definire una `Function` procedura solo a livello di modulo. Pertanto, il contesto di dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

`Function`per impostazione predefinita, le procedure sono con accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso.

Una `Function` procedura può dichiarare il tipo di dati del valore restituito dalla stored procedure. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia. Se non si specifica il `returntype` parametro, la procedura restituisce `Object` .

Se questa routine usa la `Implements` parola chiave, la classe o la struttura contenitore deve avere anche un' `Implements` istruzione che segue immediatamente la relativa `Class` `Structure` istruzione o. L' `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist` . Tuttavia, il nome con cui un'interfaccia definisce `Function` (in `definedname` ) non deve corrispondere al nome di questa procedura (in `name` ).

> [!NOTE]
> È possibile utilizzare le espressioni lambda per definire espressioni di funzione inline. Per altre informazioni, vedere [espressione di funzione](../operators/function-expression.md) ed [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Restituzione da una funzione

Quando la `Function` procedura viene restituita al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura.

Per restituire un valore da una funzione, è possibile assegnare il valore al nome della funzione o includerlo in un' `Return` istruzione.

L' `Return` istruzione assegna simultaneamente il valore restituito e chiude la funzione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

Nell'esempio seguente viene assegnato il valore restituito al nome della funzione `myFunction` e quindi viene utilizzata l' `Exit Function` istruzione per restituire.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Le `Exit Function` `Return` istruzioni e generano un'uscita immediata da una `Function` routine. Qualsiasi numero di `Exit Function` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Function` `Return` istruzioni e.

Se si utilizza `Exit Function` senza assegnare un valore a `name` , la stored procedure restituisce il valore predefinito per il tipo di dati specificato in `returntype` . Se `returntype` non è specificato, la procedura restituisce `Nothing` , che rappresenta il valore predefinito per `Object` .

## <a name="calling-a-function"></a>Chiamata di una funzione

È possibile chiamare una `Function` stored procedure utilizzando il nome della procedura, seguito dall'elenco di argomenti tra parentesi, in un'espressione. È possibile omettere le parentesi solo se non si forniscono argomenti. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

È possibile chiamare una `Function` stored procedure nello stesso modo in cui si chiama qualsiasi funzione di libreria, ad esempio `Sqrt` , `Cos` o `ChrW` .

È anche possibile chiamare una funzione usando la `Call` parola chiave. In tal caso, il valore restituito viene ignorato. `Call`Nella maggior parte dei casi non è consigliabile usare la parola chiave. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).

Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna. Per questo motivo, non è consigliabile utilizzare una `Function` stored procedure in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.

## <a name="async-functions"></a>Funzioni asincrone

La *funzionalità asincrona consente* di richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.

Se si contrassegna una funzione con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nella funzione. Quando il controllo raggiunge un' `Await` espressione nella `Async` funzione, il controllo torna al chiamante e l'avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa. Al termine dell'attività, l'esecuzione può riprendere nella funzione.

> [!NOTE]
> Una `Async` routine restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine della `Async` procedura, a seconda di quale si verifica per primo.

Una `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> . Di seguito è riportato un esempio di una `Async` funzione con un tipo restituito <xref:System.Threading.Tasks.Task%601> .

Una `Async` funzione non può dichiarare parametri [ByRef](../modifiers/byref.md) .

Un' [istruzione Sub](sub-statement.md) può anche essere contrassegnata con il `Async` modificatore. Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore. Una `Async` `Sub` routine non può essere attesa e il chiamante di una `Async` `Sub` routine non può intercettare le eccezioni generate dalla `Sub` procedura.

Per altre informazioni sulle `Async` funzioni, vedere [programmazione asincrona con Async e await](../../programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Funzioni iteratore

Una funzione *iteratore* esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Una funzione iteratore usa l'istruzione [yield](yield-statement.md) per restituire un elemento alla volta. Quando viene raggiunta un'istruzione [yield](yield-statement.md) , viene memorizzata la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.

È possibile chiamare un iteratore dal codice client usando un [per ogni... Istruzione successiva](for-each-next-statement.md) .

Il tipo restituito di una funzione iteratore può essere <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .

Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l' `Function` istruzione per dichiarare il nome, i parametri e il codice che formano il corpo di una `Function` routine. Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene richiamata la funzione dichiarata nell'esempio precedente.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Esempio

Nell'esempio seguente `DelayAsync` è un oggetto `Async` `Function` che ha un tipo restituito <xref:System.Threading.Tasks.Task%601> . `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. La dichiarazione di funzione di `DelayAsync` deve quindi avere un tipo restituito `Task(Of Integer)` . Poiché il tipo restituito è `Task(Of Integer)` , la valutazione dell' `Await` espressione in `DoSomethingAsync` genera un numero intero. Questa operazione viene illustrata in questa istruzione: `Dim result As Integer = Await delayTask` .

La `startButton_Click` procedura è un esempio di `Async Sub` procedura. Poiché `DoSomethingAsync` è una `Async` funzione, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()` . La `startButton_Click` `Sub` procedura deve essere definita con il `Async` modificatore perché contiene un' `Await` espressione.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](sub-statement.md)
- [Routine Function](../../programming-guide/language-features/procedures/function-procedures.md)
- [Elenco parametri](parameter-list.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Call](call-statement.md)
- [Di](of-clause.md)
- [Matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedura: Usare una classe generica](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Risoluzione dei problemi relativi alle routine](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Espressione di funzione](../operators/function-expression.md)
