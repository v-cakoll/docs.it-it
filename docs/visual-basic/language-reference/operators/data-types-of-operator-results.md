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
ms.openlocfilehash: 3867d433ea5f9a6effe70db0ff4162390fb50b5c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331462"
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
  
 Se uno degli operandi di un'operazione di `+`, `–`, `*`, `/`o `Mod` è `Decimal` e l'altro non è `Single` o `Double`, Visual Basic espande l'altro operando a `Decimal`. Esegue l'operazione in `Decimal`e il tipo di dati del risultato è `Decimal`.  
  
## <a name="floating-point-arithmetic"></a>Aritmetica a virgola mobile  
 Visual Basic esegue la maggior parte delle operazioni aritmetiche a virgola mobile in [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), che rappresenta il tipo di dati più efficiente per tali operazioni. Tuttavia, se un operando è [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) e l'altro non è `Double`, Visual Basic esegue l'operazione in `Single`. Ogni operando viene ampliato in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
### <a name="-and--operators"></a>Operatori/e ^  
 L'operatore `/` viene definito solo per i tipi di dati [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)e [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) . Visual Basic allarga ogni operando in base al tipo di dati appropriato prima dell'operazione e il risultato ha tale tipo di dati.  
  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l'operatore `/`. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|Qualsiasi tipo Integer|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|Qualsiasi tipo Integer|Decimal|Single|Double|Double|  
  
 L'operatore `^` viene definito solo per il tipo di dati `Double`. Visual Basic estende ogni operando in modo che sia necessario `Double` prima dell'operazione e il tipo di dati del risultato sia sempre `Double`.  
  
## <a name="integer-arithmetic"></a>Aritmetica Integer  
 Il tipo di dati del risultato di un'operazione Integer dipende dai tipi di dati degli operandi. In generale, Visual Basic utilizza i criteri seguenti per determinare il tipo di dati del risultato:  
  
- Se entrambi gli operandi di un operatore binario hanno lo stesso tipo di dati, il risultato ha tale tipo di dati. Viene `Boolean`un'eccezione, che è forzato a `Short`.  
  
- Se un operando non firmato partecipa a un operando firmato, il risultato ha un tipo firmato con almeno un valore di grandi dimensioni come operando.  
  
- In caso contrario, il risultato è in genere il più grande dei due tipi di dati dell'operando.  
  
 Si noti che il tipo di dati del risultato potrebbe non corrispondere al tipo di dati dell'operando.  
  
> [!NOTE]
> Il tipo di dati del risultato non è sempre sufficiente per mantenere tutti i valori possibili risultante dall'operazione. È possibile che si verifichi un'eccezione <xref:System.OverflowException> se il valore è troppo grande per il tipo di dati del risultato.  
  
### <a name="unary--and--operators"></a>Operatore unario + e-  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per i due operatori unari, `+` e `–`.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`+` unario|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`–` unario|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### <a name="-and--operators"></a>Operatori <\< e > >  
 La tabella seguente illustra i tipi di dati dei risultati per i due operatori di spostamento di bit, `<<` e `>>`. Visual Basic considera ogni operatore di spostamento di bit come operatore unario sull'operando sinistro, ovvero lo schema di bit da spostare.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando sinistro è `Decimal`, `Single`, `Double`o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è `Long`. L'operando destro (il numero di posizioni di bit da spostare) deve essere `Integer` o un tipo che si allarga a `Integer`.  
  
### <a name="binary----and-mod-operators"></a>Operatori binari +,-, \*e mod  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per gli operatori Binary `+` e `–` e gli operatori `*` e `Mod`. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
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
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l'operatore `\`. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
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
  
 Se uno degli operandi dell'operatore `\` è [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), Visual Basic tenta di convertirlo in [Long](../../../visual-basic/language-reference/data-types/long-data-type.md) prima dell'operazione e il tipo di dati result è `Long`.  
  
## <a name="relational-and-bitwise-comparisons"></a>Confronti relazionali e bit per bit  
 Il tipo di dati del risultato di un'operazione relazionale (`=`, `<>`, `<`, `>`, `<=``>=`) è sempre `Boolean`[tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Lo stesso vale per le operazioni logiche (`And`, `AndAlso`, `Not`, `Or`, `OrElse``Xor`) negli operandi `Boolean`.  
  
 Il tipo di dati del risultato di un'operazione logica bit per bit dipende dai tipi di dati degli operandi. Si noti che `AndAlso` e `OrElse` sono definiti solo per `Boolean`e Visual Basic converte ogni operando come necessario per `Boolean` prima di eseguire l'operazione.  
  
### <a name="-----and--operators"></a>=, < >, \<, >, \<= e > = operatori  
 Se entrambi gli operandi sono `Boolean`, Visual Basic considera `True` inferiore a `False`. Se un tipo numerico viene confrontato con una `String`, Visual Basic tenta di convertire il `String` in `Double` prima dell'operazione. Un operando `Char` o `Date` può essere confrontato solo con un altro operando dello stesso tipo di dati. Il tipo di dati del risultato è sempre `Boolean`.  
  
### <a name="bitwise-not-operator"></a>Operatore NOT bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per l'operatore di `Not` bit per bit.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Booleano|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 Se l'operando è `Decimal`, `Single`, `Double`o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è `Long`.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>Operatori and, or e XOR bit per bit  
 Nella tabella seguente vengono illustrati i tipi di dati dei risultati per gli operatori di `And`, `Or`e `Xor` bit per bit. Si noti che questa tabella è simmetrica. per una determinata combinazione di tipi di dati degli operandi, il tipo di dati del risultato è lo stesso indipendentemente dall'ordine degli operandi.  
  
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
  
 Se un operando è `Decimal`, `Single`, `Double`o `String`, Visual Basic tenta di convertirlo in `Long` prima dell'operazione e il tipo di dati del risultato è identico a quello dell'operando che era già stato `Long`.  
  
## <a name="miscellaneous-operators"></a>Operatori vari  
 L'operatore `&` viene definito solo per la concatenazione di `String` operandi. Visual Basic converte ogni operando come necessario per `String` prima dell'operazione e il tipo di dati del risultato è sempre `String`. Ai fini dell'operatore `&`, tutte le conversioni da `String` vengono considerate più estese, anche se `Option Strict` è `On`.  
  
 Gli operatori `Is` e `IsNot` richiedono che entrambi gli operandi siano di un tipo riferimento. L'espressione `TypeOf`...`Is` richiede che il primo operando sia di un tipo di riferimento e che il secondo operando sia il nome di un tipo di dati. In tutti questi casi il tipo di dati del risultato è `Boolean`.  
  
 L'operatore `Like` viene definito solo per criteri di ricerca di `String` operandi. Visual Basic tenta di convertire ogni operando come necessario per `String` prima dell'operazione. Il tipo di dati del risultato è sempre `Boolean`.  
  
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
