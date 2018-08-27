---
title: Clausola Take While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 181cc641bb12329c898cc3bb226ea49f0836e979
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932027"
---
# <a name="take-while-clause-visual-basic"></a>Clausola Take While (Visual Basic)
Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Take While expression  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Un'espressione che rappresenta una condizione di test per gli elementi. L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un `Integer` deve essere valutata come un `Boolean`.|  
  
## <a name="remarks"></a>Note  
 Il `Take While` clausola include gli elementi dall'inizio del risultato della query finché l'oggetto fornito `expression` restituisce `false`. Dopo il `expression` restituisce `false`, la query ignora tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 Il `Take While` clausola differisce dal `Where` clausola in quanto il `Where` clausola può essere utilizzata per includere tutti gli elementi da una query che soddisfano una determinata condizione. Il `Take While` clausola include gli elementi solo fino al primo non viene soddisfatta la condizione. Il `Take While` clausola è particolarmente utile quando si lavora con un risultato della query ordinati.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Take While` clausola per recuperare i risultati fino a quando non viene trovato il primo dei clienti senza ordini.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/index.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
