---
title: Tipi di dati dei risultati degli operatori
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
ms.openlocfilehash: b80508c5619770da0c7dc78003ff9d4847dd94d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371427"
---
# <a name="data-types-of-operator-results-visual-basic"></a>Tipi di dati dei risultati degli operatori (Visual Basic)
Visual Basic determina il tipo di dati del risultato di un'operazione in base ai tipi di dati degli operandi. In alcuni casi potrebbe trattarsi di un tipo di dati con un intervallo maggiore rispetto a quello di uno degli operandi.  
  
## <a name="data-type-ranges"></a>Intervalli dei tipi di dati  
 Gli intervalli dei tipi di dati rilevanti, in ordine dal più piccolo al più grande, sono i seguenti:  
  
- [Booleano](../data-types/boolean-data-type.md) : due valori possibili  
  
- [SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md) -256 possibili valori integrali  
  
- [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md) -65.536 (6.5... E + 4) possibili valori integrali  
  
- [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md) -4.294.967.296 (4.2... E + 9) possibili valori integrali  
  
- [Long](../data-types/long-data-type.md), [ULONG](../data-types/ulong-data-type.md) -18.446.744.073.709.551.615 (1.8... E + 19) possibili valori integrali  
  
- [Decimal](../data-types/decimal-data-type.md) : 1.5... E + 29 possibili valori integrali, intervallo massimo 7.9... E + 28 (valore assoluto)  
  
- [Singolo](../data-types/single-data-type.md) : intervallo massimo 3.4... E + 38 (valore assoluto)  
  
- [Double](../data-types/double-data-type.md) : intervallo massimo 1.7... E + 308 (valore assoluto)  
  
 Per ulteriori informazioni sui tipi di dati Visual Basic, vedere [tipi di dati](../data-types/index.md).  
  
 Se un operando non restituisce [nulla](../nothing.md), gli operatori aritmetici Visual Basic lo considerano come zero.  
  
## <a name="decimal-arithmetic"></a>Aritmetica decimale  
 Si noti che il tipo di dati [Decimal](../data-types/decimal-data-type.md) non è né a virgola mobile né intero.  
  
 Se uno degli operandi di `+` un' `–` operazione,,, `*` `/` o `Mod` è `Decimal` e l'altro non è `Single` o `Double` , Visual Basic amplia l'altro operando a `Decimal` . Esegue l'operazione in `Decimal` e il tipo di dati del risultato è `Decimal` .  
  
## <a name="floating-point-arithmetic"></a>Aritmetica a virgola mobile  
 Visual Basic esegue la maggior parte delle operazioni aritmetiche a virgola mobile in [Double](../data-types/double-data-type.md), che rappresenta il tipo di dati più efficiente per tali operazioni. Tuttavia, se un operando è [Single](../data-types/single-data-type.md) e l'altro non lo è `Double` , Visual Basic esegue l'operazione in `Single` . Ogni operando viene ampliato in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
### <a name="-and--operators"></a>Operatori/e ^  
 L' `/` operatore viene definito solo per i tipi di dati [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)e [Double](../data-types/double-data-type.md) . Visual Basic allarga ogni operando in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l' `/` operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Qualsiasi tipo Integer|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Qualsiasi tipo Integer|Decimal|Single|Double|Double|  
  
 L' `^` operatore viene definito solo per il `Double` tipo di dati. Visual Basic estende ogni operando in modo che `Double` sia necessario prima dell'operazione e il tipo di dati del risultato è sempre `Double` .  
  
## <a name="integer-arithmetic"></a>Aritmetica Integer  
 Il tipo di dati del risultato di un'operazione Integer dipende dai tipi di dati degli operandi. In generale, Visual Basic utilizza i criteri seguenti per determinare il tipo di dati del risultato:  
  
- Se entrambi gli operandi di un operatore binario hanno lo stesso tipo di dati, il risultato ha tale tipo di dati. Un'eccezione è `Boolean` , che viene forzata a `Short` .  
  
- Se un operando non firmato partecipa a un operando firmato, il risultato ha un tipo firmato con almeno un valore di grandi dimensioni come operando.  
  
- In caso contrario, il risultato è in genere il più grande dei due tipi di dati dell'operando.  
  
 Si noti che il tipo di dati del risultato potrebbe non corrispondere al tipo di dati dell'operando.  
  
> [!NOTE]
> Il tipo di dati del risultato non è sempre sufficiente per mantenere tutti i valori possibili risultante dall'operazione. <xref:System.OverflowException>Se il valore è troppo grande per il tipo di dati del risultato, è possibile che si verifichi un'eccezione.  
  
### <a name="unary--and--operators"></a>Operatore unario + e-  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per i due operatori unari, `+` e `–` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|Unario`+`|Short|SByte|Byte|Short|UShort|Intero|UInteger|long|ULong|  
|Unario`–`|Short|SByte|Short|Short|Intero|Intero|long|long|Decimal|  
  
### <a name="-and--operators"></a><\< and >Operatori di>  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per i due operatori di spostamento di bit, `<<` e `>>` . Visual Basic considera ogni operatore di spostamento di bit come operatore unario sull'operando sinistro, ovvero lo schema di bit da spostare.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Intero|UInteger|long|ULong|  
  
 Se l'operando sinistro è `Decimal` ,, `Single` `Double` o `String` , Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è `Long` . L'operando destro (il numero di posizioni di bit da spostare) deve essere `Integer` o un tipo che si allarga a `Integer` .  
  
