---
title: Clausola Distinct
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 5aecffbce036500d294d03a925798d51f1269af6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401394"
---
# <a name="distinct-clause-visual-basic"></a>Clausola Distinct (Visual Basic)
Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successive.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Osservazioni  
 È possibile utilizzare la `Distinct` clausola per restituire un elenco di elementi univoci. La `Distinct` clausola fa in modo che la query ignori i risultati di query duplicati. La `Distinct` clausola si applica ai valori duplicati per tutti i campi restituiti specificati dalla `Select` clausola. Se non `Select` viene specificata alcuna clausola, la `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nella `From` clausola. Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà solo il risultato di una query se tutti i membri del tipo corrispondono a un risultato della query esistente.  
  
## <a name="example"></a>Esempio  
 L'espressione di query seguente unisce un elenco di clienti e un elenco di ordini dei clienti. La `Distinct` clausola viene inclusa per restituire un elenco di nomi di clienti e date degli ordini univoci.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola from](from-clause.md)
- [Clausola SELECT](select-clause.md)
- [Clausola WHERE](where-clause.md)
