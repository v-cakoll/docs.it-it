---
title: Operazioni sugli elementi (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a>Operazioni sugli elementi (C#)
Le operazioni sugli elementi restituiscono un singolo elemento specifico di una sequenza.  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sugli elementi.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|Restituisce l'elemento in corrispondenza dell'indice specificato in una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=nameWithType>|  
|ElementAtOrDefault|Restituisce l'elemento in corrispondenza di un indice specificato in una Collection o un valore predefinito se l'indice è esterno all'intervallo.|Non applicabile.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=nameWithType>|  
|First|Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=nameWithType>|  
|FirstOrDefault|Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione. Restituisce un valore predefinito se questo tipo di elemento non esiste.|Non applicabile.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=nameWithType>|  
|Ultimo|Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=nameWithType>|  
|LastOrDefault|Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione. Restituisce un valore predefinito se questo tipo di elemento non esiste.|Non applicabile.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=nameWithType>|  
|Single|Restituisce l'unico elemento di una Collection o l'unico elemento che soddisfa una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=nameWithType>|  
|SingleOrDefault|Restituisce l'unico elemento di una Collection o l'unico elemento che soddisfa una condizione. Restituisce un valore predefinito se tale elemento non esiste o la Collection non contiene esattamente un elemento.|Non applicabile.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq>   
 [Cenni preliminari sugli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

