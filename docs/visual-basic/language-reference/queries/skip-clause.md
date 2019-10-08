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
ms.openlocfilehash: e52de186e1475bfabd02821a0cd2384d8350eed3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004773"
---
# <a name="skip-clause-visual-basic"></a>Clausola Skip (Visual Basic)
Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Parti  
 `count`  
 Obbligatorio. Valore o espressione che restituisce il numero di elementi della sequenza da ignorare.  
  
## <a name="remarks"></a>Note  
 La clausola `Skip` fa in modo che una query ignori gli elementi all'inizio di un elenco di risultati e restituisca gli elementi rimanenti. Il numero di elementi da ignorare è identificato dal parametro `count`.  
  
 È possibile utilizzare la clausola `Skip` con la clausola `Take` per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo alla clausola `Skip` e la dimensione dell'intervallo alla clausola `Take`.  
  
 Quando si utilizza la clausola `Skip` in una query, potrebbe essere necessario assicurarsi che i risultati vengano restituiti in un ordine che consentirà alla clausola `Skip` di ignorare i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 È possibile usare la clausola `SkipWhile` per specificare che solo determinati elementi vengono ignorati, a seconda della condizione specificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la clausola `Skip` insieme alla clausola `Take` per restituire dati da una query in pagine. La funzione `GetCustomers` usa la clausola `Skip` per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e usa la clausola `Take` per restituire una pagina di clienti a partire da tale valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
