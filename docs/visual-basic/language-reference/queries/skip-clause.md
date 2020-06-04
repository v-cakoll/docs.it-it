---
title: Clausola Skip
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359658"
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
  
## <a name="remarks"></a>Commenti  
 La `Skip` clausola fa in modo che una query ignori gli elementi all'inizio di un elenco di risultati e restituisca gli elementi rimanenti. Il numero di elementi da ignorare è identificato dal `count` parametro.  
  
 È possibile utilizzare la `Skip` clausola con la `Take` clausola per restituire un intervallo di dati da qualsiasi segmento di una query. A tale scopo, passare l'indice del primo elemento dell'intervallo alla `Skip` clausola e la dimensione dell'intervallo alla `Take` clausola.  
  
 Quando si utilizza la `Skip` clausola in una query, potrebbe essere necessario assicurarsi che i risultati vengano restituiti in un ordine che consentirà alla `Skip` clausola di ignorare i risultati desiderati. Per ulteriori informazioni sull'ordinamento dei risultati di query, vedere [clausola ORDER BY](order-by-clause.md).  
  
 È possibile usare la `SkipWhile` clausola per specificare che solo determinati elementi vengono ignorati, a seconda della condizione specificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata la `Skip` clausola insieme alla `Take` clausola per restituire dati da una query in pagine. La `GetCustomers` funzione utilizza la `Skip` clausola per ignorare i clienti nell'elenco fino al valore di indice iniziale fornito e utilizza la `Take` clausola per restituire una pagina di clienti a partire da tale valore di indice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola Order By](order-by-clause.md)
- [Clausola Skip While](skip-while-clause.md)
- [Clausola Take](take-clause.md)
