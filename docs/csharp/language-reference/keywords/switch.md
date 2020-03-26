---
title: Istruzione switch in C#
ms.date: 04/09/2019
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: 49b3836f17e91ae8de10d68e97fd662aae80d1ff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249318"
---
# <a name="switch-c-reference"></a>switch (Riferimenti per C#)

In questo `switch` articolo viene illustrata la dichiarazione. Per informazioni `switch` sull'espressione (introdotta nella versione 8.0 di C,0), vedere l'articolo sulle [ `switch` espressioni](../operators/switch-expression.md) nella sezione [espressioni e operatori.](../operators/index.md)

`switch`è un'istruzione di selezione che sceglie una singola *sezione switch* da eseguire da un elenco di candidati in base a una corrispondenza di criteri con *l'espressione di corrispondenza.*

[!code-csharp[switch#1](~/samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]

L'istruzione `switch` viene spesso usata come alternativa a un costrutto [if-else](if-else.md) se una singola espressione viene testata in base a tre o più condizioni. Ad esempio, l'istruzione `switch` determina se una variabile di tipo `Color` ha uno dei tre valori:

[!code-csharp[switch#3](~/samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]

È equivalente all'esempio seguente che usa un costrutto `if`-`else`.

[!code-csharp[switch#3a](~/samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]

## <a name="the-match-expression"></a>Espressione di ricerca

L'espressione di ricerca fornisce il valore da confrontare con i modelli nelle etichette `case`. La relativa sintassi è la seguente:

```csharp
   switch (expr)
```

In C# 6 e versioni precedenti l'espressione di ricerca deve essere un'espressione che restituisce un valore dei tipi seguenti:

- un [char](../builtin-types/char.md).
- una [stringa](../builtin-types/reference-types.md).
- un [bool](../builtin-types/bool.md).
- un valore [integrale,](../builtin-types/integral-numeric-types.md) ad esempio un `int` oggetto `long`.
- un valore [di enumerazione.](../builtin-types/enum.md)

A partire da C# 7.0, l'espressione di ricerca può essere qualsiasi espressione non null.

## <a name="the-switch-section"></a>Sezione opzioni

Un'istruzione `switch` include una o più sezioni opzioni. Ogni sezione switch contiene una o più *etichette case* (etichetta case o default) seguite da una o più istruzioni. L'istruzione `switch` può includere al massimo un'etichetta default posizionata in qualsiasi sezione switch. Nell'esempio seguente viene illustrata una semplice istruzione `switch` con tre sezioni switch, contenenti ognuna due istruzioni. La seconda sezione switch contiene le etichette `case 2:` e `case 3:`.

Un'istruzione `switch` può contenere qualsiasi numero di sezioni opzioni e ogni sezione può avere una o più etichette case, come illustrato nell'esempio seguente. Tuttavia, due etichette case non possono contenere la stessa espressione.

[!code-csharp[switch#2](~/samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]

Viene eseguita una sola sezione opzioni in un'istruzione switch. C# non consente di continuare l'esecuzione da una sezione opzioni a quella successiva. Per questo motivo, il codice seguente genera un errore del compilatore, CS0163: "Il controllo non può passare da un'etichetta caso (etichetta\<caso>) a un'altra."

```csharp
switch (caseSwitch)
{
    // The following switch section causes an error.
    case 1:
        Console.WriteLine("Case 1...");
        // Add a break or other jump statement here.
    case 2:
        Console.WriteLine("... and/or Case 2");
        break;
}
```

Questo requisito viene generalmente soddisfatto chiudendo in modo esplicito la sezione opzioni tramite un'istruzione [break](break.md), [goto](goto.md) o [return](return.md). Tuttavia, anche il codice seguente è valido, perché assicura che il controllo del programma non possa passare alla sezione opzioni `default`.

[!code-csharp[switch#4](~/samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]

L'esecuzione dell'elenco di istruzioni nella sezione opzioni con un'etichetta case che corrisponde all'espressione di ricerca inizia con la prima istruzione e continua con l'elenco di istruzioni, in genere fino a raggiungere un'istruzione di salto, ad esempio `break`, `goto case`, `goto label`, `return` o `throw`. A quel punto, il controllo viene trasferito al di fuori dell'istruzione `switch` o in un'altra etichetta case. Un'istruzione `goto`, se usata, deve trasferire il controllo a un'etichetta costante. Questa restrizione è necessaria, perché il tentativo di trasferire il controllo a un'etichetta non costante può avere effetti collaterali indesiderati, come il trasferimento del controllo a una posizione non prevista nel codice o la creazione di un ciclo infinito.

## <a name="case-labels"></a>Etichette case

Ogni etichetta case specifica un criterio da confrontare con l'espressione di ricerca (la variabile `caseSwitch` negli esempi precedenti). Se corrispondono, il controllo viene trasferito alla sezione opzioni che contiene la **prima** etichetta case corrispondente. Se nessun criterio di etichetta case corrisponde all'espressione di ricerca, il controllo viene trasferito alla sezione con etichetta case `default`, se presente. Se non è presente alcun case `default`, non vengono eseguite istruzioni in nessuna sezione opzioni e il controllo viene trasferito al di fuori dell'istruzione `switch`.

Per informazioni sull'istruzione `switch` e sui criteri di ricerca, vedere [Criteri di ricerca con la sezione `switch` istruzione](#pattern).

Poiché C# 6 supporta solo il criterio costante e non consente la ripetizione di valori costanti, le etichette case definiscono valori che si escludono a vicenda e solo un criterio può corrispondere all'espressione di ricerca. Di conseguenza, l'ordine in cui vengono visualizzate le istruzioni `case` non è rilevante.

In C# 7.0, tuttavia, poiché sono supportati altri criteri, le etichette case non devono necessariamente definire valori che si escludono a vicenda e più criteri possono corrispondere all'espressione di ricerca. Dal momento che vengono eseguite solo le istruzioni nella prima sezione opzione che contiene il criterio di corrispondenza, l'ordine in cui ora vengono visualizzate le istruzioni `case` è importante. Se C# rileva una sezione opzioni la cui istruzione o istruzioni case sono equivalenti a o sono subset di istruzioni precedenti, viene generato l'errore del compilatore CS8120: "Lo switch case è già stato gestito da un case precedente."

Nell'esempio seguente viene illustrata un'istruzione `switch` che usa un'ampia gamma di criteri che non si escludono a vicenda. Se si sposta la sezione opzioni `case 0:` in modo che non sia più la prima sezione nell'istruzione `switch`, C# genera un errore del compilatore perché un numero intero il cui valore è uguale a zero è un sottoinsieme di tutti i numeri interi, che corrisponde al criterio definito dall'istruzione `case int val`.

[!code-csharp[switch#5](~/samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]

È possibile correggere il problema ed eliminare l'avviso del compilatore in uno dei due modi seguenti:

- Modificando l'ordine delle sezioni opzioni.

- Usando una [clausola when](#when) nell'etichetta `case`.

## <a name="the-default-case"></a>Case `default`

Il case `default` specifica la sezione opzioni da eseguire se l'espressione di ricerca non corrisponde a nessun'altra etichetta `case`. Se non è presente un case `default` e l'espressione di ricerca non corrisponde a nessun'altra etichetta `case`, il flusso del programma salta l'istruzione `switch`.

Il case `default` può essere visualizzato in qualsiasi ordine nell'istruzione `switch`. Indipendentemente dall'ordine nel codice sorgente, viene sempre valutato per ultimo, dopo la valutazione di tutte le etichette `case`.

## <a name="pattern-matching-with-the-switch-statement"></a><a name="pattern" /> Criteri di ricerca con istruzione `switch`

Ogni istruzione `case` definisce un criterio che, in caso di corrispondenza con l'espressione di ricerca, provoca l'esecuzione della sezione opzioni che la contiene. Tutte le versioni di C# supportano il criterio costante. I criteri rimanenti sono supportati a partire da C# 7.0.

### <a name="constant-pattern"></a>Criterio costante

Il criterio costante verifica se un'espressione di ricerca è uguale a una costante specificata. La relativa sintassi è la seguente:

```csharp
   case constant:
```

dove *costant* è il valore su cui eseguire il test. *constant* può essere una delle espressioni costanti seguenti:

- Un valore letterale `true` [bool:](../builtin-types/bool.md) o `false`.
- Qualsiasi costante [integrale,](../builtin-types/integral-numeric-types.md) ad esempio un `int`oggetto , un `long`, o un `byte`oggetto .
- Il nome di una variabile `const` dichiarata.
- Una costante di enumerazione.
- Un valore letterale [char](../builtin-types/char.md).
- Un valore letterale [string](../builtin-types/reference-types.md).

L'espressione costante viene valutata nel modo seguente:

- Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).

- In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.

Nell'esempio seguente viene usato il modello costante per determinare se una determinata data è un fine settimana, il primo giorno della settimana lavorativa, l'ultimo giorno della settimana o nel mezzo della settimana lavorativa. Viene valutata la proprietà <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> del giorno corrente con i membri dell'enumerazione <xref:System.DayOfWeek>.

[!code-csharp[switch#7](~/samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

L'esempio seguente usa il modello costante per gestire l'input dell'utente in un'applicazione console che simula una macchina per il caffè automatica.

[!code-csharp[switch#6](~/samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]

### <a name="type-pattern"></a>Criterio del tipo

Il criterio del tipo consente la conversione e valutazione concise del tipo. Quando si usa con l'espressione `switch` per eseguire i criteri di ricerca, verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo. La relativa sintassi è la seguente:

```csharp
   case type varname
```

dove *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se la ricerca ha esito positivo. Il tipo in fase di compilazione di *expr* può essere un parametro di tipo generico, a partire da C# 7.1.

L'espressione `case` è `true` se una delle condizioni seguenti è true:

- *expr* è un'istanza dello stesso tipo di *type*.

- *expr* è un'istanza di un tipo che deriva da *type*. In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.

- *expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*. Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione del tipo. Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.

- *expr* è un'istanza di un tipo che implementa l'interfaccia *type*.

Se l'espressione del case è true, *varname* viene assegnata in modo definitivo e ha l'ambito locale esclusivamente all'interno della sezione opzioni.

Si noti che `null` non corrisponde a un tipo. Per associare un `null`, usare l'etichetta `case` seguente:

```csharp
case null:
```

Nell'esempio seguente viene usato il criterio del tipo per fornire informazioni sui vari generi di tipi di raccolta.

[!code-csharp[type-pattern#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

Invece di `object`, si potrebbe creare un metodo generico usando il tipo della raccolta come parametro di tipo, come illustrato nel codice seguente:

[!code-csharp[type-pattern#3](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern3.cs#1)]

La versione generica presenta due differenze rispetto al primo esempio. La prima è che non è possibile usare il case `null`. Non è possibile usare un case costante perché il compilatore non è in grado di convertire un tipo arbitrario `T` in alcun tipo diverso da `object`. Ciò che prima era il case `default` ora esegue il test per un `object` non Null. Questo significa che il case `default` esegue il test solo per `null`.

Senza criteri di ricerca, questo codice potrebbe essere scritto come segue. L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null` o eseguire cast ripetuti.

[!code-csharp[type-pattern2#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><a name="when" /> Istruzione `case` e clausola `when`

A partire da C# 7.0, poiché le istruzioni case non devono escludersi a vicenda, è possibile aggiungere una clausola `when` per specificare una condizione aggiuntiva che deve essere soddisfatta perché l'istruzione case restituisca true. La clausola `when` può essere qualsiasi espressione che restituisce un valore booleano.

Nell'esempio seguente viene definita una classe `Shape` di base, una classe `Rectangle` che deriva da `Shape` e una classe `Square` che deriva da `Rectangle`. L'esempio usa la clausola `when` per assicurarsi che `ShowShapeInfo` consideri un oggetto `Rectangle` a cui è stata assegnata pari lunghezza e larghezza di un elemento `Square`, anche nel caso in cui non sia stata creata un'istanza come oggetto `Square`. Il metodo non tenta di visualizzare informazioni su un oggetto `null` o su una forma la cui area è pari a zero.

[!code-csharp[when-clause#1](~/samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]

Si noti che la clausola `when` dell'esempio che tenta di verificare se un oggetto `Shape` è `null` non viene eseguita. Il criterio del tipo corretto da verificare per un `null` è `case null:`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione relativa all'[istruzione switch](~/_csharplang/spec/statements.md#the-switch-statement) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](index.md)
- [if-else](if-else.md)
- [Criteri di ricerca](../../pattern-matching.md)
