---
title: Clausola Skip While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 3d6caeb1938e8e53e8ec2575f740cd5e49496f62
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839899"
---
# <a name="skip-while-clause-visual-basic"></a>Clausola Skip While (Visual Basic)
Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Un'espressione che rappresenta una condizione di test per gli elementi. L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un `Integer` deve essere valutata come un `Boolean`.|  
  
## <a name="remarks"></a>Note  
 Il `Skip While` clausola ignora gli elementi dall'inizio del risultato della query finché l'oggetto fornito `expression` restituisce `false`. Dopo aver `expression` restituisce `false`, la query restituisce tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 Il `Skip While` clausola differisce dal `Where` clausola in quanto il `Where` clausola può essere utilizzata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione. Il `Skip While` clausola esclude gli elementi solo fino al primo non viene soddisfatta la condizione. Il `Skip While` clausola è particolarmente utile quando si lavora con un risultato della query ordinati.  
  
 È possibile ignorare un determinato numero di risultati a partire dall'inizio del risultato della query usando il `Skip` clausola.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Skip While` clausola per ignorare i risultati fino a quando non viene trovato il primo cliente dagli Stati Uniti.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
