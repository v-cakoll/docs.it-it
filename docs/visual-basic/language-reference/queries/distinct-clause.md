---
title: Clausola Distinct (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: e8d3e38261a04c4d29faab351d24d6710413b09a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004798"
---
# <a name="distinct-clause-visual-basic"></a>Clausola Distinct (Visual Basic)
Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successive.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Distinct  
```  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la clausola `Distinct` per restituire un elenco di elementi univoci. La clausola `Distinct` fa in modo che la query ignori i risultati di query duplicati. La clausola `Distinct` si applica ai valori duplicati per tutti i campi restituiti specificati dalla clausola `Select`. Se non viene specificata alcuna clausola `Select`, la clausola `Distinct` viene applicata alla variabile di intervallo per la query identificata nella clausola `From`. Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà solo il risultato di una query se tutti i membri del tipo corrispondono a un risultato della query esistente.  
  
## <a name="example"></a>Esempio  
 L'espressione di query seguente unisce un elenco di clienti e un elenco di ordini dei clienti. La clausola `Distinct` è inclusa per restituire un elenco di nomi di clienti e date degli ordini univoci.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
