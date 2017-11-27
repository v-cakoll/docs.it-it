---
title: Operazioni quantificatore (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a>Operazioni quantificatore (Visual Basic)
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
 Negli esempi viene utilizzata la `Aggregate` clausola in Visual Basic come parte della condizione di filtro in una query LINQ.  
  
 L'esempio seguente usa il `Aggregate` clausola e <xref:System.Linq.Enumerable.All%2A> metodo di estensione per restituire da una raccolta le persone con animali domestici tutti più vecchi di un periodo di memorizzazione specificato.  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 L'esempio seguente viene utilizzata la `Aggregate` clausola e <xref:System.Linq.Enumerable.Any%2A> metodo di estensione per restituire una raccolta coloro che hanno almeno un animale che è antecedente a un periodo di memorizzazione specificato.  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq>  
 [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Procedura: eseguire una Query per frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
