---
title: Overload degli operatori (F#)
description: "Informazioni su come eseguire l'overload di operatori aritmetici in una classe o un tipo di record e a livello globale in F #."
ms.date: 05/16/2016
ms.openlocfilehash: fc9b7311aa746fd758930365972a187ffdfff0d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
Nella sintassi precedente, il *simbolo di operatore* è uno dei `+`, `-`, `*`, `/`, `=`e così via. Il *elenco di parametri* specifica gli operandi in ordine appaiono nella sintassi consueto per tale operatore. Il *-corpo del metodo* costruisce il valore risultante.

Overload degli operatori per gli operatori devono essere statici. Operatore di overload per gli operatori unari, ad esempio `+` e `-`, devono includere una tilde (`~`) nel *simbolo di operatore* per indicare che l'operatore unario e non è un operatore binario, come illustrato di dichiarazione seguente.

```fsharp
static member (~-) (v : Vector)
```

Nel codice seguente viene illustrata una classe di vettori con solo due operatori, uno per meno unario e uno per la moltiplicazione per un valore scalare. Nell'esempio, due overload per la moltiplicazione scalare sono necessarie perché l'operatore deve essere utilizzato indipendentemente dall'ordine in cui vengono visualizzati il vettore e un valore scalare.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a>Creazione di nuovi operatori
È possibile eseguire l'overload di tutti gli operatori standard, ma è anche possibile creare nuovi operatori da sequenze di caratteri specifici. Caratteri consentiti sono `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, e `~`. Il `~` carattere ha un significato speciale di rendere unario un operatore e non fa parte della sequenza di caratteri dell'operatore. Non tutti gli operatori possono essere resi unari.

A seconda di utilizzare la sequenza di caratteri esatta, l'operatore avrà un determinato la precedenza e associatività. Associazione possa essere da sinistra verso destra o da destra a sinistra e viene utilizzato ogni volta che operatori dello stesso livello di precedenza vengono visualizzati in sequenza senza parentesi.

Il carattere dell'operatore `.` non influisce sulla precedenza, in modo che, ad esempio, se si desidera definire la propria versione di moltiplicazione che ha la stessa precedenza e associatività come moltiplicazione ordinaria, è possibile creare operatori quali `.*`.

Solo gli operatori `?` e `?<-` può iniziare con `?`.

Una tabella che mostra la precedenza di tutti gli operatori in F # è reperibile [riferimenti per simboli e operatore](symbol-and-operator-reference/index.md).


## <a name="overloaded-operator-names"></a>Nomi degli operatori di overload
Quando il compilatore F # compila un'espressione di operatore, viene generato un metodo che presenta un nome generato dal compilatore per questo operatore. Questo è il nome visualizzato in Microsoft intermedio language (MSIL) per il metodo e nella reflection e IntelliSense. In genere, non è necessario utilizzare questi nomi nel codice F #.

Nella tabella seguente illustra gli operatori standard e i relativi nomi generati.



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
Altre combinazioni di caratteri dell'operatore che non sono elencati di seguito possono essere usati come operatori e hanno nomi composti da concatenando i nomi per i singoli caratteri della tabella seguente. Ad esempio, +! diventa `op_PlusBang`.



|Carattere dell'operatore|nome|
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
*Prefisso* gli operatori devono essere inseriti davanti a un operando o operandi, analogamente a una funzione. *Infisso* gli operatori devono essere racchiuse tra i due operandi.

Solo determinati operatori possono essere utilizzati come gli operatori prefisso. Alcuni operatori sono sempre gli operatori prefisso, altri possono essere infisso o prefisso e il resto è sempre operatori infisso. Gli operatori che iniziano con `!`, ad eccezione di `!=`e l'operatore `~`, o ripetuti sequenze di`~`, sono sempre gli operatori prefisso. Gli operatori `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, e `%%` può essere operatori prefisso o operatori infissi. La versione di prefisso di questi operatori è distinguere dalla versione di infisso aggiungendo un `~` all'inizio di un operatore prefisso quando è definito. Il `~` non viene utilizzato quando si utilizza l'operatore, solo quando è definito.

## <a name="example"></a>Esempio

Il codice seguente viene illustrato l'utilizzo dell'operatore di overload per implementare una frazione di tipo. Una frazione è rappresentata da un numeratore e un denominatore. La funzione `hcf` viene utilizzato per determinare il fattore comune più elevato, viene utilizzato per ridurre le frazioni di secondo.

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
È inoltre possibile definire operatori a livello globale. Il codice seguente definisce un operatore `+?`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

L'output del codice sopra riportato è `12`.

È possibile ridefinire gli operatori aritmetici regolari in questo modo perché le regole di ambito per F # prevedono che gli operatori appena definiti hanno la precedenza sugli operatori incorporati.

La parola chiave `inline` viene spesso usato con gli operatori globali, che spesso sono piccole funzioni che si integrano meglio nel codice chiamante. Apportato operatore funzioni inline consente di utilizzare i parametri di tipo risolti staticamente per produrre codice generico risolto in modo statico. Per ulteriori informazioni, vedere [funzioni Inline](functions/inline-functions.md) e [parametri tipo risolti staticamente](generics/statically-resolved-type-parameters.md).

## <a name="see-also"></a>Vedere anche
[Membri](members/index.md)
