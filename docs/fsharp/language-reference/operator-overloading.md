---
title: Overload degli operatori
description: Informazioni su come eseguire l'overload di operatori aritmetici in una classe o un tipo di record e a livello globale in F#.
ms.date: 05/16/2016
ms.openlocfilehash: f4b63818cbdc44d214dca6446162ec9a8922f601
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645355"
---
# <a name="operator-overloading"></a>Overload degli operatori

In questo argomento viene descritto come eseguire l'overload di operatori aritmetici in una classe o un tipo di record e a livello globale.

## <a name="syntax"></a>Sintassi

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il *operatore-symbol* è uno dei `+`, `-`, `*`, `/`, `=`e così via. Il *elenco di parametri* specifica gli operandi in ordine vengono visualizzati nella sintassi normale per tale operatore. Il *corpo del metodo* costruisca il valore risulta.

Overload degli operatori per gli operatori devono essere statici. Operatore di overload per gli operatori unari, ad esempio `+` e `-`, deve usare un carattere tilde (`~`) nel *simbolo dell'operatore* per indicare che l'operatore è un operatore unario e non un operatore binario, come illustrato di dichiarazione seguente.

```fsharp
static member (~-) (v : Vector)
```

Nel codice seguente viene illustrata una classe di vettori con solo due operatori, uno per meno unario e uno per la moltiplicazione per un valore scalare. Nell'esempio, due overload per la moltiplicazione scalare sono necessarie perché l'operatore deve funzionare indipendentemente dall'ordine in cui vengono visualizzati il vettore e il valore scalare.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a>Creazione di nuovi operatori

È possibile eseguire l'overload di tutti gli operatori standard, ma è anche possibile creare nuovi operatori all'esterno di sequenze di caratteri specifici. Caratteri consentiti sono `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, e `~`. Il `~` carattere ha un significato speciale di creazione di un operatore unario e non fa parte della sequenza di caratteri dell'operatore. Non tutti gli operatori possono essere resi unario.

A seconda la sequenza di caratteri esatta che è usare l'operatore avrà un determinato la precedenza e associatività degli operatori. Può essere da sinistra verso destra o da destra a sinistra e viene usato ogni volta che gli operatori allo stesso livello di precedenza visualizzati in sequenza senza parentesi associatività degli operatori.

Il carattere di operatore `.` non influisce sulla precedenza, in modo che, ad esempio, se si desidera definire la propria versione di moltiplicazione che ha la stessa precedenza e associatività degli operatori di moltiplicazione ordinaria, è possibile creare operatori quali `.*`.

Solo gli operatori `?` e `?<-` può iniziare con `?`.

Una tabella che mostra la precedenza di tutti gli operatori in F# sono disponibili nel [riferimenti per simboli e operatore](symbol-and-operator-reference/index.md).

## <a name="overloaded-operator-names"></a>Nomi degli operatori di overload

Quando il F# compilatore compila un'espressione di operatore, viene generato un metodo che presenta un nome generato dal compilatore per tale operatore. Si tratta del nome che viene visualizzato il codice Microsoft intermediate language (MSIL) per il metodo, nonché reflection e IntelliSense. Non è in genere necessario usare questi nomi in F# codice.

La tabella seguente illustra gli operatori standard e i relativi nomi generati.

|Operatore|Nome generato|
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

Altre combinazioni di caratteri dell'operatore che non sono elencati di seguito possono essere utilizzati come operatori e hanno nomi composti da concatenando i nomi per i singoli caratteri della tabella seguente. Ad esempio +! diventa `op_PlusBang`.

|Carattere dell'operatore|Nome|
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

## <a name="prefix-and-infix-operators"></a>Prefisso e gli operatori infissi

*Prefisso* gli operatori devono essere inseriti davanti a uno o più operandi, analogamente a una funzione. *Infisso* gli operatori devono essere racchiuse tra i due operandi.

Solo determinati operatori possono essere utilizzati come operatori di prefisso. Alcuni operatori sono sempre gli operatori prefisso, altri possono essere infissi o il prefisso e il resto è sempre operatori infisso. Gli operatori che iniziano con `!`, tranne `!=`e l'operatore `~`, o ripetuti sequenze di`~`, sono sempre gli operatori prefisso. Gli operatori `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, e `%%` può essere operatori prefisso o operatori infissi. Si distingue la versione di questi operatori prefisso dalla versione di infissi aggiungendo un `~` all'inizio di un operatore prefisso quando viene definita. Il `~` non viene usato quando si usa l'operatore, solo quando è definito.

## <a name="example"></a>Esempio

Il codice seguente viene illustrato l'utilizzo dell'operatore di overload per implementare un tipo fraction. Una frazione è rappresentata da un numeratore e del denominatore. La funzione `hcf` viene usato per determinare il fattore comune più elevato, che consente di ridurre le frazioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

**Output:**

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a>Operatori a livello globale

È anche possibile definire operatori a livello globale. Il codice seguente definisce un operatore `+?`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

L'output del codice sopra riportato è `12`.

È possibile ridefinire gli operatori aritmetici regolare in questo modo perché gli ambiti di regole per F# impone che appena definiti gli operatori hanno la precedenza sugli operatori incorporati.

La parola chiave `inline` viene spesso usato con gli operatori globali, che spesso sono piccole funzioni che si integrano meglio nel codice chiamante. Making operatore funzioni inline anche consente loro di lavorare con i parametri di tipo risolti staticamente per generare codice generico risolto staticamente. Per altre informazioni, vedere [funzioni Inline](functions/inline-functions.md) e [staticamente parametri di tipo risolti](generics/statically-resolved-type-parameters.md).

## <a name="see-also"></a>Vedere anche

- [Membri](members/index.md)