### <a name="binary----and-mod-operators"></a>Operatori binari +,-, \* e mod  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per gli operatori e binari e `+` `–` gli `*` `Mod` operatori e. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Intero|Intero|long|long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Intero|Intero|long|long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Intero|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Intero|Intero|long|long|Decimal|  
|`UShort`|Intero|Intero|UShort|Intero|UShort|Intero|UInteger|long|ULong|  
|`Integer`|Intero|Intero|Intero|Intero|Intero|Intero|long|long|Decimal|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>Operatore \\  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l' `\` operatore. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Intero|Intero|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|Intero|Intero|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|Intero|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Intero|Intero|long|long|long|  
|`UShort`|Intero|Intero|UShort|Intero|UShort|Intero|UInteger|long|ULong|  
|`Integer`|Intero|Intero|Intero|Intero|Intero|Intero|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Se uno degli operandi dell' `\` operatore è [Decimal](../data-types/decimal-data-type.md), [Single](../data-types/single-data-type.md)o [Double](../data-types/double-data-type.md), Visual Basic tenta di convertirlo in [Long](../data-types/long-data-type.md) prima dell'operazione e il tipo di dati result è `Long` .  
  
## <a name="relational-and-bitwise-comparisons"></a>Confronti relazionali e bit per bit  
 Il tipo di dati del risultato di un'operazione relazionale ( `=` ,, `<>` `<` , `>` , `<=` , `>=` ) è sempre un `Boolean` [tipo di dati Boolean](../data-types/boolean-data-type.md). Lo stesso vale per le operazioni logiche ( `And` , `AndAlso` , `Not` , `Or` , `OrElse` , `Xor` ) negli `Boolean` operandi.  
  
 Il tipo di dati del risultato di un'operazione logica bit per bit dipende dai tipi di dati degli operandi. Si noti che `AndAlso` e `OrElse` sono definiti solo per `Boolean` e Visual Basic converte ogni operando come necessario in prima di `Boolean` eseguire l'operazione.  
  
### <a name="-----and--operators"></a>Operatori =,  <>, \<, > , \<=, and > =  
 Se entrambi gli operandi sono `Boolean` , Visual Basic considera `True` minore di `False` . Se un tipo numerico viene confrontato con un oggetto `String` , Visual Basic tenta di convertire l'oggetto `String` in `Double` prima dell'operazione. Un `Char` `Date` operando o può essere confrontato solo con un altro operando dello stesso tipo di dati. Il tipo di dati del risultato è sempre `Boolean` .  
  
### <a name="bitwise-not-operator"></a>Operatore NOT bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l'operatore bit per bit `Not` .  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Intero|UInteger|long|ULong|  
  
 Se l'operando è `Decimal` ,, `Single` `Double` o `String` , Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è `Long` .  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operatori and, or e XOR bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per gli `And` operatori, e bit per bit `Or` `Xor` . Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Intero|Intero|long|long|long|  
|`SByte`|SByte|SByte|Short|Short|Intero|Intero|long|long|long|  
|`Byte`|Short|Short|Byte|Short|UShort|Intero|UInteger|long|ULong|  
|`Short`|Short|Short|Short|Short|Intero|Intero|long|long|long|  
|`UShort`|Intero|Intero|UShort|Intero|UShort|Intero|UInteger|long|ULong|  
|`Integer`|Intero|Intero|Intero|Intero|Intero|Intero|long|long|long|  
|`UInteger`|long|long|UInteger|long|UInteger|long|UInteger|long|ULong|  
|`Long`|long|long|long|long|long|long|long|long|long|  
|`ULong`|long|long|ULong|long|ULong|long|ULong|long|ULong|  
  
 Se un operando è `Decimal` ,, `Single` `Double` o `String` , Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è identico a quello dell'operando che era già stato `Long` .  
  
## <a name="miscellaneous-operators"></a>Operatori vari  
 L' `&` operatore viene definito solo per la concatenazione degli `String` operandi. Visual Basic converte ogni operando in modo necessario `String` prima dell'operazione e il tipo di dati del risultato è sempre `String` . Per gli scopi dell' `&` operatore, tutte le conversioni a `String` vengono considerate più larghe, anche se `Option Strict` è `On` .  
  
 Gli `Is` `IsNot` operatori e richiedono che entrambi gli operandi siano di un tipo riferimento. L' `TypeOf` espressione... `Is` richiede che il primo operando sia di un tipo di riferimento e che il secondo operando sia il nome di un tipo di dati. In tutti questi casi il tipo di dati del risultato è `Boolean` .  
  
 L' `Like` operatore viene definito solo per i criteri di ricerca degli `String` operandi. Visual Basic tenta di convertire ogni operando in modo necessario `String` prima dell'operazione. Il tipo di dati del risultato è sempre `Boolean` .  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../data-types/index.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori](index.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori di confronto](comparison-operators.md)
- [Option Strict Statement](../statements/option-strict-statement.md)
