---
title: Clausola Distinct (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ed92d5d601c1ec329728346ac881c4fa2bad8aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
