---
title: Clausola Take While (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c8add6c55bb9353bac3489e68f497cb32785aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 Il `Take While` clausola include gli elementi dall'inizio del risultato della query fino a quando il parametro fornito `expression` restituisce `false`. Dopo il `expression` restituisce `false`, la query ignora tutti gli elementi rimanenti. Il `expression` viene ignorato per i risultati rimanenti.  
  
 Il `Take While` clausola differisce dal `Where` una clausola di `Where` clausola può essere utilizzata per includere tutti gli elementi da una query che soddisfano una determinata condizione. Il `Take While` clausola include gli elementi solo fino a quando la prima volta che non viene soddisfatta la condizione. Il `Take While` clausola è particolarmente utile quando si lavora con un risultato della query ordinato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Take While` clausola per recuperare i risultati fino a quando non viene trovato il primo dei clienti senza ordini.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
