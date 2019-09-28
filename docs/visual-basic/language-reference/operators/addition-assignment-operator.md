---
title: Operatore += (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 249a19abfb08677c01ac4cc484d049a7ed1a983c
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591639"
---
# <a name="-operator-visual-basic"></a>Operatore += (Visual Basic)
Aggiunge il valore di un'espressione numerica al valore di una variabile o di una proprietà numerica e assegna il risultato alla variabile o alla proprietà. Può essere usato anche per concatenare un'espressione `String` a una variabile o una proprietà `String` e assegnare il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica o `String`.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica o `String`.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro dell'operatore `+=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 L'operatore `+=` aggiunge il valore a destra alla variabile o alla proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra. L'operatore `+=` può essere usato anche per concatenare l'espressione `String` a destra della variabile `String` o della proprietà a sinistra e assegnare il risultato alla variabile o alla proprietà a sinistra.  
  
> [!NOTE]
> Quando si usa l'operatore `+=`, potrebbe non essere possibile determinare se si verificherà l'aggiunta o la concatenazione di stringhe. Usare l'operatore `&=` per la concatenazione per eliminare l'ambiguità e fornire codice autodocumentato.  
  
 Questo operatore di assegnazione esegue in modo implicito le conversioni verso un tipo di ingrandimento ma non di restringimento se l'ambiente di compilazione impone una semantica rigida. Per ulteriori informazioni su queste conversioni, vedere la pagina relativa alle [conversioni](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)verso un tipo di dati più piccolo. Per ulteriori informazioni sulla semantica restrittiva e permissiva, vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Se sono consentite semantiche permissive, l'operatore `+=` esegue in modo implicito una serie di conversioni di stringa e numeriche identiche a quelle eseguite dall'operatore `+`. Per informazioni dettagliate su queste conversioni, vedere [operatore +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Overload  
 L'operatore `+` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell'operatore `+` influiscono sul comportamento dell'operatore `+=`. Se il codice USA `+=` su una classe o una struttura che esegue l'overload `+`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `+=` per combinare il valore di una variabile con un'altra. Nella prima parte viene utilizzato `+=` con variabili numeriche per aggiungere un valore a un altro. La seconda parte USA `+=` con le variabili `String` per concatenare un valore con un altro. In entrambi i casi, il risultato viene assegnato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".  
  
## <a name="see-also"></a>Vedere anche

- [Operatore +](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
