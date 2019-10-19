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
ms.openlocfilehash: 7dc0ea1f1b30f5ffb0db8917538adf440c5ef891
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583194"
---
# <a name="sub-statement-visual-basic"></a>Istruzione Sub (Visual Basic)

Dichiara il nome, i parametri e il codice che definiscono una procedura `Sub`.

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

  Parametro facoltativo. Vedere [elenco attributi](attribute-list.md).

- `Partial`

  Parametro facoltativo. Indica la definizione di un metodo parziale. Vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).

- `accessmodifier`

  Parametro facoltativo. Può essere uno dei seguenti:

  - [Public](../modifiers/public.md)

  - [Protected](../modifiers/protected.md)

  - [Friend](../modifiers/friend.md)

  - [Private](../modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `proceduremodifiers`

  Parametro facoltativo. Può essere uno dei seguenti:

  - [Overload](../modifiers/overloads.md)

  - [Overrides](../modifiers/overrides.md)

  - [Overridable](../modifiers/overridable.md)

  - [NotOverridable](../modifiers/notoverridable.md)

  - [MustOverride](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  Parametro facoltativo. Vedere [Shared](../modifiers/shared.md).

- `Shadows`

  Parametro facoltativo. Vedere [Shadows](../modifiers/shadows.md).

- `Async`

  Parametro facoltativo. Vedere [Async](../modifiers/async.md).

- `name`

  Obbligatorio. Nome della procedura. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Per creare una routine del costruttore per una classe, impostare il nome di una routine `Sub` sulla parola chiave `New`. Per altre informazioni, vedere [durata degli oggetti: come creare ed eliminare definitivamente oggetti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

- `typeparamlist`

  Parametro facoltativo. Elenco di parametri di tipo per una routine generica. Vedere [elenco dei tipi](type-list.md).

- `parameterlist`

  Parametro facoltativo. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco di parametri](parameter-list.md).

- `Implements`

  Parametro facoltativo. Indica che questa procedura implementa una o più `Sub` procedure, ognuna definita in un'interfaccia implementata dalla classe o dalla struttura che lo contiene. Vedere [istruzione Implements](implements-statement.md).

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

  Parametro facoltativo. Indica che questa procedura può gestire uno o più eventi specifici. Vedere [handle](handles-clause.md).

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

  Parametro facoltativo. Blocco di istruzioni da eseguire all'interno di questa procedura.

- `End Sub`

  Termina la definizione di questa procedura.

## <a name="remarks"></a>Note

Tutto il codice eseguibile deve trovarsi all'interno di una routine. Usare una procedura `Sub` quando non si vuole restituire un valore al codice chiamante. Utilizzare una procedura `Function` quando si desidera restituire un valore.

## <a name="defining-a-sub-procedure"></a>Definizione di una routine Sub

È possibile definire una procedura di `Sub` solo a livello di modulo. Il contesto di dichiarazione per una routine Sub deve pertanto essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una procedura o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

per impostazione predefinita, `Sub` procedure per l'accesso pubblico. È possibile modificare i livelli di accesso usando i modificatori di accesso.

Se nella routine viene utilizzata la parola chiave `Implements`, la classe o la struttura che lo contiene deve disporre di un'istruzione `Implements` che segue immediatamente il `Class` o l'istruzione `Structure`. L'istruzione `Implements` deve includere ogni interfaccia specificata nel `implementslist`. Tuttavia, il nome con cui un'interfaccia definisce il `Sub` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).

## <a name="returning-from-a-sub-procedure"></a>Restituzione da una routine Sub

Quando una `Sub` procedura restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha chiamato.

Nell'esempio seguente viene illustrato un ritorno da una routine `Sub`.

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

Le istruzioni `Exit Sub` e `Return` generano un'uscita immediata da una procedura di `Sub`. Un numero qualsiasi di istruzioni `Exit Sub` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Sub` e `Return` istruzioni.

## <a name="calling-a-sub-procedure"></a>Chiamata a una procedura secondaria

È possibile chiamare una procedura `Sub` usando il nome della stored procedure in un'istruzione e quindi seguendo tale nome con l'elenco di argomenti racchiuso tra parentesi. È possibile omettere le parentesi solo se non si forniscono argomenti. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.

Una routine `Sub` e una procedura `Function` possono avere parametri ed eseguire una serie di istruzioni. Tuttavia, una routine di `Function` restituisce un valore e non una `Sub` routine. Pertanto, non è possibile utilizzare una stored procedure `Sub` in un'espressione.

È possibile utilizzare la parola chiave `Call` quando si chiama una routine `Sub`, ma tale parola chiave non è consigliata per la maggior parte degli utilizzi. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).

Visual Basic a volte riorganizza le espressioni aritmetiche per aumentare l'efficienza interna. Per questo motivo, se nell'elenco di argomenti sono incluse espressioni che chiamano altre routine, non è necessario presupporre che tali espressioni verranno richiamate in un ordine particolare.

## <a name="async-sub-procedures"></a>Procedure secondarie asincrone

Utilizzando la funzionalità asincrona, è possibile richiamare funzioni asincrone senza utilizzare callback espliciti o suddividere manualmente il codice tra più funzioni o espressioni lambda.

Se si contrassegna una routine con il modificatore [Async](../modifiers/async.md) , è possibile usare l'operatore [await](../../../visual-basic/language-reference/operators/await-operator.md) nella procedura. Quando il controllo raggiunge un'espressione `Await` nella procedura `Async`, il controllo torna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa. Al termine dell'attività, l'esecuzione può riprendere nella procedura.

> [!NOTE]
> Una procedura `Async` restituisce al chiamante quando viene rilevato il primo oggetto atteso che non è ancora completo o viene raggiunta la fine della `Async` routine, a seconda di quale si verifica per primo.

È anche possibile contrassegnare un' [istruzione di funzione](function-statement.md) con il modificatore `Async`. Una funzione `Async` può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un esempio più avanti in questo argomento illustra una funzione `Async` che ha un tipo restituito di <xref:System.Threading.Tasks.Task%601>.

`Async` `Sub` procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore. Non è possibile attendere un `Async` `Sub` routine e il chiamante di una procedura di `Sub` `Async` non può rilevare eccezioni generate dalla procedura `Sub`.

Una `Async` routine non può dichiarare alcun parametro [ByRef](../modifiers/byref.md) .

Per altre informazioni sulle procedure di `Async`, vedere [programmazione asincrona con Async e await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l'istruzione `Sub` per definire il nome, i parametri e il codice che formano il corpo di una routine di `Sub`.

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a>Esempio

Nell'esempio seguente `DelayAsync` è un `Async` `Function` il cui tipo restituito è <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. Pertanto, la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione dell'espressione `Await` in `DoSomethingAsync` produce un Integer, come illustrato nella seguente istruzione: `Dim result As Integer = Await delayTask`.

La procedura `startButton_Click` è un esempio di `Async Sub` routine. Poiché `DoSomethingAsync` è una funzione `Async`, l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nella seguente istruzione: `Await DoSomethingAsync()`. Il `startButton_Click` `Sub` routine deve essere definito con il modificatore di `Async` perché contiene un'espressione `Await`.

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
