---
title: 'Procedura: determinare se due oggetti sono identici'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348606"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Procedura: determinare se due oggetti sono identici (Visual Basic)
In Visual Basic, due riferimenti a variabili sono considerati identici se i relativi puntatori sono gli stessi, ovvero se entrambe le variabili puntano alla stessa istanza della classe in memoria. In una Windows Forms Application, ad esempio, può essere necessario eseguire un confronto per determinare se l'istanza corrente (`Me`) corrisponde a una particolare istanza, ad esempio `Form2`.  
  
 Visual Basic fornisce due operatori per confrontare i puntatori. L' [operatore is](../../../../visual-basic/language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e l' [operatore](../../../../visual-basic/language-reference/operators/isnot-operator.md) non viene restituito `True` se non lo sono.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinare se due oggetti sono identici  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Per determinare se due oggetti sono identici  
  
1. Configurare un'espressione `Boolean` per testare i due oggetti.  
  
2. Nell'espressione di test usare l'operatore `Is` con i due oggetti come operandi.  
  
     `Is` restituisce `True` se gli oggetti puntano alla stessa istanza della classe.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinare se due oggetti non sono identici  
 In alcuni casi si desidera eseguire un'azione se i due oggetti non sono identici e può essere scomodo combinare `Not` e `Is`, ad esempio `If Not obj1 Is obj2`. In tal caso, è possibile usare l'operatore `IsNot`.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Per determinare se due oggetti non sono identici  
  
1. Configurare un'espressione `Boolean` per testare i due oggetti.  
  
2. Nell'espressione di test usare l'operatore `IsNot` con i due oggetti come operandi.  
  
     `IsNot` restituisce `True` se gli oggetti non puntano alla stessa istanza della classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono testate coppie di variabili di `Object` per verificare se puntano alla stessa istanza della classe.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 Nell'esempio precedente viene visualizzato il seguente output.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vedere anche

- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Procedura: determinare se due oggetti sono correlati](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
