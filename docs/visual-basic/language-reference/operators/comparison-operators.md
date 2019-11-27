---
title: Operatori di confronto
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: ea7604626ede66da818e4bc22fe4922bc752dc2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336077"
---
# <a name="comparison-operators-visual-basic"></a>Operatori di confronto (Visual Basic)
Di seguito sono riportati gli operatori di confronto definiti in Visual Basic.

 operatore `<`

 operatore `<=`

 operatore `>`

 operatore `>=`

 operatore `=`

 operatore `<>`

 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)

 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [Operatore Like](../../../visual-basic/language-reference/operators/like-operator.md)

 Questi operatori confrontano due espressioni per determinare se sono uguali e, in caso contrario, come si differenziano. `Is`, `IsNot`e `Like` sono descritte in dettaglio nelle pagine della guida separate. Gli operatori di confronto relazionali vengono descritti in dettaglio in questa pagina.

## <a name="syntax"></a>Sintassi
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Parti
 `result`  
 Obbligatoria. Valore `Boolean` che rappresenta il risultato del confronto.

 `expression1`, `expression2`  
 Obbligatoria. In qualsiasi espressione.

 `comparisonoperator`  
 Obbligatoria. Qualsiasi operatore di confronto relazionale.

 `object1`, `object2`  
 Obbligatoria. Qualsiasi nome di oggetto di riferimento.

 `string`  
 Obbligatoria. Qualsiasi espressione `String` .

 `pattern`  
 Obbligatoria. Qualsiasi espressione `String` o intervallo di caratteri.

## <a name="remarks"></a>Note
 La tabella seguente contiene un elenco degli operatori di confronto relazionale e le condizioni che determinano se `result` è `True` o `False`.

|Operatore|`True` se|`False` se|
|--------------|---------------|----------------|
|`<` (minore di)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=` (minore o uguale a)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>` (maggiore di)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=` (maggiore o uguale a)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=` (uguale a)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>` (diverso da)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> L' [operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md) viene utilizzato anche come operatore di assegnazione.

 L'operatore `Is`, l'operatore `IsNot` e l'operatore `Like` hanno funzionalità di confronto specifiche che differiscono dagli operatori della tabella precedente.

## <a name="comparing-numbers"></a>Confronto di numeri
 Quando si confronta un'espressione di tipo `Single` a una di tipo `Double`, l'espressione `Single` viene convertita in `Double`. Questo comportamento è opposto al comportamento trovato nella Visual Basic 6.

 Analogamente, quando si confronta un'espressione di tipo `Decimal` a un'espressione di tipo `Single` o `Double`, l'espressione `Decimal` viene convertita in `Single` o `Double`. Per `Decimal` espressioni, qualsiasi valore frazionario minore di 1E-28 potrebbe andare perduto. Tale perdita di valori frazionari può causare il confronto di due valori come uguali quando non lo sono. Per questo motivo, è necessario prestare attenzione quando si utilizza l'uguaglianza (`=`) per confrontare due variabili a virgola mobile. È più sicuro verificare se il valore assoluto della differenza tra i due numeri è inferiore a una piccola tolleranza accettabile.

### <a name="floating-point-imprecision"></a>Imprecisione a virgola mobile
 Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria. Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' [operatore mod](../../../visual-basic/language-reference/operators/mod-operator.md). Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.

## <a name="comparing-strings"></a>Confronto di stringhe
 Quando si confrontano le stringhe, le espressioni stringa vengono valutate in base al relativo ordinamento alfabetico, che dipende dall'impostazione del `Option Compare`.

 `Option Compare Binary` basa i confronti tra stringhe in base a un ordinamento derivato dalle rappresentazioni binarie interne dei caratteri. Il tipo di ordinamento è determinato dalla tabella codici. Nell'esempio seguente viene illustrato un tipico ordinamento binario.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text` basa i confronti di stringhe su un ordinamento testuale senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali dell'applicazione. Quando si imposta `Option Compare Text` e si ordinano i caratteri nell'esempio precedente, viene applicato l'ordinamento del testo seguente:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Dipendenza dalle impostazioni locali
 Quando si imposta `Option Compare Text`, il risultato di un confronto tra stringhe può dipendere dalle impostazioni locali in cui l'applicazione è in esecuzione. Due caratteri possono essere paragonati come uguali in un'unica impostazione locale ma non in un'altra. Se si utilizza un confronto tra stringhe per prendere decisioni importanti, ad esempio se si desidera accettare un tentativo di accesso, è necessario ricevere un avviso per la riservatezza delle impostazioni locali. Prendere in considerazione l'impostazione `Option Compare Binary` o la chiamata del <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, che prende in considerazione le impostazioni locali.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Programmazione senza tipo con operatori di confronto relazionali
 L'utilizzo di operatori di confronto relazionali con espressioni `Object` non è consentito in `Option Strict On`. Quando `Option Strict` è `Off`e `expression1` o `expression2` è un'espressione `Object`, i tipi di runtime determinano il modo in cui vengono confrontati. Nella tabella seguente viene illustrata la modalità di confronto delle espressioni e il risultato del confronto, a seconda del tipo di runtime degli operandi.

|Se gli operandi sono|Il confronto è|
|---------------------|-------------------|
|Entrambi `String`|Confronto di ordinamento basato sulle caratteristiche di ordinamento delle stringhe.|
|Entrambi numerici|Oggetti convertiti in `Double`, confronto numerico.|
|Uno numerico e uno `String`|Il `String` viene convertito in un `Double` e viene eseguito un confronto numerico. Se non è possibile convertire il `String` in `Double`, viene generata un'<xref:System.InvalidCastException>.|
|Uno o entrambi sono tipi di riferimento diversi da `String`|Viene generato un tipo <xref:System.InvalidCastException>.|

 I confronti numerici considerano `Nothing` come 0. I confronti tra stringhe considerano `Nothing` come `""` (una stringa vuota).

## <a name="overloading"></a>Overload
 Operatori di confronto relazionale (`<`. è possibile eseguire l' *Overload*di `<=`, `>`, `>=`, `=``<>`), il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa uno di questi operatori in una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

 Si noti che è possibile eseguire l'overload dell' [operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md) solo come operatore di confronto relazionale, non come operatore di assegnazione.

## <a name="example"></a>Esempio
 Nell'esempio seguente vengono illustrati diversi utilizzi degli operatori di confronto relazionali, utilizzati per confrontare le espressioni. Gli operatori di confronto relazionale restituiscono un risultato `Boolean` che indica se l'espressione specificata restituisce `True`. Quando si applicano gli operatori `>` e `<` alle stringhe, il confronto viene eseguito usando il normale ordinamento in ordine alfabetico delle stringhe. Questo ordine può dipendere dalle impostazioni locali. Indica se l'ordinamento fa distinzione tra maiuscole e minuscole o non dipende dall'impostazione [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) .

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 Nell'esempio precedente, il primo confronto restituisce `False` e i confronti rimanenti restituiscono `True`.

## <a name="see-also"></a>Vedere anche

- <xref:System.InvalidCastException>
- [Operatore =](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
