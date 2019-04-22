---
title: Tipi di dati dei risultati degli operatori (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: 45dcc80ee791da1c2731ba32f0ebd34564faf806
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814983"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipi di dati dei risultati degli operatori (Visual Basic)
Visual Basic determina il tipo di dati del risultato di un'operazione in base ai tipi di dati degli operandi. In alcuni casi potrebbe trattarsi di un tipo di dati con un intervallo maggiore rispetto a quello degli operandi.  
  
## <a name="data-type-ranges"></a>Intervalli dei tipi di dati  
 Gli intervalli dei tipi di dati rilevanti, in ordine dal più piccolo al più grande, sono i seguenti:  
  
-   [Booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) , ovvero due valori possibili  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) : 256 valori integrali possibili  
  
-   [Brevi](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) , ovvero 65.536 (6.5... E + 4) possibili valori integrali  
  
-   [Numero intero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) : 4.294.967.296 (4.2... E + 9) possibili valori integrali  
  
-   [Lungo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) : 18.446.744.073.709.551.615 (1.8... E + 19) possibili valori integrali  
  
-   [Decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -1,5... E + 29 possibili valori integrali, massimi intervallo 7.9... E + 28 (valore assoluto)  
  
-   [Singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) : intervallo massimo 3.4... E + 38 (valore assoluto)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) : intervallo massimo 1.7... E + 308 (valore assoluto)  
  
 Per altre informazioni sui tipi di dati di Visual Basic, vedere [tipi di dati](../../../visual-basic/language-reference/data-types/index.md).  
  
 Se un operando [Nothing](../../../visual-basic/language-reference/nothing.md), gli operatori aritmetici di Visual Basic viene considerano da zero.  
  
## <a name="decimal-arithmetic"></a>Operazioni aritmetiche decimali  
 Si noti che il [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md) non è tipo di dati a virgola mobile né integer.  
  
 Se degli operandi di un' `+`, `–`, `*`, `/`, o `Mod` operazione `Decimal` e l'altro non lo è `Single` o `Double`, Visual Basic si amplia l'altro operando a `Decimal`. L'operazione viene eseguita `Decimal`, e il tipo di dati di risultati è `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmetica a virgola mobile  
 Visual Basic esegue la maggior parte delle operazioni aritmetiche a virgola mobile in [doppie](../../../visual-basic/language-reference/data-types/double-data-type.md), ovvero i dati più efficienti digitare per tali operazioni. Tuttavia, se uno degli operandi è [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) e l'altro No `Double`, Visual Basic esegue l'operazione in `Single`. Converte ogni operando in base alle esigenze per il tipo di dati appropriato prima dell'operazione e il risultato contiene tale tipo di dati.  
  
### <a name="-and--operators"></a>/ e ^ operatori  
 Il `/` operatore è definito solo per il [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md), e [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) i tipi di dati. Visual Basic può ampliarsi nel tipo ogni operando in base alle esigenze per il tipo di dati appropriato prima dell'operazione e il risultato contiene tale tipo di dati.  
  
 La tabella seguente illustra il risultato tipi di dati per il `/` operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati di operando, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Qualsiasi tipo integer|  
|`Decimal`|Decimale|Single|Double|Decimale|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Qualsiasi tipo integer|Decimale|Single|Double|Double|  
  
 Il `^` operatore è definito solo per il `Double` tipo di dati. Visual Basic si amplia in base alle esigenze per ogni operando `Double` prima dell'operazione e il risultato di tipo di dati è sempre `Double`.  
  
## <a name="integer-arithmetic"></a>Calcoli di interi  
 Il tipo di dati del risultato di un'operazione di integer dipende dai tipi dei dati degli operandi. In generale, Visual Basic utilizza i criteri seguenti per determinare il tipo di dati di risultati:  
  
-   Se entrambi gli operandi dell'operatore binario con lo stesso tipo di dati, il risultato contiene tale tipo di dati. È un'eccezione `Boolean`, che è obbligato a `Short`.  
  
-   Se fa parte di un operando non firmato con un operando con segno, il risultato ha un tipo con segno con almeno un più ampio un intervallo come degli operandi.  
  
-   In caso contrario, il risultato ha in genere il più elevato tra i due tipi di dati di operando.  
  
 Si noti che il tipo di dati di risultati potrebbe non essere quello utilizzato per qualsiasi tipo di dati di operando.  
  
> [!NOTE]
>  Il tipo di dati di risultati non è sempre sufficientemente grande da contenere tutti i possibili valori risultanti dall'operazione. Un <xref:System.OverflowException> eccezione può verificarsi se il valore è troppo grande per il tipo di dati di risultati.  
  
### <a name="unary--and--operators"></a>Unari + e -operatori  
 Nella tabella seguente mostra il risultato tipi di dati per i due operatori unari, `+` e `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unario `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimale|  
  
### <a name="-and--operators"></a><\< e >> operatori  
 Nella tabella seguente mostra il risultato tipi di dati per i due operatori di spostamento di bit, `<<` e `>>`. Visual Basic ogni operatore di spostamento di bit viene considerato come un operatore unario sul relativo operando sinistro (lo schema di bit da spostare).  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando sinistro è `Decimal`, `Single`, `Double`, o `String`, tenta di convertirlo in Visual Basic `Long` prima dell'operazione e il risultato è di tipo di dati `Long`. L'operando destro (il numero di posizioni di bit da spostare) deve essere `Integer` o un tipo convertibile in `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Binario +, -, * e gli operatori Mod  
 La tabella seguente illustra il risultato tipi di dati per il file binario `+` e `–` operatori e il `*` e `Mod` operatori. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati di operando, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimale|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimale|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimale|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimale|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimale|  
