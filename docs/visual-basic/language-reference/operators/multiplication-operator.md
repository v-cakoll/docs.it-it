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
ms.openlocfilehash: b5b601c7604cb7ce1afaebc98b2157634a77fda4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701097"
---
# <a name="-operator-visual-basic"></a>Operatore * (Visual Basic)
Moltiplica due numeri.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Parti  
  
|Nome|Definizione|  
|---|---|  
|`number1`|Obbligatorio. Qualsiasi espressione numerica.|  
|`number2`|Obbligatorio. Qualsiasi espressione numerica.|  
  
## <a name="result"></a>Risultato  
 Il risultato è il prodotto di `number1` e `number2`.  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal`.  
  
## <a name="remarks"></a>Note  
 Il tipo di dati del risultato dipende dai tipi degli operandi. Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.  
  
|Tipi di dati degli operandi|Tipo di dati result|  
|---|---|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULONG](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Tipo di dati numerico appropriato per i tipi di dati di `number1` e `number2`. Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Entrambe le espressioni sono [decimali](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Entrambe le espressioni sono [singole](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Entrambe le espressioni sono un tipo di dati a virgola mobile (`Single` o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) ma non entrambe `Single` (Nota `Decimal` non è un tipo di dati a virgola mobile)|`Double`|  
  
 Se un'espressione restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), viene considerata come zero.  
  
## <a name="overloading"></a>Overload  
 L'operatore `*` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato l'operatore `*` per moltiplicare due numeri. Il risultato è il prodotto dei due operandi.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
