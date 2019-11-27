---
title: Operazioni del quantificatore
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346590"
---
# <a name="quantifier-operations-visual-basic"></a>Operazioni del quantificatore (Visual Basic)
Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.  
  
 La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine. La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`. La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Tutte|Determina se tutti gli elementi di una sequenza soddisfano una condizione.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Any|Determina se alcuni elementi di una sequenza soddisfano una condizione.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Contiene|Determina se una sequenza contiene un elemento specifico.|Non applicabile.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
 In questi esempi viene utilizzata la clausola `Aggregate` in Visual Basic come parte della condizione di filtro in una query LINQ.  
  
 Nell'esempio seguente viene utilizzata la clausola `Aggregate` e il metodo di estensione <xref:System.Linq.Enumerable.All%2A> per restituire da una raccolta le persone i cui animali sono di età superiore a quella specificata.  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 Nell'esempio seguente viene usata la clausola `Aggregate` e il metodo di estensione <xref:System.Linq.Enumerable.Any%2A> per restituire da una raccolta le persone che hanno almeno un animale che è antecedente a una determinata età.  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Procedura: eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
