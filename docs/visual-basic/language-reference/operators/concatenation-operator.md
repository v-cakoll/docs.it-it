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
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592238"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operatore (Visual Basic)
Genera una concatenazione di stringhe di due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi variabile `String` o `Object`.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si allarga a `String`.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si allarga a `String`.  
  
## <a name="remarks"></a>Note  
 Se il tipo di dati di `expression1` o `expression2` non è `String` ma viene ampliato a `String`, viene convertito in `String`. Se uno dei tipi di dati non viene ampliato a `String`, il compilatore genera un errore.  
  
 Il tipo di dati di `result` è `String`. Se una o entrambe le espressioni restituiscono [Nothing](../../../visual-basic/language-reference/nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".  
  
> [!NOTE]
> L'operatore `&` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Il carattere e commerciale (&) può essere usato anche per identificare le variabili come tipo `Long`. Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l'operatore `&` per forzare la concatenazione di stringhe. Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori di concatenazione in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
