---
title: Clausola Take (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: cb109eaf43fee19b77ac690492b85919c9d78301
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816954"
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
 Il `Take` clausola provoca una query includere un numero specificato di elementi contigui dall'inizio di un elenco di risultati. Viene specificato il numero di elementi da includere per il `count` parametro.  
  
 È possibile usare la `Take` clausola con il `Skip` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A questo scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo dal `Take` clausola. In questo caso, il `Take` clausola deve essere specificata dopo il `Skip` clausola.  
  
 Quando si usa la `Take` clausola in una query, è necessario anche assicurarsi che i risultati vengono restituiti in un ordine che consentirà di `Take` clausola per includere i risultati desiderati. Per altre informazioni su come ordinare i risultati della query, vedere [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile usare il `TakeWhile` clausola per specificare che vengano restituiti solo determinati elementi, in base a una condizione specificata.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Take` clausola insieme al `Skip` clausola per restituire i dati da una query nelle pagine. La funzione GetCustomers utilizza il `Skip` clausola per ignorare i clienti nell'elenco fino a quando il valore iniziale specificato valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire dal valore di indice specificato.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
