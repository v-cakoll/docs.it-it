---
title: Istruzione Function (Visual Basic)
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
ms.openlocfilehash: dffe67d1c31b0fe7c037839ba0588793a461f276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638057"
---
# <a name="function-statement-visual-basic"></a>Istruzione Function (Visual Basic)

Dichiara il nome, parametri e il codice che definiscono un `Function` procedure.

## <a name="syntax"></a>Sintassi

```
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativo. Visualizzare [elenco attributi](attribute-list.md).

- `accessmodifier`

  Facoltativo. Può essere uno dei seguenti:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Facoltativo. Può essere uno dei seguenti:

  - [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Facoltativo. Visualizzare [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Async`

  Facoltativo. Visualizzare [Async](../../../visual-basic/language-reference/modifiers/async.md).

- `Iterator`

  Facoltativo. Visualizzare [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).

- `name`

  Obbligatorio. Nome della procedura. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `typeparamlist`

  Facoltativo. Elenco di parametri di tipo per una routine generica. Visualizzare [elenco dei tipi](type-list.md).

- `parameterlist`

  Facoltativo. Elenco di nomi delle variabili locali che rappresentano i parametri di questa procedura. Visualizzare [elenco di parametri](parameter-list.md).

- `returntype`

  Obbligatorio se `Option Strict` è `On`. Tipo di dati del valore restituito da questa procedura.

