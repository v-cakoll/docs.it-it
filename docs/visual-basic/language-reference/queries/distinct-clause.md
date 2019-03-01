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
ms.openlocfilehash: 00a2e52bd6669869bb2e25bc2857f1598da5763f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971247"
---
# <a name="distinct-clause-visual-basic"></a>Clausola Distinct (Visual Basic)
Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successiva.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Note  
 È possibile usare il `Distinct` clausola per restituire un elenco di elementi univoci. Il `Distinct` clausola fa sì che la query ignorare i risultati della query duplicate. Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola. Se nessun `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nel `From` clausola. Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrisponde a un risultato di query esistente.  
  
## <a name="example"></a>Esempio  
 L'espressione di query seguente viene aggiunto un elenco di clienti e un elenco di ordini dei clienti. Il `Distinct` clausola è inclusa per restituire un elenco di nomi di clienti univoci e ordinare le date.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
