---
title: 'Procedura: determinare se due oggetti sono identici (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Procedura: determinare se due oggetti sono identici (Visual Basic)
In Visual Basic, due riferimenti a variabili sono considerati identici se i relativi puntatori sono uguali, vale a dire, se entrambe le variabili puntano alla stessa istanza di classe in memoria. Ad esempio, in un'applicazione Windows Form, è consigliabile eseguire un confronto per determinare se l'istanza corrente (`Me`) è uguale a un'istanza specifica, ad esempio `Form2`.  
  
 Visual Basic fornisce due operatori per confrontare i puntatori. Il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e [operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) restituisce `True` se non lo sono.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinare se due oggetti sono identici  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Per determinare se due oggetti sono identici  
  
1.  Impostare un `Boolean` espressione per testare i due oggetti.  
  
2.  Nell'espressione test, utilizzare il `Is` operatore con i due oggetti come operandi.  
  
     `Is` Restituisce `True` se gli oggetti puntano alla stessa istanza di classe.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinare se due oggetti non sono identici  
 Talvolta si desidera eseguire un'azione, se i due oggetti non sono identici, ma può essere difficile combinare `Not` e `Is`, ad esempio `If Not obj1 Is obj2`. In questo caso è possibile utilizzare il `IsNot` operatore.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Per determinare se due oggetti non sono identici  
  
1.  Impostare un `Boolean` espressione per testare i due oggetti.  
  
2.  Nell'espressione test, utilizzare il `IsNot` operatore con i due oggetti come operandi.  
  
     `IsNot` Restituisce `True` se gli oggetti non puntano alla stessa istanza di classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente verifica coppie di `Object` variabili per stabilire se puntano alla stessa istanza di classe.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 Nell'esempio precedente viene visualizzato l'output seguente.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vedere anche  
 [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Procedura: determinare se due oggetti sono correlati](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
