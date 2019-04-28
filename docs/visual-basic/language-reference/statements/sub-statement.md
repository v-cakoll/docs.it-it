---
title: Istruzione Sub (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: ab94865f4881b40b38f67eb40d2f9fa2e1982af8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783838"
---
# <a name="sub-statement-visual-basic"></a>Istruzione Sub (Visual Basic)

Dichiara il nome, parametri e il codice che definiscono un `Sub` procedure.

## <a name="syntax"></a>Sintassi

```
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativo. Visualizzare [elenco attributi](attribute-list.md).

- `Partial`

  Facoltativo. Indica la definizione di un metodo parziale. Visualizzare [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Facoltativo. Può essere uno dei seguenti:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Facoltativo. Può essere uno dei seguenti:

  - [Overload](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Facoltativo. Visualizzare [condiviso](../modifiers/shared.md).

- `Shadows`

  Facoltativo. Visualizzare [Shadows](../modifiers/shadows.md).

- `Async`

  Facoltativo. Visualizzare [Async](../modifiers/async.md).

- `name`

  Obbligatorio. Nome della procedura. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave). Per altre informazioni, vedere [durata degli oggetti: Come gli oggetti vengono creati e distrutti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Facoltativo. Elenco di parametri di tipo per una routine generica. Visualizzare [elenco dei tipi](type-list.md).

- `parameterlist`

  Facoltativo. Elenco di nomi delle variabili locali che rappresentano i parametri di questa procedura. Visualizzare [elenco di parametri](parameter-list.md).

- `Implements`

  Facoltativo. Indica che questa procedura consente di implementare uno o più `Sub` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura. Visualizzare [implementa istruzione](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle routine `Sub` implementate.

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

- `End Sub`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Note

Tutto il codice eseguibile deve essere all'interno di una routine. Usare un `Sub` procedure quando non si vuole restituire un valore al codice chiamante. Usare un `Function` procedure quando si vuole restituire un valore.

## <a name="defining-a-sub-procedure"></a>La definizione di una routine Sub

È possibile definire un `Sub` procedure solo a livello di modulo. Il contesto della dichiarazione per una routine sub deve, pertanto, essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

`Sub` Per impostazione predefinita le procedure per l'accesso pubblico. È possibile modificare i livelli di accesso usando i modificatori di accesso.

Se la procedura Usa il `Implements` parola chiave, alla classe o struttura deve avere un `Implements` istruzione che segue immediatamente relativo `Class` o `Structure` istruzione. Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`. Tuttavia, il nome mediante il quale definisce un'interfaccia di `Sub` (in `definedname`) non deve necessariamente corrispondere al nome di questa procedura (in `name`).

## <a name="returning-from-a-sub-procedure"></a>Restituzione da una routine Sub

Quando un `Sub` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.

Nell'esempio seguente viene illustrata la restituzione da una `Sub` procedure.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Il `Exit Sub` e `Return` istruzioni uscire immediatamente da un `Sub` procedure. Un numero qualsiasi di `Exit Sub` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Sub` e `Return` istruzioni.

## <a name="calling-a-sub-procedure"></a>Chiamare una routine Sub

Si chiama un `Sub` procedura usando il nome della routine in un'istruzione e quindi seguire tale nome con il relativo elenco di argomenti racchiuso tra parentesi. Solo se non si fornisce alcun argomento, è possibile omettere le parentesi. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

Oggetto `Sub` procedure e un `Function` procedura può avere parametri ed eseguire una serie di istruzioni. Tuttavia, un `Function` routine restituisce un valore e un `Sub` non di procedura. Pertanto, è possibile utilizzare un `Sub` procedure in un'espressione.

È possibile usare la `Call` parola chiave quando si chiama un `Sub` routine, ma tale parola chiave non è consigliato per la maggior parte degli utilizzi. Per altre informazioni, vedere [istruzione Call](call-statement.md).

In alcuni casi, Visual Basic ridispone espressioni aritmetiche per aumentare l'efficienza interno. Per questo motivo, se all'elenco di argomenti sono incluse le espressioni che chiamano altre procedure, si dovrebbero evitare supposizioni che verranno chiamate tali espressioni in un ordine particolare.

## <a name="async-sub-procedures"></a>Routine Sub Async

Usando la funzionalità Async, è possibile richiamare le funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.

Se si contrassegna una procedura con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella procedura. Quando il controllo raggiunge un' `Await` espressione nel `Async` procedure, il controllo ritorna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, l'esecuzione può riprendere la procedura.

> [!NOTE]
> Un' `Async` routine restituisce al chiamante quando viene rilevato un il primo oggetto atteso che non è ancora completo o alla fine del `Async` procedure viene raggiunta, qualunque si verifichi prima.

È inoltre possibile contrassegnare un [istruzione Function](function-statement.md) con il `Async` modificatore. Un' `Async` funzione può avere un tipo restituito <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un esempio più avanti in questo argomento viene illustrato un `Async` che presenta un tipo restituito della funzione <xref:System.Threading.Tasks.Task%601>.

`Async` `Sub` le procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore. Un' `Async` `Sub` routine non può essere atteso e il chiamante di un `Async` `Sub` procedure non può intercettare le eccezioni che il `Sub` routine genera un'eccezione.

Un' `Async` routine non può dichiarare [ByRef](../modifiers/byref.md) parametri.

Per altre informazioni sulle `Async` procedure, vedere [programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Esempio

L'esempio seguente usa il `Sub` istruzione per definire il nome, parametri e codice che costituiscono il corpo di un `Sub` procedure.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Esempio

Nell'esempio riportato di seguito `DelayAsync` è un `Async` `Function` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. Pertanto, la dichiarazione della funzione di `DelayAsync` deve presentare un tipo restituito di `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione nella `DoSomethingAsync` genera un numero intero, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask`.

Il `startButton_Click` procedure è un esempio di un `Async Sub` procedure. In quanto `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()`. Il `startButton_Click` `Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](implements-statement.md)
- [Istruzione Function](function-statement.md)
- [Elenco dei parametri](parameter-list.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Call](call-statement.md)
- [Of](of-clause.md)
- [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
