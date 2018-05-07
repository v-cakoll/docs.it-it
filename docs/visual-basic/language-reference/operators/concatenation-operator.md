---
title: '&amp; Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-visual-basic"></a>&amp; Operatore (Visual Basic)
Genera una concatenazione di due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `String` o `Object` variabile.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si amplia in `String`.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si amplia in `String`.  
  
## <a name="remarks"></a>Note  
 Se il tipo di dati `expression1` o `expression2` non `String` ma si amplia in `String`, viene convertito in `String`. Se uno dei tipi di dati si amplia in `String`, il compilatore genera un errore.  
  
 Il tipo di dati `result` è `String`. Se una o entrambe le espressioni restituiscono [nulla](../../../visual-basic/language-reference/nothing.md) o hanno un valore di <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".  
  
> [!NOTE]
>  Il `&` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Il carattere e commerciale (&) consente inoltre di identificare le variabili di tipo `Long`. Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `&` operatore per forzare la concatenazione di stringhe. Il risultato è un valore stringa che rappresenta la concatenazione ai due operandi stringa.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori di concatenazione in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
