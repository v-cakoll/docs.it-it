---
title: Istruzione Sub
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
ms.openlocfilehash: e50b79c31c92ac116d6c82bcececba3340894d74
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404174"
---
# <a name="sub-statement-visual-basic"></a>Istruzione Sub (Visual Basic)

Dichiara il nome, i parametri e il codice che definiscono una `Sub` routine.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativa. Vedere [elenco attributi](attribute-list.md).

- `Partial`

  Facoltativa. Indica la definizione di un metodo parziale. Vedere [metodi parziali](../../programming-guide/language-features/procedures/partial-methods.md).

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

- `name`

  Obbligatorio. Nome della procedura. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md). Per creare una routine del costruttore per una classe, impostare il nome di una `Sub` stored procedure sulla `New` parola chiave. Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Facoltativa. Elenco di parametri di tipo per una routine generica. Vedere [elenco dei tipi](type-list.md).

- `parameterlist`

  Facoltativa. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco di parametri](parameter-list.md).

- `Implements`

  Facoltativa. Indica che questa procedura implementa una o più `Sub` procedure, ognuna delle quali è definita in un'interfaccia implementata dalla classe o dalla struttura contenitore di questa procedura. Vedere [istruzione Implements](implements-statement.md).

- `implementslist`

  Necessario se si fornisce `Implements`. Elenco delle routine `Sub` implementate.

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

- `End Sub`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Commenti

Tutto il codice eseguibile deve trovarsi all'interno di una routine. Utilizzare una `Sub` stored procedure quando non si desidera restituire un valore al codice chiamante. Utilizzare una `Function` procedura quando si desidera restituire un valore.

## <a name="defining-a-sub-procedure"></a>Definizione di una routine Sub

È possibile definire una `Sub` procedura solo a livello di modulo. Il contesto di dichiarazione per una routine Sub deve pertanto essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

`Sub`per impostazione predefinita, le procedure sono con accesso pubblico. È possibile modificare i livelli di accesso usando i modificatori di accesso.

Se la routine usa la `Implements` parola chiave, la classe o la struttura contenitore deve avere un' `Implements` istruzione che segue immediatamente la relativa `Class` `Structure` istruzione o. L' `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist` . Tuttavia, il nome con cui un'interfaccia definisce `Sub` (in `definedname` ) non deve corrispondere al nome di questa procedura (in `name` ).

## <a name="returning-from-a-sub-procedure"></a>Restituzione da una routine Sub

Quando una `Sub` procedura viene restituita al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.

Nell'esempio seguente viene illustrato un ritorno da una `Sub` routine.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Le `Exit Sub` `Return` istruzioni e generano un'uscita immediata da una `Sub` routine. Qualsiasi numero di `Exit Sub` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Sub` `Return` istruzioni e.

## <a name="calling-a-sub-procedure"></a>Chiamata a una procedura secondaria

Per chiamare una `Sub` stored procedure, utilizzare il nome della stored procedure in un'istruzione e quindi seguire tale nome con l'elenco di argomenti racchiuso tra parentesi. È possibile omettere le parentesi solo se non si forniscono argomenti. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

Una `Sub` routine e una `Function` procedura possono avere parametri ed eseguire una serie di istruzioni. Tuttavia, una `Function` routine restituisce un valore e una `Sub` procedura non lo è. Pertanto, non è possibile utilizzare una `Sub` stored procedure in un'espressione.

È possibile utilizzare la `Call` parola chiave quando si chiama una `Sub` routine, ma tale parola chiave non è consigliata per la maggior parte degli utilizzi. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).

Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna. Per questo motivo, se nell'elenco di argomenti sono incluse espressioni che chiamano altre routine, non è necessario presupporre che tali espressioni verranno richiamate in un ordine particolare.

## <a name="async-sub-procedures"></a>Procedure secondarie asincrone

Utilizzando la funzionalità asincrona, è possibile richiamare funzioni asincrone senza utilizzare callback espliciti o suddividere manualmente il codice tra più funzioni o espressioni lambda.

Se si contrassegna una routine con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../operators/await-operator.md) nella procedura. Quando il controllo raggiunge un' `Await` espressione nella `Async` routine, il controllo torna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa. Al termine dell'attività, l'esecuzione può riprendere nella procedura.

> [!NOTE]
> Una `Async` routine viene restituita al chiamante quando viene rilevato il primo oggetto atteso che non è ancora completo o viene raggiunta la fine della `Async` procedura, a seconda di quale si verifica per primo.

È anche possibile contrassegnare un' [istruzione di funzione](function-statement.md) con il `Async` modificatore. Una `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> . Un esempio più avanti in questo argomento illustra una `Async` funzione con tipo restituito <xref:System.Threading.Tasks.Task%601> .

`Async``Sub`le stored procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore. Una `Async` `Sub` routine non può essere attesa e il chiamante di una `Async` `Sub` stored procedure non può intercettare le eccezioni `Sub` generate dalla procedura.

Una `Async` routine non può dichiarare parametri [ByRef](../modifiers/byref.md) .

Per altre informazioni sulle `Async` procedure, vedere [programmazione asincrona con Async e await](../../programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l' `Sub` istruzione per definire il nome, i parametri e il codice che formano il corpo di una `Sub` routine.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Esempio

Nell'esempio seguente `DelayAsync` è un oggetto `Async` `Function` che ha un tipo restituito <xref:System.Threading.Tasks.Task%601> . `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. La dichiarazione di funzione di `DelayAsync` deve pertanto avere un tipo restituito di `Task(Of Integer)` . Poiché il tipo restituito è `Task(Of Integer)` , la valutazione dell' `Await` espressione in `DoSomethingAsync` produce un Integer, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask` .

La `startButton_Click` procedura è un esempio di `Async Sub` procedura. Poiché `DoSomethingAsync` è una `Async` funzione, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()` . La `startButton_Click` `Sub` procedura deve essere definita con il `Async` modificatore perché contiene un' `Await` espressione.

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](implements-statement.md)
- [Istruzione Function](function-statement.md)
- [Elenco parametri](parameter-list.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Call](call-statement.md)
- [Di](of-clause.md)
- [Matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [Procedura: Usare una classe generica](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Risoluzione dei problemi relativi alle routine](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [Metodi parziali](../../programming-guide/language-features/procedures/partial-methods.md)
