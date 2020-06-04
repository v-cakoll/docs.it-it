---
title: Clausola Take
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 25dd06905525a96bc1504f033eb4f19af6d454a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359632"
---
# <a name="take-clause-visual-basic"></a>Clausola Take (Visual Basic)
Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Parti  
 `count`  
 Obbligatorio. Valore o espressione che restituisce il numero di elementi della sequenza da restituire.  
  
## <a name="remarks"></a>Commenti  
 La `Take` clausola fa in modo che una query includa un numero specificato di elementi contigui dall'inizio di un elenco di risultati. Il numero di elementi da includere è specificato dal `count` parametro.  
  
 È possibile utilizzare la `Take` clausola con la `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo alla `Skip` clausola e la dimensione dell'intervallo alla `Take` clausola. In questo caso, la `Take` clausola deve essere specificata dopo la `Skip` clausola.  
  
 Quando si utilizza la `Take` clausola in una query, potrebbe essere necessario assicurarsi che i risultati vengano restituiti in un ordine che consenta alla `Take` clausola di includere i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](order-by-clause.md).  
  
 È possibile utilizzare la `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, a seconda della condizione specificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la `Take` clausola insieme alla `Skip` clausola per restituire dati da una query in pagine. La funzione GetCustomers utilizza la `Skip` clausola per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e utilizza la `Take` clausola per restituire una pagina di clienti a partire da tale valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola Order By](order-by-clause.md)
- [Clausola Take While](take-while-clause.md)
- [Clausola Skip](skip-clause.md)
