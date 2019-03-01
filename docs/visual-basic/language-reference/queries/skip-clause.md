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
ms.openlocfilehash: 8441e619cdbd18545be72fd701c2cc9b1cf495d9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971237"
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
 Il `Skip` clausola provoca una query ignorare gli elementi all'inizio di un elenco dei risultati e restituire gli elementi rimanenti. Il numero di elementi da ignorare è identificato dal `count` parametro.  
  
 È possibile usare la `Skip` clausola con il `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A questo scopo, passare l'indice del primo elemento dell'intervallo per il `Skip` clausola e le dimensioni dell'intervallo dal `Take` clausola.  
  
 Quando si usa la `Skip` clausola in una query, è necessario anche assicurarsi che i risultati vengono restituiti in un ordine che consentirà di `Skip` clausola per ignorare i risultati desiderati. Per altre informazioni su come ordinare i risultati della query, vedere [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile usare il `SkipWhile` clausola per specificare che solo alcuni elementi vengono ignorati, a seconda di una condizione fornita.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Skip` clausola insieme al `Take` clausola per restituire i dati da una query nelle pagine. Il `GetCustomers` funzione Usa le `Skip` clausola per ignorare i clienti nell'elenco fino a quando il valore iniziale specificato valore di indice e utilizza il `Take` clausola per restituire una pagina di clienti a partire dal valore di indice specificato.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
