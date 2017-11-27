---
title: Clausola Skip While (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 Il `Skip While` clausola ignora gli elementi dall'inizio del risultato della query fino a quando il parametro fornito `expression` restituisce `false`. Dopo aver `expression` restituisce `false`, la query restituisce tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 Il `Skip While` clausola differisce dal `Where` una clausola di `Where` clausola può essere utilizzata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione. Il `Skip While` clausola esclude gli elementi solo fino a quando la prima volta che non viene soddisfatta la condizione. Il `Skip While` clausola è particolarmente utile quando si lavora con un risultato della query ordinato.  
  
 È possibile ignorare un determinato numero di risultati dall'inizio del risultato della query utilizzando il `Skip` clausola.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Skip While` clausola per ignorare i risultati fino a quando non viene trovato il primo cliente dagli Stati Uniti.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
