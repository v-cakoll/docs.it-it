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
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345926"
---
# <a name="function-statement-visual-basic"></a>Istruzione Function (Visual Basic)

Dichiara il nome, i parametri e il codice che definiscono una procedura `Function`.

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

  Facoltativa. Può essere uno dei collegamenti seguenti:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Facoltativa. Può essere uno dei collegamenti seguenti:

  - [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Facoltativa. Vedere [Shared](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Facoltativa. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Async`

  Facoltativa. Vedere [Async](../../../visual-basic/language-reference/modifiers/async.md).

- `Iterator`

  Facoltativa. Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Obbligatoria. Nome della procedura. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Facoltativa. Elenco di parametri di tipo per una routine generica. Vedere [elenco dei tipi](type-list.md).

- `parameterlist`

  Facoltativa. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco di parametri](parameter-list.md).

- `returntype`

  Obbligatorio se `Option Strict` è `On`. Tipo di dati del valore restituito da questa procedura.

- `Implements`

  Facoltativa. Indica che questa procedura implementa una o più `Function` procedure, ognuna definita in un'interfaccia implementata dalla classe o dalla struttura che lo contiene. Vedere [istruzione Implements](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle routine `Function` implementate.

  `implementedprocedure [ , implementedprocedure ... ]`

  Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:

  `interface.definedname`

  |Parte|Descrizione|
  |---|---|
  |`interface`|Obbligatoria. Nome di un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura.|
  |`definedname`|Obbligatoria. Nome mediante il quale la routine viene definita in `interface`.|

- `Handles`

  Facoltativa. Indica che questa procedura può gestire uno o più eventi specifici. Vedere [handle](handles-clause.md).

- `eventlist`

  Necessario se si fornisce `Handles`. Elenco di eventi gestiti da questa procedura.

  `eventspecifier [ , eventspecifier ... ]`

  Ogni `eventspecifier` presenta la sintassi e le parti seguenti:

  `eventvariable.event`

  |Parte|Descrizione|
  |---|---|
  |`eventvariable`|Obbligatoria. Variabile oggetto dichiarata con il tipo di dati della classe o della struttura che genera l'evento.|
  |`event`|Obbligatoria. Nome dell'evento gestito da questa procedura.|

- `statements`

  Facoltativa. Blocco di istruzioni da eseguire all'interno di questa procedura.

- `End Function`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Note

Tutto il codice eseguibile deve trovarsi all'interno di una routine. Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, di una struttura o di un modulo a cui viene fatto riferimento come classe, struttura o modulo contenitore.

Per restituire un valore al codice chiamante, utilizzare una procedura `Function`; in caso contrario, utilizzare una procedura `Sub`.

## <a name="defining-a-function"></a>Definizione di una funzione

È possibile definire una procedura di `Function` solo a livello di modulo. Pertanto, il contesto di dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

per impostazione predefinita, `Function` procedure per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso.

Una procedura `Function` può dichiarare il tipo di dati del valore restituito dalla stored procedure. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia. Se non si specifica il parametro `returntype`, la procedura restituisce `Object`.

Se questa routine usa la parola chiave `Implements`, la classe o la struttura contenitore deve avere anche un'istruzione `Implements` che segue immediatamente la `Class` o l'istruzione `Structure`. L'istruzione `Implements` deve includere ogni interfaccia specificata nel `implementslist`. Tuttavia, il nome con cui un'interfaccia definisce il `Function` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).

> [!NOTE]
> È possibile utilizzare le espressioni lambda per definire espressioni di funzione inline. Per altre informazioni, vedere [espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md) ed [espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Restituzione da una funzione

Quando la `Function` procedura restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura.

Per restituire un valore da una funzione, è possibile assegnare il valore al nome della funzione o includerlo in un'istruzione `Return`.

L'istruzione `Return` assegna simultaneamente il valore restituito e chiude la funzione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

Nell'esempio seguente viene assegnato il valore restituito al nome della funzione `myFunction` e quindi viene utilizzata l'istruzione `Exit Function` per restituire.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Le istruzioni `Exit Function` e `Return` generano un'uscita immediata da una procedura di `Function`. Un numero qualsiasi di istruzioni `Exit Function` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Function` e `Return` istruzioni.

Se si utilizza `Exit Function` senza assegnare un valore a `name`, la stored procedure restituisce il valore predefinito per il tipo di dati specificato in `returntype`. Se `returntype` non è specificato, la procedura restituisce `Nothing`, che rappresenta il valore predefinito per `Object`.

## <a name="calling-a-function"></a>Chiamata di una funzione

È possibile chiamare una procedura `Function` usando il nome della stored procedure, seguito dall'elenco di argomenti tra parentesi, in un'espressione. È possibile omettere le parentesi solo se non si forniscono argomenti. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

È possibile chiamare una routine `Function` nello stesso modo in cui si chiama qualsiasi funzione di libreria, ad esempio `Sqrt`, `Cos`o `ChrW`.

È anche possibile chiamare una funzione usando la parola chiave `Call`. In tal caso, il valore restituito viene ignorato. Nella maggior parte dei casi non è consigliabile usare la parola chiave `Call`. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).

Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna. Per questo motivo, non è consigliabile usare una stored procedure `Function` in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.

## <a name="async-functions"></a>Funzioni asincrone

La *funzionalità asincrona consente* di richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.

Se si contrassegna una funzione con il modificatore [Async](../../../visual-basic/language-reference/modifiers/async.md) , è possibile usare l'operatore [await](../../../visual-basic/language-reference/operators/await-operator.md) nella funzione. Quando il controllo raggiunge un'espressione `Await` nella funzione `Async`, il controllo torna al chiamante e l'avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa. Al termine dell'attività, l'esecuzione può riprendere nella funzione.

> [!NOTE]
> Una procedura `Async` restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine della `Async` routine, a seconda di quale si verifica per primo.

Una funzione `Async` può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Di seguito è riportato un esempio di una funzione `Async` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>.

Una funzione `Async` non può dichiarare alcun parametro [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) .

Un' [istruzione Sub](sub-statement.md) può anche essere contrassegnata con il modificatore `Async`. Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore. Non è possibile attendere un `Async` `Sub` routine e il chiamante di una procedura di `Sub` `Async` non può rilevare le eccezioni generate dalla procedura di `Sub`.

Per altre informazioni sulle funzioni di `Async`, vedere [programmazione asincrona con Async e await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Funzioni iteratore

Una funzione *iteratore* esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Una funzione iteratore usa l'istruzione [yield](yield-statement.md) per restituire un elemento alla volta. Quando viene raggiunta un'istruzione [yield](yield-statement.md) , viene memorizzata la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.

È possibile chiamare un iteratore dal codice client usando un [per ogni... Istruzione successiva](for-each-next-statement.md) .

Il tipo restituito di una funzione iteratore può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>.

Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l'istruzione `Function` per dichiarare il nome, i parametri e il codice che formano il corpo di una routine di `Function`. Il modificatore `ParamArray` consente alla funzione di accettare un numero variabile di argomenti.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene richiamata la funzione dichiarata nell'esempio precedente.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Esempio

Nell'esempio seguente `DelayAsync` è un `Async` `Function` il cui tipo restituito è <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. La dichiarazione di funzione di `DelayAsync` deve pertanto avere un tipo restituito di `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione dell'espressione `Await` in `DoSomethingAsync` produce un valore integer. Questa operazione è illustrata in questa istruzione: `Dim result As Integer = Await delayTask`.

La procedura `startButton_Click` è un esempio di `Async Sub` routine. Poiché `DoSomethingAsync` è una funzione `Async`, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nella seguente istruzione: `Await DoSomethingAsync()`. Il `startButton_Click` `Sub` routine deve essere definito con il modificatore di `Async` perché contiene un'espressione `Await`.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Sub](sub-statement.md)
- [Routine Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Elenco dei parametri](parameter-list.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Call](call-statement.md)
- [Of](of-clause.md)
- [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md)
