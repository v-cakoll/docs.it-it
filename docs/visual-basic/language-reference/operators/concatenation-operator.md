---
title: '&amp;Operatore (Visual Basic)'
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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968346"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operatore (Visual Basic)
Genera una concatenazione di stringhe di due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Richiesto. Qualsiasi `String` variabile `Object` o.  
  
 `expression1`  
 Richiesto. Qualsiasi espressione con un tipo di dati che si allarga `String`a.  
  
 `expression2`  
 Richiesto. Qualsiasi espressione con un tipo di dati che si allarga `String`a.  
  
## <a name="remarks"></a>Note  
 Se il tipo di dati `expression1` di `expression2` o non `String` è ma si allarga `String`a, viene convertito in `String`. Se uno dei tipi di dati non viene ampliato `String`a, il compilatore genera un errore.  
  
 Il tipo di dati `result` di `String`è. Se una o entrambe le espressioni restituiscono [Nothing](../../../visual-basic/language-reference/nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".  
  
> [!NOTE]
> L' `&` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Il carattere e commerciale (&) può essere usato anche per identificare le variabili `Long`come tipo. Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene `&` usato l'operatore per forzare la concatenazione di stringhe. Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori di concatenazione in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
