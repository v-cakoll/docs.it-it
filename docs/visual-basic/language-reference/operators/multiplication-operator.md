---
title: '* Operatore'
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
ms.openlocfilehash: f1a7653fb3006ab3c9736ec168a8c5ea028f4763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409319"
---
# <a name="-operator-visual-basic"></a>Operatore * (Visual Basic)
Moltiplica due numeri.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`number1`|Obbligatorio. Qualsiasi espressione numerica.|  
|`number2`|Obbligatorio. Qualsiasi espressione numerica.|  
  
## <a name="result"></a>Risultato  
 Il risultato è il prodotto di `number1` e `number2` .  
  
## <a name="supported-types"></a>Tipi supportati  
 Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal` .  
  
## <a name="remarks"></a>Commenti  
 Il tipo di dati del risultato dipende dai tipi degli operandi. Nella tabella seguente viene illustrato il modo in cui viene determinato il tipo di dati del risultato.  
  
|Tipi di dati degli operandi|Tipo di dati result|  
|---|---|  
|Entrambe le espressioni sono tipi di dati integrali ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULONG](../data-types/ulong-data-type.md))|Tipo di dati numerico appropriato per i tipi di dati di `number1` e `number2` . Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).|  
|Entrambe le espressioni sono [decimali](../data-types/decimal-data-type.md)|`Decimal`|  
|Entrambe le espressioni sono [singole](../data-types/single-data-type.md)|`Single`|  
|Expression è un tipo di dati a virgola mobile ( `Single` o [Double](../data-types/double-data-type.md)), ma non entrambi `Single` (Nota `Decimal` non è un tipo di dati a virgola mobile)|`Double`|  
  
 Se un'espressione restituisce [Nothing](../nothing.md), viene considerata come zero.  
  
## <a name="overloading"></a>Overload  
 L' `*` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato l' `*` operatore per moltiplicare due numeri. Il risultato è il prodotto dei due operandi.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore * =](multiplication-assignment-operator.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
