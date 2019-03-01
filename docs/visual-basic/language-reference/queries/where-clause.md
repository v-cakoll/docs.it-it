---
title: Clausola Where (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 3d8f17c54d6a7767cc7a694ddb2508ae9ca4df60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971390"
---
# <a name="where-clause-visual-basic"></a>Clausola Where (Visual Basic)
Specifica la condizione di filtro per una query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Where condition  
```  
  
## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. Espressione che determina se i valori per l'elemento corrente nella raccolta sono inclusi nella raccolta di output. L'espressione deve restituire un `Boolean` valore o l'equivalente di un `Boolean` valore. Se la condizione restituisce `True`, l'elemento è incluso nel risultato della query; in caso contrario, l'elemento viene escluso dai risultati della query.  
  
## <a name="remarks"></a>Note  
 Il `Where` clausola consente di filtrare i dati delle query selezionando solo gli elementi che soddisfano determinati criteri. Gli elementi i cui valori che il `Where` clausola restituisca `True` sono incluse nel risultato della query; sono esclusi gli altri elementi. L'espressione che viene usato in un `Where` clausola deve corrispondere a un `Boolean` o l'equivalente di un `Boolean`, ad esempio un numero intero che restituisce `False` quando il valore è zero. È possibile combinare più espressioni in un `Where` clausola con operatori logici, ad esempio `And`, `Or`, `AndAlso`, `OrElse`, `Is`, e `IsNot`.  
  
 Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vi si accede, ad esempio, quando sono associati a dati o scorrere in un `For` ciclo. Di conseguenza, il `Where` clausola non viene valutata fino a quando non si accede alla query. Se si dispone di valori esterni per la query che vengono usate nel `Where` clausola, assicurarsi che il valore appropriato viene utilizzato nel `Where` clausola al momento dell'esecuzione della query. Per altre informazioni sull'esecuzione di query, vedere [Writing Your prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 È possibile chiamare funzioni all'interno di un `Where` clausola per eseguire un calcolo o un'operazione su un valore dall'elemento corrente nella raccolta. Chiamata a una funzione un `Where` clausola può comportare la query venga eseguita immediatamente quando viene definito anziché quando vi si accede. Per altre informazioni sull'esecuzione di query, vedere [Writing Your prima Query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Esempio  
 La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` dell'oggetto nel `customers` raccolta. Il `Where` clausola utilizza la variabile di intervallo per limitare l'output per i clienti dall'area specificata. Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa `And` e `Or` operatori logici nel `Where` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