|`ULong`|Decimale|Decimale|ULong|Decimale|ULong|Decimale|ULong|Decimale|ULong|  
  
### <a name="-operator"></a>Operatore \  
 La tabella seguente illustra il risultato tipi di dati per il `\` operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati di operando, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Se degli operandi del `\` operatore [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md), o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic tenta di convertirlo in [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)prima dell'operazione e il risultato è di tipo di dati `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Confronti di bit per bit e non relazionali  
 Il tipo di dati del risultato di un'operazione relazionale (`=`, `<>`, `<`, `>`, `<=`, `>=`) è sempre `Boolean` [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo stesso vale per le operazioni logiche (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`) in `Boolean` operandi.  
  
 Il tipo di dati del risultato di un'operazione logica OR bit per bit dipende dai tipi dei dati degli operandi. Si noti che `AndAlso` e `OrElse` sono definiti solo per `Boolean`, e Visual Basic converte ogni operando in base alle esigenze per `Boolean` prima di eseguire l'operazione.  
  
### <a name="-----and--operators"></a>=, <> \<, >, \<= e > = operatori  
 Se sono entrambi gli operandi `Boolean`, Visual Basic viene considerato `True` sia inferiore a `False`. Se un tipo numerico viene confrontato con un `String`, Visual Basic tenta di convertire le `String` a `Double` prima dell'operazione. Oggetto `Char` o `Date` solo con un altro operando dello stesso tipo di dati, è possibile confrontare l'operando. Il tipo di dati del risultato è sempre `Boolean`.  
  
### <a name="bitwise-not-operator"></a>OR Not (operatore)  
 La tabella seguente illustra il risultato tipi di dati per i bit per bit `Not` operatore.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Booleano|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando è `Decimal`, `Single`, `Double`, o `String`, tenta di convertirlo in Visual Basic `Long` prima dell'operazione e il risultato è di tipo di dati `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>OR bit per bit e, in alternativa e gli operatori di Xor  
 La tabella seguente illustra il risultato tipi di dati per i bit per bit `And`, `Or`, e `Xor` operatori. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati di operando, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Booleano|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Se è un operando `Decimal`, `Single`, `Double`, o `String`, tenta di convertirlo in Visual Basic `Long` prima dell'operazione e i dati del risultato tipo è lo stesso come se l'operando è già stato `Long`.  
  
## <a name="miscellaneous-operators"></a>Operatori vari  
 Il `&` operatore è definito solo per la concatenazione di `String` operandi. Visual Basic consente di convertire ogni operando in base alle esigenze per `String` prima dell'operazione e il risultato di tipo di dati è sempre `String`. Per quanto riguarda il `&` operatore, tutte le conversioni in `String` sono considerati di ampliamento, anche se `Option Strict` è `On`.  
  
 Il `Is` e `IsNot` operatori richiedono entrambi gli operandi siano di un tipo riferimento. Il `TypeOf`... `Is` espressione richiede il primo operando di un tipo di riferimento e il secondo operando per corrispondere al nome di un tipo di dati. In tutti questi casi i dati del risultato è tipo `Boolean`.  
  
 Il `Like` operatore è definito solo per i criteri di ricerca `String` operandi. Visual Basic tenta di convertire ogni operando in base alle esigenze per `String` prima dell'operazione. Il tipo di dati del risultato è sempre `Boolean`.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori](../../../visual-basic/language-reference/operators/index.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
