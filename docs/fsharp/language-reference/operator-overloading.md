---
title: Overload degli operatori
description: Informazioni su come eseguire l'overload di operatori aritmetici in una classe o in un tipo di F#record e a livello globale in.
ms.date: 05/16/2016
ms.openlocfilehash: c656c1c47938e62386c8f063cf9a6caaaf69d0fe
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627396"
---
# <a name="operator-overloading"></a>Overload degli operatori

In questo argomento viene descritto come eseguire l'overload di operatori aritmetici in una classe o in un tipo di record e a livello globale.

## <a name="syntax"></a>Sintassi

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a>Note

Nella sintassi precedente il *simbolo operator* è uno tra `+`, `*` `-`,, `/`, `=`e così via. *Parameter-list* specifica gli operandi nell'ordine in cui sono visualizzati nella sintassi consueta per l'operatore. Il *corpo del metodo* costruisce il valore risultante.

Gli overload degli operatori per gli operatori devono essere statici. Gli overload degli operatori per gli operatori unari, ad `+` esempio `-`e, devono usare una tilde`~`() nel *simbolo operator* per indicare che l'operatore è un operatore unario e non un operatore binario, come illustrato di seguito. Dichiarazione.

```fsharp
static member (~-) (v : Vector)
```

Nel codice seguente viene illustrata una classe di vettori con solo due operatori, uno per meno unario e uno per la moltiplicazione per un valore scalare. Nell'esempio sono necessari due overload per la moltiplicazione scalare perché l'operatore deve funzionare indipendentemente dall'ordine in cui vengono visualizzati il vettore e il valore scalare.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a>Creazione di nuovi operatori

È possibile eseguire l'overload di tutti gli operatori standard, ma è anche possibile creare nuovi operatori dalle sequenze di determinati caratteri. I caratteri di operatore `!`consentiti `*`sono `+` `&`, `%`, `.`, `/`,, `-`,,, `<`, ,`=`, `>` `?` ,`@`, ,`^` e`~`. `|` Il `~` carattere ha il significato speciale di rendere unaria un operatore e non fa parte della sequenza di caratteri dell'operatore. Non tutti gli operatori possono essere resi unari.

A seconda della sequenza di caratteri esatta utilizzata, l'operatore avrà una certa precedenza e associatività. L'associatività può essere da sinistra a destra o da destra a sinistra e viene usata ogni volta che gli operatori con lo stesso livello di precedenza vengono visualizzati in sequenza senza parentesi.

Il carattere `.` dell'operatore non influisce sulla precedenza, quindi, ad esempio, se si desidera definire una versione personalizzata della moltiplicazione con la stessa precedenza e associatività della moltiplicazione ordinaria, è possibile creare operatori come `.*`.

Solo gli operatori `?` e `?<-` possono iniziare con `?`.

Una tabella che mostra la precedenza di tutti gli operatori F# in si trova in [riferimento a simboli e operatori](./symbol-and-operator-reference/index.md).

## <a name="overloaded-operator-names"></a>Nomi degli operatori di overload

Quando il F# compilatore compila un'espressione di operatore, genera un metodo con un nome generato dal compilatore per l'operatore. Si tratta del nome che viene visualizzato nel linguaggio MSIL (Microsoft Intermediate Language) per il metodo e anche in Reflection e IntelliSense. Non è in genere necessario usare questi nomi nel F# codice.

Nella tabella seguente vengono illustrati gli operatori standard e i corrispondenti nomi generati.

|Operator|Nome generato|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

Altre combinazioni di caratteri operatore che non sono elencate di seguito possono essere usate come operatori e hanno nomi costituiti dalla concatenazione di nomi per i singoli caratteri della tabella seguente. Ad esempio, +! diventa `op_PlusBang`.

|Carattere operatore|Name|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a>Operatori prefix e infissi

Si prevede che gli operatori di *prefisso* siano posizionati davanti a un operando o a operandi, molto simile a una funzione. Si prevede che gli operatori infissi siano posizionati tra i due operandi.

Solo determinati operatori possono essere utilizzati come operatori di prefisso. Alcuni operatori sono sempre operatori di prefisso, altri possono essere infissi o prefissi e i restanti sono sempre operatori infissi. Gli operatori che iniziano `!`con, `!=`ad eccezione di e `~`l'operatore, o sequenze ripetute di, sono sempre operatori di`~`prefisso. Gli operatori `+` `-` ,`&` ,,`%%` ,,, e possono essere operatori di prefisso o infissi. `+.` `-.` `&&` `%` È possibile distinguere la versione del prefisso di questi operatori dalla versione infissi aggiungendo `~` un oggetto all'inizio di un operatore di prefisso quando viene definito. L' `~` oggetto non viene utilizzato quando si utilizza l'operatore, solo quando è definito.

## <a name="example"></a>Esempio

Il codice seguente illustra l'uso dell'overload degli operatori per implementare un tipo di frazione. Una frazione viene rappresentata da un numeratore e da un denominatore. La funzione `hcf` viene usata per determinare il fattore comune più elevato, che viene usato per ridurre le frazioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

**Output:**

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a>Operatori a livello globale

È anche possibile definire gli operatori a livello globale. Il codice seguente definisce un operatore `+?`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

L'output del codice precedente è `12`.

È possibile ridefinire gli operatori aritmetici regolari in questo modo perché le regole F# di ambito per stabiliscono che gli operatori appena definiti hanno la precedenza sugli operatori predefiniti.

La parola `inline` chiave viene spesso usata con gli operatori globali, che sono spesso piccole funzioni più integrate nel codice chiamante. La creazione di funzioni operatore inline consente inoltre di utilizzare parametri di tipo risolti staticamente per produrre codice generico risolto in modo statico. Per altre informazioni, vedere [funzioni inline](./functions/inline-functions.md) e [parametri di tipo risolti staticamente](./generics/statically-resolved-type-parameters.md).

## <a name="see-also"></a>Vedere anche

- [Membri](./members/index.md)
