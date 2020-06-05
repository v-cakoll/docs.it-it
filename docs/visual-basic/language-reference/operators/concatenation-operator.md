---
title: Operatore &amp;
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
ms.openlocfilehash: d778c0c99d6d074fe8b73aaf3660074643e7e136
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371609"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operatore (Visual Basic)
Genera una concatenazione di stringhe di due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `String` `Object` variabile o.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si allarga a `String` .  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione con un tipo di dati che si allarga a `String` .  
  
## <a name="remarks"></a>Commenti  
 Se il tipo di dati di `expression1` o `expression2` non è `String` ma si allarga a `String` , viene convertito in `String` . Se uno dei tipi di dati non viene ampliato a `String` , il compilatore genera un errore.  
  
 Il tipo di dati di `result` è `String` . Se una o entrambe le espressioni restituiscono [Nothing](../nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType> , vengono considerate come una stringa con un valore di "".  
  
> [!NOTE]
> L' `&` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Il carattere e commerciale (&) può essere usato anche per identificare le variabili come tipo `Long` . Per ulteriori informazioni, vedere [caratteri di tipo](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato l' `&` operatore per forzare la concatenazione di stringhe. Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore&=](and-assignment-operator.md)
- [Operatori di concatenazione](concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori di concatenazione in Visual Basic](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
