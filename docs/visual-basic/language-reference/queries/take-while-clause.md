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
ms.openlocfilehash: 4b6133efdbd9c46ab85201ad454671e5538b6a81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359580"
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
|`expression`|Obbligatorio. Espressione che rappresenta una condizione per cui verificare gli elementi. L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un oggetto `Integer` da valutare come `Boolean` .|  
  
## <a name="remarks"></a>Commenti  
 La `Take While` clausola include gli elementi dall'inizio di un risultato della query fino a quando l'oggetto specificato `expression` restituisce `false` . Una volta `expression` restituiti `false` , la query ignorerà tutti gli elementi rimanenti. `expression`Viene ignorato per i risultati rimanenti.  
  
 La clausola è `Take While` diversa dalla `Where` clausola in quanto la `Where` clausola può essere utilizzata per includere tutti gli elementi di una query che soddisfano una determinata condizione. La `Take While` clausola include gli elementi solo fino alla prima volta che la condizione non viene soddisfatta. La `Take While` clausola è particolarmente utile quando si lavora con un risultato di query ordinato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la `Take While` clausola per recuperare i risultati fino a quando non viene trovato il primo cliente senza ordini.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola Take](take-clause.md)
- [Clausola Skip While](skip-while-clause.md)
- [Clausola WHERE](where-clause.md)
