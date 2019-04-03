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
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825066"
---
# <a name="-operator-visual-basic"></a>Operatore / (Visual Basic)
Divide due numeri e restituisce un risultato a virgola mobile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 Il risultato è il quoziente completo del `expression1` diviso per `expression2`, incluso l'eventuale resto.  
  
 Il [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) restituisce il quoziente, interrompendo il resto.  
  
## <a name="remarks"></a>Note  
 Il tipo di dati del risultato dipende dai tipi degli operandi. La tabella seguente illustra come viene determinato il tipo di dati del risultato.  
  
|Tipi di dati di operando|Tipo di dati|  
|------------------------|----------------------|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [breve](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Un'espressione è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) tipo di dati e l'altro non è un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Un'espressione è un [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md) tipo di dati e l'altro non è un [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) o un [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Delle espressioni è una [doppie](../../../visual-basic/language-reference/data-types/double-data-type.md) tipo di dati|`Double`|  
  
 Prima di eseguita la divisione, le espressioni numeriche integrali vengono estesi a `Double`. Se si assegna il risultato a un tipo di dati integrali, Visual Basic tenta di convertire il risultato da `Double` per quel tipo. Ciò può generare un'eccezione se il risultato non rientra in tale tipo. In particolare, vedere "Ha tentato di divisione per Zero" in questa pagina della Guida.  
  
 Se `expression1` oppure `expression2` restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerato come zero.  
  
## <a name="attempted-division-by-zero"></a>Tentativo di divisione per Zero  
 Se `expression2` restituisce zero, il `/` operatore si comporta in modo diverso per i tipi di dati di operando diversi. Nella tabella seguente sono elencati i comportamenti possibili.  
  
|Tipi di dati di operando|Comportamento se `expression2` è uguale a zero|  
|------------------------|---------------------------------------|  
|A virgola mobile (`Single` o `Double`)|Restituisce un numero infinito (<xref:System.Double.PositiveInfinity> oppure <xref:System.Double.NegativeInfinity>), o <xref:System.Double.NaN> (non un numero) se `expression1` anche è zero|  
|`Decimal`|Genera un'eccezione <xref:System.DivideByZeroException>|  
|Integrale (con o senza segno)|Tentativo di riconvertire in genera un'eccezione di tipo integrale <xref:System.OverflowException> perché non possono accettare i tipi integrali <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, o <xref:System.Double.NaN>|  
  
> [!NOTE]
>  Il `/` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `/` operatore per eseguire la divisione a virgola mobile. Il risultato è il quoziente di due operandi.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Le espressioni nell'esempio precedente restituiscono valori di 2,5 e 3,333333. Si noti che il risultato è sempre a virgola mobile (`Double`), anche se entrambi gli operandi sono costanti integer.  
  
## <a name="see-also"></a>Vedere anche

- [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Tipi di dati dei risultati degli operatori](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
