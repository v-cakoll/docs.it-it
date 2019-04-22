---
title: Partizionamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: b857c8c6e6b56a7263e6725a747e98ccfe4ff4fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832463"
---
# <a name="partitioning-data-c"></a>Partizionamento dei dati (C#)
Il partizionamento in LINQ è l'operazione di divisione di una sequenza di input in due sezioni senza ridisposizione degli elementi e la successiva restituzione di una delle sezioni.  
  
 La figura seguente illustra i risultati di tre diverse operazioni di partizionamento in una sequenza di caratteri. La prima operazione restituisce i primi tre elementi nella sequenza. La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti. La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.  
  
 ![Figura che illustra tre operazioni di partizionamento LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Nella sezione seguente sono elencati i metodi degli operatori di query standard che eseguono la partizione delle sequenze.  
  
## <a name="operators"></a>Operatori  
  
|Nome dell'operatore|Description|Sintassi di espressione della query C#|Altre informazioni|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|Ignora gli elementi fino a una posizione specificata in una sequenza.|Non applicabile.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Ignora gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|Non applicabile.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Accetta gli elementi fino a una posizione specificata in una sequenza.|Non applicabile.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Accetta gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|Non applicabile.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
