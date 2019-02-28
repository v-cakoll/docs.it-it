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
ms.openlocfilehash: 2237da5d64ada6817d3a9a88b04b76f573bd76c0
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976512"
---
# <a name="amp-operator-visual-basic"></a>&amp; Operatore (Visual Basic)
Genera una concatenazione di due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Eventuali `String` o `Object` variabile.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si amplia in `String`.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si amplia in `String`.  
  
## <a name="remarks"></a>Note  
 Se il tipo di dati `expression1` oppure `expression2` non è `String` ma può ampliarsi nel tipo `String`, viene convertito in `String`. Se uno dei tipi di dati si amplia in `String`, il compilatore genera un errore.  
  
 Il tipo di dati `result` è `String`. Se una o entrambe le espressioni restituiscono [Nothing](../../../visual-basic/language-reference/nothing.md) o avere un valore di <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".  
  
> [!NOTE]
>  Il `&` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Il carattere e commerciale (&) è anche utilizzabile per identificare le variabili di tipo `Long`. Per altre informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `&` operatore per forzare la concatenazione di stringhe. Il risultato è un valore stringa che rappresenta la concatenazione di due operandi stringa.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori di concatenazione in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
