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
ms.openlocfilehash: b0ebdb723df6bdb4f74e1558537c307ddb917f64
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2019
ms.locfileid: "69923280"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipi di dati dei risultati degli operatori (Visual Basic)
Visual Basic determina il tipo di dati del risultato di un'operazione in base ai tipi di dati degli operandi. In alcuni casi potrebbe trattarsi di un tipo di dati con un intervallo maggiore rispetto a quello di uno degli operandi.  
  
## <a name="data-type-ranges"></a>Intervalli dei tipi di dati  
 Gli intervalli dei tipi di dati rilevanti, in ordine dal più piccolo al più grande, sono i seguenti:  
  
- [Booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) : due valori possibili  
  
- [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) -256 possibili valori integrali  
  
- [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) -65.536 (6.5... E + 4) possibili valori integrali  
  
- [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4.294.967.296 (4.2... E + 9) possibili valori integrali  
  
- [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULONG](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18.446.744.073.709.551.615 (1.8... E + 19) possibili valori integrali  
  
- [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) : 1.5... E + 29 possibili valori integrali, intervallo massimo 7.9... E + 28 (valore assoluto)  
  
- [Singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) : intervallo massimo 3.4... E + 38 (valore assoluto)  
  
- [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) : intervallo massimo 1.7... E + 308 (valore assoluto)  
  
 Per ulteriori informazioni sui tipi di dati Visual Basic, vedere [tipi di dati](../../../visual-basic/language-reference/data-types/index.md).  
  
 Se un operando non restituisce [nulla](../../../visual-basic/language-reference/nothing.md), gli operatori aritmetici Visual Basic lo considerano come zero.  
  
## <a name="decimal-arithmetic"></a>Aritmetica decimale  
 Si noti che il tipo di dati [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) non è né a virgola mobile né intero.  
  
 Se uno degli operandi di `+`un' `–`operazione `*`, `/`,, `Mod` o è `Decimal` e l'altro non `Single` è o `Double`, Visual Basic allarga l'altro operando a `Decimal`. Esegue l'operazione in e `Decimal`il tipo di dati del risultato è `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmetica a virgola mobile  
 Visual Basic esegue la maggior parte delle operazioni aritmetiche a virgola mobile in [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), che rappresenta il tipo di dati più efficiente per tali operazioni. Tuttavia, se un operando è [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) e l'altro non `Double`lo è, Visual Basic esegue l' `Single`operazione in. Ogni operando viene ampliato in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
### <a name="-and--operators"></a>Operatori/e ^  
 L' `/` operatore viene definito solo per i tipi di dati [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)e [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) . Visual Basic allarga ogni operando in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
 Nella tabella seguente vengono illustrati i tipi di dati `/` dei risultati per l'operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Qualsiasi tipo Integer|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Qualsiasi tipo Integer|Decimal|Single|Double|Double|  
  
 L' `^` operatore viene definito solo per il `Double` tipo di dati. Visual Basic estende ogni operando in modo che `Double` sia necessario prima dell'operazione e il tipo di dati del `Double`risultato è sempre.  
  
## <a name="integer-arithmetic"></a>Aritmetica Integer  
 Il tipo di dati del risultato di un'operazione Integer dipende dai tipi di dati degli operandi. In generale, Visual Basic utilizza i criteri seguenti per determinare il tipo di dati del risultato:  
  
- Se entrambi gli operandi di un operatore binario hanno lo stesso tipo di dati, il risultato ha tale tipo di dati. Un'eccezione è `Boolean`, che viene forzata a `Short`.  
  
- Se un operando non firmato partecipa a un operando firmato, il risultato ha un tipo firmato con almeno un valore di grandi dimensioni come operando.  
  
- In caso contrario, il risultato è in genere il più grande dei due tipi di dati dell'operando.  
  
 Si noti che il tipo di dati del risultato potrebbe non corrispondere al tipo di dati dell'operando.  
  
> [!NOTE]
> Il tipo di dati del risultato non è sempre sufficiente per mantenere tutti i valori possibili risultante dall'operazione. Se <xref:System.OverflowException> il valore è troppo grande per il tipo di dati del risultato, è possibile che si verifichi un'eccezione.  
  
### <a name="unary--and--operators"></a>Operatore unario + e-  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per i `+` due `–`operatori unari, e.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario`+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|Unario`–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<Operatori > e >  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per i due operatori `<<` di `>>`spostamento di bit, e. Visual Basic considera ogni operatore di spostamento di bit come operatore unario sull'operando sinistro, ovvero lo schema di bit da spostare.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando sinistro `Decimal`è `Single` `Double`,, o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato `Long`è. L'operando destro (il numero di posizioni di bit da spostare) `Integer` deve essere o un tipo che si `Integer`allarga a.  
  
### <a name="binary----and-mod-operators"></a>Operatori binari +,-, * e mod  
 Nella tabella seguente vengono illustrati i tipi di dati dei `+` risultati `–` per gli operatori `*` e `Mod` binari e gli operatori e. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>Operatore \\  
 Nella tabella seguente vengono illustrati i tipi di dati `\` dei risultati per l'operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
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
  
 Se uno degli operandi dell' `\` operatore è [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic tenta di convertirlo in [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) prima dell'operazione e il tipo di dati result è `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Confronti relazionali e bit per bit  
 Il`=`tipo di dati del risultato di un'operazione relazionale ( `<`, `>`, `<=`, `>=`,,) `Boolean`è sempre un `<>` [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo stesso vale per le operazioni logiche (`And` `Not`, `AndAlso`,, `Or`, `OrElse`, `Xor`) `Boolean` negli operandi.  
  
 Il tipo di dati del risultato di un'operazione logica bit per bit dipende dai tipi di dati degli operandi. Si noti `AndAlso` che `OrElse` e sono definiti solo `Boolean`per e Visual Basic converte ogni operando come necessario `Boolean` in prima di eseguire l'operazione.  
  
### <a name="-----and--operators"></a>operatori =, < > \<,, > \<, = e > =  
 Se entrambi gli operandi sono `Boolean`, Visual Basic considera `True` minore di `False`. Se un tipo numerico viene confrontato `String`con un oggetto, Visual Basic tenta `String` di `Double` convertire l'oggetto in prima dell'operazione. Un `Char` operando o `Date` può essere confrontato solo con un altro operando dello stesso tipo di dati. Il tipo di dati del risultato `Boolean`è sempre.  
  
### <a name="bitwise-not-operator"></a>Operatore NOT bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei `Not` risultati per l'operatore bit per bit.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando `Decimal`è `Single` `Double`,, o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato `Long`è.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operatori and, or e XOR bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei `And`risultati `Or`per gli `Xor` operatori, e bit per bit. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 Se un operando `Decimal`è `Single` `Double`,, o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è identico a quello dell'operando che `Long`era già stato.  
  
## <a name="miscellaneous-operators"></a>Operatori vari  
 L' `&` operatore viene definito solo per la concatenazione degli `String` operandi. Visual Basic converte ogni operando in modo `String` necessario prima dell'operazione e il tipo di dati del risultato `String`è sempre. `&` Per gli scopi dell'operatore, tutte le conversioni a `String` vengono considerate più larghe, anche se `Option Strict` è `On`.  
  
 Gli `Is` operatori `IsNot` e richiedono che entrambi gli operandi siano di un tipo riferimento. `TypeOf`... `Is` l'espressione richiede che il primo operando sia di un tipo di riferimento e che il secondo operando sia il nome di un tipo di dati. In tutti questi casi il tipo di dati del `Boolean`risultato è.  
  
 L' `Like` operatore viene definito solo per i criteri di `String` ricerca degli operandi. Visual Basic tenta di convertire ogni operando in modo `String` necessario prima dell'operazione. Il tipo di dati del risultato `Boolean`è sempre.  
  
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
