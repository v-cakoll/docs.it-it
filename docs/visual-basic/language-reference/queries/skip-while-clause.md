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
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004705"
---
# <a name="skip-while-clause-visual-basic"></a>Clausola Skip While (Visual Basic)
Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Parti  
  
|Nome|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Espressione che rappresenta una condizione per cui verificare gli elementi. L'espressione deve restituire un valore `Boolean` o un equivalente funzionale, ad esempio un `Integer` da valutare come `Boolean`.|  
  
## <a name="remarks"></a>Note  
 La clausola `Skip While` ignora gli elementi dall'inizio di un risultato della query fino a quando il `expression` fornito restituisce `false`. Dopo che `expression` restituisce `false`, la query restituisce tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 La clausola `Skip While` è diversa dalla clausola `Where` in quanto la clausola `Where` può essere usata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione. La clausola `Skip While` esclude gli elementi solo fino alla prima volta che la condizione non viene soddisfatta. La clausola `Skip While` è particolarmente utile quando si utilizza un risultato di query ordinato.  
  
 È possibile ignorare un numero specifico di risultati dall'inizio di un risultato della query utilizzando la clausola `Skip`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la clausola `Skip While` per ignorare i risultati fino a quando non viene trovato il primo cliente del Stati Uniti.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
