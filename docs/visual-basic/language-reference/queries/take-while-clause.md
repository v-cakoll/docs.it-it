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
ms.openlocfilehash: f7e0587d7737d99d48fcc9cd4a102e78248a55e5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979934"
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
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
