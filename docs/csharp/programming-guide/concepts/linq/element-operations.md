---
title: Operazioni sugli elementi (C#)
description: Informazioni sui metodi dell'operatore query standard che eseguono operazioni sugli elementi, che restituiscono un singolo elemento da una sequenza in C#.
ms.date: 10/03/2018
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
ms.openlocfilehash: 8cd34146a3b93205ec01ed128aacb79d566a03c6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105445"
---
# <a name="element-operations-c"></a>Operazioni sugli elementi (C#)

Le operazioni sugli elementi restituiscono un singolo elemento specifico di una sequenza.  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sugli elementi.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|Restituisce l'elemento in corrispondenza dell'indice specificato in una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=nameWithType>|  
|ElementAtOrDefault|Restituisce l'elemento in corrispondenza di un indice specificato in una Collection o un valore predefinito se l'indice è esterno all'intervallo.|Non applicabile.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=nameWithType>|  
|Primo|Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=nameWithType>|  
|FirstOrDefault|Restituisce il primo elemento di una Collection o il primo elemento che soddisfa una condizione. Restituisce un valore predefinito se questo tipo di elemento non esiste.|Non applicabile.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=nameWithType>|  
|Last (Ultimo)|Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione.|Non applicabile.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=nameWithType>|  
|LastOrDefault|Restituisce l'ultimo elemento di una Collection o l'ultimo elemento che soddisfa una condizione. Restituisce un valore predefinito se questo tipo di elemento non esiste.|Non applicabile.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=nameWithType>|  
|Single|Restituisce l'unico elemento di una raccolta o l'unico elemento che soddisfa una condizione. Genera un'eccezione <xref:System.InvalidOperationException> se non è presente alcun elemento o sono presenti più elementi da restituire. |Non applicabile.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=nameWithType>|  
|SingleOrDefault|Restituisce l'unico elemento di una raccolta o l'unico elemento che soddisfa una condizione. Restituisce un valore predefinito se non sono presenti elementi da restituire. Genera un'eccezione <xref:System.InvalidOperationException> se sono presenti più elementi da restituire. |Non applicabile.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Come eseguire una query per il file o i file più grandi in un albero di directory (LINQ) (C#)](./how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
