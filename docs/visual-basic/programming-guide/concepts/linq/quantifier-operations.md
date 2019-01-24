---
title: Operazioni del quantificatore (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0f732cdb51ed4e26039fc8c1d02b95ad32f901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551930"
---
# <a name="quantifier-operations-visual-basic"></a>Operazioni del quantificatore (Visual Basic)
Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.  
  
 La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine. La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`. La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.  
  
 ![Operazioni con quantificatore LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi delle espressioni di Query Visual Basic|Altre informazioni|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Tutti|Determina se tutti gli elementi di una sequenza soddisfano una condizione.|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Qualsiasi|Determina se alcuni elementi di una sequenza soddisfano una condizione.|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Contiene|Determina se una sequenza contiene un elemento specifico.|Non applicabile.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
 Questi esempi usano il `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.  
  
 L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.All%2A> metodo di estensione per restituire da una raccolta le persone cui animali domestici tutto antecedenti a un periodo di validità specificato.  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.Any%2A> metodo di estensione per restituire da una raccolta di coloro che hanno almeno un animale che è precedente rispetto a un periodo di validità specificato.  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Procedura: Eseguire una query per trovare frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
