---
title: Operatore / (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 238c062b2dd0744ba96cf9ba8591c0ef39f81bb3
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592186"
---
# <a name="-operator-visual-basic"></a>Operatore / (Visual Basic)
Divide due numeri e restituisce un risultato a virgola mobile.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a>Parti  
 `expression1`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.  
  
## <a name="result"></a>Risultato  
 Il risultato è il quoziente completo di `expression1` diviso per `expression2`, incluso qualsiasi resto.  
  
 L' [operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente integer, che elimina il resto.  
  
## <a name="remarks"></a>Note  
 Il tipo di dati del risultato dipende dai tipi degli operandi. Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.  
  
|Tipi di dati degli operandi|Tipo di dati result|  
|------------------------|----------------------|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULONG](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Un'espressione è un tipo di dati [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) e l'altra non è un [valore Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Un'espressione è un tipo di dati [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) e l'altra non è una [singola](../../../visual-basic/language-reference/data-types/single-data-type.md) o una [doppia](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Expression è un tipo di dati [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
  
 Prima di eseguire la divisione, le espressioni numeriche integrali vengono ampliate a `Double`. Se il risultato viene assegnato a un tipo di dati integrale, Visual Basic tenta di convertire il risultato da `Double` a tale tipo. Questa operazione può generare un'eccezione se il risultato non rientra in tale tipo. In particolare, vedere "tentativo di divisione per zero" in questa pagina della guida.  
  
 Se `expression1` o`expression2` restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per zero  
 Se `expression2` restituisce zero, l'operatore `/` si comporta in modo diverso per i diversi tipi di dati degli operandi. La tabella seguente illustra i possibili comportamenti.  
  
|Tipi di dati degli operandi|Comportamento se `expression2` è zero|  
|------------------------|---------------------------------------|  
|A virgola mobile (`Single` o `Double`)|Restituisce Infinity (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>) o <xref:System.Double.NaN> (non un numero) se `expression1` è anche zero|  
|`Decimal`|Genera <xref:System.DivideByZeroException>|  
|Integrale (con segno o senza segno)|Il tentativo di conversione nel tipo integrale genera <xref:System.OverflowException> perché i tipi integrali non accettano <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity> o <xref:System.Double.NaN>|  
  
> [!NOTE]
> L'operatore `/` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l'operatore `/` per eseguire la divisione a virgola mobile. Il risultato è il quoziente dei due operandi.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Le espressioni nell'esempio precedente restituiscono i valori 2,5 e 3,333333. Si noti che il risultato è sempre a virgola mobile (`Double`), anche se entrambi gli operandi sono costanti integer.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Tipi di dati dei risultati degli operatori](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
