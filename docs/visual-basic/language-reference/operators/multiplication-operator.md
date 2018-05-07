---
title: '* Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 4e2d1000afcf8951e8914335f7b5a278b49f6277
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>Operatore * (Visual Basic)
Moltiplica due numeri.  
  
## <a name="syntax"></a>Sintassi  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`number1`|Obbligatorio. Qualsiasi espressione numerica.|  
|`number2`|Obbligatorio. Qualsiasi espressione numerica.|  
  
## <a name="result"></a>Risultato  
 Il risultato è il prodotto di `number1` e `number2`.  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno a virgola mobile e `Decimal`.  
  
## <a name="remarks"></a>Note  
 Il tipo di dati del risultato dipende dai tipi degli operandi. Nella tabella seguente viene illustrato come il tipo di dati del risultato viene determinato.  
  
|Tipi di dati di operando|Tipi di dati|  
|---|---|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [breve](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [intero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lungo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Dati di tipo numerico appropriato per i tipi di dati di `number1` e `number2`. Vedere le tabelle "Calcoli di interi" in [tipi di dati di risultati di operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Entrambe le espressioni sono [decimale](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Entrambe le espressioni sono [singolo](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Delle espressioni è un tipo di dati a virgola mobile (`Single` o [doppie](../../../visual-basic/language-reference/data-types/double-data-type.md)) ma non entrambi `Single` (Nota `Decimal` non è un tipo di dati a virgola mobile)|`Double`|  
  
 Se un'espressione restituisce [nulla](../../../visual-basic/language-reference/nothing.md), viene considerato pari a zero.  
  
## <a name="overloading"></a>Overload  
 Il `*` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `*` operatore per moltiplicare due numeri. Il risultato è il prodotto dei due operandi.  
  
 [!code-vb[VbVbalrOperators#4](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
