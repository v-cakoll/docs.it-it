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
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349639"
---
# <a name="take-clause-visual-basic"></a>Clausola Take (Visual Basic)
Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Take count  
```  
  
## <a name="parts"></a>Parti  
 `count`  
 Obbligatoria. Valore o espressione che restituisce il numero di elementi della sequenza da restituire.  
  
## <a name="remarks"></a>Note  
 La clausola `Take` fa in modo che una query includa un numero specificato di elementi contigui dall'inizio di un elenco di risultati. Il numero di elementi da includere è specificato dal parametro `count`.  
  
 È possibile utilizzare la clausola `Take` con la clausola `Skip` per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo alla clausola `Skip` e la dimensione dell'intervallo alla clausola `Take`. In questo caso, è necessario specificare la clausola `Take` dopo la clausola `Skip`.  
  
 Quando si utilizza la clausola `Take` in una query, potrebbe essere necessario verificare che i risultati vengano restituiti in un ordine che consenta alla clausola `Take` di includere i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile utilizzare la clausola `TakeWhile` per specificare che vengano restituiti solo determinati elementi, a seconda della condizione specificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la clausola `Take` insieme alla clausola `Skip` per restituire dati da una query in pagine. La funzione GetCustomers usa la clausola `Skip` per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e usa la clausola `Take` per restituire una pagina di clienti a partire da tale valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
