---
title: Clausola Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359645"
---
# <a name="skip-while-clause-visual-basic"></a>Clausola Skip While (Visual Basic)
Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Espressione che rappresenta una condizione per cui verificare gli elementi. L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un oggetto `Integer` da valutare come `Boolean` .|  
  
## <a name="remarks"></a>Commenti  
 La `Skip While` clausola ignora gli elementi dall'inizio di un risultato della query fino a quando l'oggetto specificato `expression` restituisce `false` . `expression`Una volta restituito `false` , la query restituisce tutti gli elementi rimanenti. `expression`Viene ignorato per i risultati rimanenti.  
  
 La clausola è `Skip While` diversa dalla `Where` clausola in quanto la `Where` clausola può essere usata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione. La `Skip While` clausola esclude gli elementi solo fino alla prima volta che la condizione non viene soddisfatta. La `Skip While` clausola è particolarmente utile quando si lavora con un risultato di query ordinato.  
  
 È possibile ignorare un numero specifico di risultati dall'inizio di un risultato della query usando la `Skip` clausola.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la `Skip While` clausola per ignorare i risultati fino a quando non viene trovato il primo cliente del Stati Uniti.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola Skip](skip-clause.md)
- [Clausola Take While](take-while-clause.md)
- [Clausola WHERE](where-clause.md)
