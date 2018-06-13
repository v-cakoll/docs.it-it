---
title: Clausola Skip (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602827"
---
# <a name="skip-clause-visual-basic"></a>Clausola Skip (Visual Basic)
Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Skip count  
```  
  
## <a name="parts"></a>Parti  
 `count`  
 Obbligatorio. Un valore o un'espressione che restituisce il numero di elementi della sequenza da ignorare.  
  
## <a name="remarks"></a>Note  
 Il `Skip` clausola interrompe una query ignora gli elementi all'inizio di un elenco di risultati e restituisce gli elementi rimanenti. Il numero di elementi da ignorare è identificato dal `count` parametro.  
  
 È possibile utilizzare il `Skip` clausola con il `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo per il `Take` clausola.  
  
 Quando si utilizza il `Skip` clausola in una query, è necessario anche per assicurarsi che i risultati vengono restituiti in un ordine, per consentire il `Skip` clausola per ignorare i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati della query, vedere [clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile utilizzare il `SkipWhile` clausola per specificare che solo determinati elementi vengano ignorati, a seconda di una condizione fornita.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Skip` clausola con il `Take` clausola per restituire dati da una query in pagine. Il `GetCustomers` funzione Usa il `Skip` clausola per ignorare i clienti nell'elenco finché l'iniziale fornito valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire da quel valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
