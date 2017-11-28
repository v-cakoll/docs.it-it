---
title: Clausola Take (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ee289a24c15226126a526af116ed53b4a9055b35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="take-clause-visual-basic"></a>Clausola Take (Visual Basic)
Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Take count  
```  
  
## <a name="parts"></a>Parti  
 `count`  
 Obbligatorio. Un valore o un'espressione che restituisce il numero di elementi della sequenza da restituire.  
  
## <a name="remarks"></a>Note  
 Il `Take` clausola interrompe una query includere un numero specificato di elementi contigui dall'inizio di un elenco di risultati. Da cui viene specificato il numero di elementi da includere il `count` parametro.  
  
 È possibile utilizzare il `Take` clausola con il `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo per il `Take` clausola. In questo caso, il `Take` clausola deve essere specificata dopo il `Skip` clausola.  
  
 Quando si utilizza il `Take` clausola in una query, è necessario anche per assicurarsi che i risultati vengono restituiti in un ordine, per consentire il `Take` clausola per includere i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati della query, vedere [clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile utilizzare il `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, a seconda di una condizione fornita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Take` clausola con il `Skip` clausola per restituire dati da una query in pagine. La funzione GetCustomers utilizza il `Skip` clausola per ignorare i clienti nell'elenco finché l'iniziale fornito valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire da quel valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