- `Implements`

  Facoltativo. Indica che questa procedura consente di implementare uno o più `Function` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura. Visualizzare [implementa istruzione](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle routine `Function` implementate.

  `implementedprocedure [ , implementedprocedure ... ]`

  Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:

  `interface.definedname`

  |Parte|Descrizione|
  |---|---|
  |`interface`|Obbligatorio. Classe o struttura contenente nome di un'interfaccia implementata da questa procedura.|
  |`definedname`|Obbligatorio. Nome mediante il quale la routine viene definita in `interface`.|

- `Handles`

  Facoltativo. Indica che questa procedura può gestire uno o più eventi specifici. Visualizzare [gestisce](handles-clause.md).

- `eventlist`

  Necessario se si fornisce `Handles`. Elenco di eventi che gestisce questa procedura.

  `eventspecifier [ , eventspecifier ... ]`

  Ogni `eventspecifier` presenta la sintassi e le parti seguenti:

  `eventvariable.event`

  |Parte|Descrizione|
  |---|---|
  |`eventvariable`|Obbligatorio. Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.|
  |`event`|Obbligatorio. Nome dell'evento gestito da questa routine.|

- `statements`

  Facoltativo. Blocco di istruzioni da eseguire all'interno di questa procedura.

- `End Function`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Note

Tutto il codice eseguibile deve essere all'interno di una routine. Ogni procedura, a sua volta, viene dichiarato all'interno di una classe, una struttura o un modulo che viene definito la classe, struttura o modulo che lo contiene.

Per restituire un valore al codice chiamante, usare una `Function` procedure; in caso contrario, utilizzare un `Sub` procedure.

## <a name="defining-a-function"></a>Definizione di una funzione

È possibile definire un `Function` procedure solo a livello di modulo. Pertanto, il contesto della dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

`Function` Per impostazione predefinita le procedure per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso.

Oggetto `Function` routine consente di dichiarare il tipo di dati del valore a cui la stored procedure restituisce. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia. Se non si specifica la `returntype` parametro, la stored procedure restituisce `Object`.

Se questa procedura Usa il `Implements` parola chiave, alla classe o struttura deve anche avere un `Implements` istruzione che segue immediatamente relativo `Class` o `Structure` istruzione. Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`. Tuttavia, il nome mediante il quale definisce un'interfaccia di `Function` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).

> [!NOTE]
> È possibile usare espressioni lambda per definire le espressioni di funzione inline. Per altre informazioni, vedere [un'espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md) e [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

## <a name="returning-from-a-function"></a>Restituzione da una funzione

Quando il `Function` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la routine.

Per restituire un valore da una funzione, è possibile assegnare il valore per il nome della funzione o includerlo in un `Return` istruzione.

Il `Return` istruzione contemporaneamente assegna il valore restituito e termina la funzione, come illustrato nell'esempio seguente.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

L'esempio seguente assegna il valore restituito per il nome della funzione `myFunction` e quindi Usa il `Exit Function` istruzione da restituire.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

Il `Exit Function` e `Return` istruzioni uscire immediatamente da un `Function` procedure. Un numero qualsiasi di `Exit Function` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Function` e `Return` istruzioni.

Se si usa `Exit Function` senza assegnarle un valore per `name`, la procedura restituisce il valore predefinito per il tipo di dati specificato in `returntype`. Se `returntype` non è specificato, viene restituito `Nothing`, ovvero il valore predefinito per `Object`.

## <a name="calling-a-function"></a>Chiamata di una funzione

Si chiama un `Function` procedure utilizzando il nome, seguito dall'elenco di argomenti racchiuso tra parentesi, in un'espressione. Solo se non fornire alcun argomento, è possibile omettere le parentesi. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

Si chiama un `Function` procedure simile a quello di chiamare qualsiasi libreria funzione, ad esempio `Sqrt`, `Cos`, o `ChrW`.

È anche possibile chiamare una funzione usando il `Call` (parola chiave). In tal caso, il valore restituito viene ignorato. Usare il `Call` parola chiave non è consigliata nella maggior parte dei casi. Per altre informazioni, vedere [istruzione Call](call-statement.md).

In alcuni casi, Visual Basic ridispone espressioni aritmetiche per aumentare l'efficienza interno. Per questo motivo, è consigliabile non usare un `Function` procedure in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.

## <a name="async-functions"></a>Funzioni asincrone

Il *Async* funzionalità consente di richiamare le funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.

Se si contrassegna una funzione con il [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella funzione. Quando il controllo raggiunge un' `Await` espressione nel `Async` funzione, il controllo ritorna al chiamante e lo stato di avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, la funzione può riprendere l'esecuzione.

> [!NOTE]
> Un' `Async` routine viene restituito al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine del `Async` procedure, a seconda di quale si verifica per primo.

Un' `Async` funzione può avere un tipo restituito <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un esempio di un' `Async` che presenta un tipo restituito della funzione <xref:System.Threading.Tasks.Task%601> di seguito viene fornito.

Un' `Async` funzione non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.

Oggetto [istruzione Sub](sub-statement.md) può essere contrassegnato anche con il `Async` modificatore. Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore. Un' `Async` `Sub` routine non può essere atteso e il chiamante di un `Async` `Sub` procedure non può intercettare le eccezioni generate dal `Sub` procedure.

Per altre informazioni sulle `Async` funzioni, vedere [programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="iterator-functions"></a>Funzioni di iteratore

Un' *iteratore* funzione esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Funzione un iteratore Usa il [Yield](yield-statement.md) istruzione per restituire ogni elemento uno alla volta. Quando un [Yield](yield-statement.md) viene raggiunta l'istruzione, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.

Chiamare un iteratore dal codice client usando un [For Each... Avanti](for-each-next-statement.md) istruzione.

Il tipo restituito di una funzione di iteratore può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.

Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).

## <a name="example"></a>Esempio

L'esempio seguente usa il `Function` istruzione per dichiarare il nome, parametri e codice che costituiscono il corpo di un `Function` procedure. Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a>Esempio

Nell'esempio seguente richiama la funzione dichiarata nell'esempio precedente.

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a>Esempio

Nell'esempio riportato di seguito `DelayAsync` è un `Async` `Function` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. Di conseguenza la dichiarazione della funzione di `DelayAsync` deve avere un tipo restituito `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione in `DoSomethingAsync` genera un numero intero. Questa situazione è illustrata nella presente informativa: `Dim result As Integer = Await delayTask`.

Il `startButton_Click` procedure è un esempio di un `Async Sub` procedure. In quanto `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato di seguito l'istruzione seguente: `Await DoSomethingAsync()`. Il `startButton_Click` `Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.

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
