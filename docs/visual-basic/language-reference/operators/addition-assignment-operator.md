---
title: Operatore +=
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
ms.openlocfilehash: c2ce384901a9f0207e8279a5a07a88600c875e7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372207"
---
# <a name="-operator-visual-basic"></a>Operatore += (Visual Basic)
Aggiunge il valore di un'espressione numerica al valore di una variabile o di una proprietà numerica e assegna il risultato alla variabile o alla proprietà. Può essere usato anche per concatenare un' `String` espressione a una `String` variabile o a una proprietà e assegnare il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi `String` proprietà o variabile numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione o numerica `String` .  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `+=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).  
  
 L' `+=` operatore aggiunge il valore a destra alla variabile o alla proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra. L' `+=` operatore può essere usato anche per concatenare l' `String` espressione a destra della `String` variabile o della proprietà a sinistra e assegnare il risultato alla variabile o alla proprietà a sinistra.  
  
> [!NOTE]
> Quando si utilizza l' `+=` operatore, potrebbe non essere possibile determinare se si verificherà l'aggiunta o la concatenazione di stringhe. Usare l' `&=` operatore per la concatenazione per eliminare l'ambiguità e per fornire codice autodocumentato.  
  
 Questo operatore di assegnazione esegue in modo implicito le conversioni verso un tipo di ingrandimento ma non di restringimento se l'ambiente di compilazione impone una semantica rigida. Per ulteriori informazioni su queste conversioni, vedere la pagina relativa alle [conversioni](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)verso un tipo di dati più piccolo. Per ulteriori informazioni sulla semantica restrittiva e permissiva, vedere [istruzione Option Strict](../statements/option-strict-statement.md).  
  
 Se sono consentite semantiche permissive, l' `+=` operatore esegue in modo implicito una serie di conversioni di stringa e numeriche identiche a quelle eseguite dall' `+` operatore. Per informazioni dettagliate su queste conversioni, vedere [operatore +](addition-operator.md).  
  
## <a name="overloading"></a>Overload  
 L' `+` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `+` operatore influiscono sul comportamento dell' `+=` operatore. Se il codice usa `+=` su una classe o una struttura che esegue l'overload di `+` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `+=` operatore per combinare il valore di una variabile con un'altra. La prima parte USA `+=` con le variabili numeriche per aggiungere un valore a un altro. La seconda parte USA `+=` con le `String` variabili per concatenare un valore con un altro. In entrambi i casi, il risultato viene assegnato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".  
  
## <a name="see-also"></a>Vedere anche

- [Operatore +](addition-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Operatori di concatenazione](concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
