---
title: Operatore TypeOf
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 0cce36073b53442bce63f966f3bd94bd5d70d2a8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406327"
---
# <a name="typeof-operator-visual-basic"></a>Operatore TypeOf (Visual Basic)
Verifica se il tipo di runtime del risultato di un'espressione è compatibile con il tipo specificato.
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Restituita. Valore `Boolean`.  
  
 `objectexpression`  
 Obbligatorio. Qualsiasi espressione che restituisce un tipo riferimento.  
  
 `typename`  
 Obbligatorio. Qualsiasi nome di un tipo di dati.  
  
## <a name="remarks"></a>Commenti  
 L'operatore `TypeOf` determina se il tipo di `objectexpression` in fase di esecuzione è compatibile con `typename`. La compatibilità dipende dalla categoria del tipo di `typename`. La tabella seguente illustra come viene determinata la compatibilità.  
  
|Categoria del tipo di `typename`|Criterio di compatibilità|  
|---------------------------------|-----------------------------|  
|Class|`objectexpression` è del tipo `typename` o eredita da `typename`|  
|Struttura|`objectexpression` è del tipo `typename`|  
|Interfaccia|`objectexpression` implementa `typename` o eredita da una classe che implementa `typename`|  
  
 Se il tipo di `objectexpression` in fase di esecuzione soddisfa il criterio di compatibilità, `result` sarà `True`. In caso contrario, `result` sarà `False`.  Se `objectexpression` è null, `TypeOf`...`Is` restituisce `False` e ...`IsNot` restituisce `True`.  
  
 `TypeOf` viene sempre usato con la parola chiave `Is` per costruire un'espressione `TypeOf`...`Is` oppure con la parola chiave `IsNot` per costruire un'espressione `TypeOf`...`IsNot`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente le espressioni `TypeOf`...`Is` vengono usate per verificare la compatibilità dei tipi di due variabili di riferimento a un oggetto con diversi tipi di dati.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 La variabile `refInteger` presenta un tipo in fase di esecuzione `Integer`. È compatibile con `Integer`, ma non con `Double`. La variabile `refForm` presenta un tipo in fase di esecuzione <xref:System.Windows.Forms.Form>. È compatibile con <xref:System.Windows.Forms.Form> perché si tratta del relativo tipo, con <xref:System.Windows.Forms.Control> perché <xref:System.Windows.Forms.Form> eredita da <xref:System.Windows.Forms.Control> e con <xref:System.ComponentModel.IComponent> perché <xref:System.Windows.Forms.Form> eredita da <xref:System.ComponentModel.Component>, che implementa <xref:System.ComponentModel.IComponent>. `refForm` non è invece compatibile con <xref:System.Windows.Forms.Label>.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Is](is-operator.md)
- [Operatore IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
