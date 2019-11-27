---
title: Clausola Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347103"
---
# <a name="take-while-clause-visual-basic"></a>Clausola Take While (Visual Basic)
Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatoria. Espressione che rappresenta una condizione per cui verificare gli elementi. L'espressione deve restituire un valore `Boolean` o un equivalente funzionale, ad esempio un `Integer` da valutare come `Boolean`.|  
  
## <a name="remarks"></a>Note  
 La clausola `Take While` include gli elementi dall'inizio di un risultato della query fino a quando l'`expression` fornito non restituisce `false`. Quando il `expression` restituisce `false`, la query ignorerà tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 La clausola `Take While` differisce dalla clausola `Where` in quanto la clausola `Where` può essere utilizzata per includere tutti gli elementi di una query che soddisfano una determinata condizione. La clausola `Take While` include gli elementi solo fino alla prima volta che la condizione non viene soddisfatta. La clausola `Take While` è particolarmente utile quando si utilizza un risultato di query ordinato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la clausola `Take While` per recuperare i risultati fino a quando non viene trovato il primo cliente senza ordini.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
