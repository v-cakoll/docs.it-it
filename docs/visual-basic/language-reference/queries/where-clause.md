---
title: Clausola Where (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2572f513d00bc72e869cf28d382be799f7a303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-visual-basic"></a>Clausola Where (Visual Basic)
Specifica la condizione di filtro per una query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. Un'espressione che determina se i valori per l'elemento corrente nella raccolta vengono inclusi nella raccolta di output. L'espressione deve restituire un `Boolean` valore o l'equivalente di un `Boolean` valore. Se la condizione restituisce `True`, l'elemento è incluso nel risultato della query; in caso contrario, l'elemento viene escluso dai risultati della query.  
  
## <a name="remarks"></a>Note  
 Il `Where` clausola consente di filtrare i dati di query selezionando solo gli elementi che soddisfano determinati criteri. Gli elementi i cui valori determinano la `Where` clausola in modo che restituisca `True` sono inclusi nel risultato della query; sono esclusi gli altri elementi. L'espressione utilizzata in un `Where` clausola deve restituire un `Boolean` o l'equivalente di un `Boolean`, ad esempio un Integer che restituisce `False` quando il valore è zero. È possibile combinare più espressioni in un `Where` clausola tramite gli operatori logici, ad esempio `And`, `Or`, `AndAlso`, `OrElse`, `Is`, e `IsNot`.  
  
 Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vi si accede, ad esempio, quando vengono associati a dati o scorrere in un `For` ciclo. Di conseguenza, il `Where` clausola non viene valutata fino a quando non si accede alla query. Se si dispone di valori esterni per la query che vengono utilizzati nel `Where` clausola, venga utilizzato il valore appropriato nel `Where` clausola al momento dell'esecuzione della query. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura nella prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 È possibile chiamare funzioni all'interno di un `Where` clausola per eseguire un calcolo o un'operazione su un valore dall'elemento corrente nella raccolta. Chiamata di una funzione un `Where` clausola può provocare la query venga eseguita immediatamente quando viene definita anziché quando vi si accede. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura nella prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza un `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto di `customers` insieme. Il `Where` clausola utilizza la variabile di intervallo per limitare l'output ai clienti dalla regione specificata. Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa `And` e `Or` operatori logici nella `Where` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
