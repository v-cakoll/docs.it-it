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
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603977"
---
# <a name="distinct-clause-visual-basic"></a>Clausola Distinct (Visual Basic)
Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successive.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `Distinct` clausola per restituire un elenco di elementi univoci. Il `Distinct` clausola, la query di ignorare i risultati di query duplicata. Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola. Se non `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nella `From` clausola. Se la variabile di intervallo non è un tipo immutabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrispondano a un risultato della query esistente.  
  
## <a name="example"></a>Esempio  
 L'espressione di query seguente unisce in join un elenco di clienti e un elenco di ordini cliente. Il `Distinct` clausola viene inclusa per restituire un elenco di nomi di clienti univoci e Data ordine.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
