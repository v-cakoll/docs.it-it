---
title: Operazioni del quantificatore (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 090bc53c3dcedc82972ab7d16fa2968011a7db65
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412253"
---
# <a name="quantifier-operations-c"></a>Operazioni del quantificatore (C#)
Le operazioni del quantificatore restituiscono un valore <xref:System.Boolean>, che indica se alcuni o tutti gli elementi di una sequenza soddisfano una condizione.  
  
 La figura seguente illustra due diverse operazioni del quantificatore in due diverse sequenze di origine. La prima operazione chiede se uno o più elementi sono il carattere "A" e il risultato è `true`. La seconda operazione chiede se tutti gli elementi sono il carattere "A" e il risultato è `true`.  
  
 ![Operazioni con quantificatore LINQ](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni del quantificatore.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Description|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Tutti|Determina se tutti gli elementi di una sequenza soddisfano una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|Qualsiasi|Determina se alcuni elementi di una sequenza soddisfano una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|Contiene|Determina se una sequenza contiene un elemento specifico.|Non applicabile.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Procedura: Specificare dinamicamente i filtri dei predicati in fase di esecuzione](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [Procedura: Eseguire una query per trovare frasi che contengono un set definito di parole (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
