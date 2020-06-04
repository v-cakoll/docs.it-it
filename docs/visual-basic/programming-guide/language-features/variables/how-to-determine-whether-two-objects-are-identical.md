---
title: 'Procedura: determinare se due oggetti sono identici'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 67c3af8b7bdac3ad1c7e4908f1ac2684df7a87aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410477"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Procedura: determinare se due oggetti sono identici (Visual Basic)
In Visual Basic, due riferimenti a variabili sono considerati identici se i relativi puntatori sono gli stessi, ovvero se entrambe le variabili puntano alla stessa istanza della classe in memoria. In una Windows Forms Application, ad esempio, può essere necessario eseguire un confronto per determinare se l'istanza corrente ( `Me` ) è uguale a una particolare istanza, ad esempio `Form2` .  
  
 Visual Basic fornisce due operatori per confrontare i puntatori. L' [operatore is](../../../language-reference/operators/is-operator.md) restituisce `True` se gli oggetti sono identici e l' [operatore](../../../language-reference/operators/isnot-operator.md) non restituisce `True` se non lo sono.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinare se due oggetti sono identici  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Per determinare se due oggetti sono identici  
  
1. Configurare un' `Boolean` espressione per testare i due oggetti.  
  
2. Nell'espressione di test usare l' `Is` operatore con i due oggetti come operandi.  
  
     `Is`restituisce `True` se gli oggetti puntano alla stessa istanza della classe.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinare se due oggetti non sono identici  
 In alcuni casi si desidera eseguire un'azione se i due oggetti non sono identici e può essere scomodo combinare `Not` e `Is` , ad esempio `If Not obj1 Is obj2` . In tal caso, è possibile usare l' `IsNot` operatore.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Per determinare se due oggetti non sono identici  
  
1. Configurare un' `Boolean` espressione per testare i due oggetti.  
  
2. Nell'espressione di test usare l' `IsNot` operatore con i due oggetti come operandi.  
  
     `IsNot`restituisce `True` se gli oggetti non puntano alla stessa istanza della classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono testate coppie di `Object` variabili per verificare se puntano alla stessa istanza della classe.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 Nell'esempio precedente viene visualizzato il seguente output.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vedere anche

- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Variabili oggetto](object-variables.md)
- [Valori di variabili oggetto](object-variable-values.md)
- [Operatore Is](../../../language-reference/operators/is-operator.md)
- [Operatore IsNot](../../../language-reference/operators/isnot-operator.md)
- [Procedura: determinare se due oggetti sono correlati](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase e MyClass](../../program-structure/me-my-mybase-and-myclass.md)
